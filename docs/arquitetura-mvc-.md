# Arquitetura Lógica: Monolito Modular, 4 Camadas e Padrão MVC

## 1. Justificativa da Arquitetura: Porquê Monolito Modular?
O **Salutis** foi estruturado como um **Monolito Modular** num único repositório, com módulos estritamente separados por responsabilidade e fronteiras claras.

- **Porquê escolher Monolito Modular?** Garante simplicidade operacional, tipagem unificada, facilidade de teste de ponta a ponta e controlo total do estado entre o Totem do Paciente, o Painel da Enfermagem e o Dashboard do Coordenador.
- **Porquê NÃO usar Microsserviços nesta fase?** O custo de orquestração distribuída, latência de rede e complexidade de deploy não trazem benefício para a validação funcional do MVP acadêmico.

---

## 2. Arquitetura em 4 Camadas

1. **Camada de Apresentação (`/src/presentation/views`):**
   - Responsável exclusivamente pelas telas, navegação entre os 3 passos, rótulos acessíveis, estados vazios (*empty states*), modais de confirmação e feedback visual (Alto Contraste e Fonte Ampliada).
2. **Camada de Aplicação (`/src/application/controllers`):**
   - Orquestra os casos de uso e a sequência de ações do utilizador (`CheckInController`, `TriagemController`, `FilaController`), ligando os eventos da interface às entidades de domínio.
3. **Camada de Domínio (`/src/domain/models`):**
   - Contém as entidades baseadas no Diagrama de Classes UML (`Paciente`, `Atendimento`, `Triagem`, `Fila`, `Notificacao`) e as regras de negócio puras (validação de CPF/carteirinha, cálculo de tempo estimado e ordenação por Protocolo de Manchester + Estatuto do Idoso).
4. **Camada de Infraestrutura (`/src/infrastructure/mocks`):**
   - Fornece os dados fictícios (mocks 100% anonimizados em conformidade com a LGPD), persistência local em memória/contingência e referências de ativos exportados.

---

## 3. Mapeamento do Padrão MVC no Fluxo Principal

| Passo do Fluxo | Ação do Utilizador (Gatilho) | Controller Acionado (O Maestro) | Model Alterado / Regra Validada (O Cérebro) | View Atualizada (O Rosto) | Requisito Rastreável |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Passo 1: Check-in** | Paciente insere CPF fictício ou lê carteirinha e clica em *Confirmar Check-in* | `CheckInController.iniciarAtendimento()` | Cria instância de `Paciente` e `Atendimento`; valida formato de identificação e aplica flag `prioridadeLegal` (Idoso 60+). | Transita da **View 1 (Check-in)** para a **View 2 (Pré-Triagem)**. | `RF01`, `RNF01`, `US01` |
| **Passo 2: Pré-Triagem e Senha** | Paciente seleciona sintomas (*Dor, Falta de ar, Febre, Tontura*) e envia; Enfermagem classifica risco | `TriagemController.registrarSintomas()` e `TriagemController.classificarPrioridade()` | Atualiza `Triagem` (`sintomas`, `sinaisVitais`, `classificacao`); gera senha `A047` e insere na `Fila` conforme gravidade. | Exibe estado de confirmação na **View 2** com Senha `A047` e avança para a **View 3**. | `RF02`, `US02` |
| **Passo 3: Fila e Convocação** | Atualização em tempo real ou clique do enfermeiro em *Chamar Paciente* | `FilaController.atualizarPosicao()` e `FilaController.chamarPaciente()` | Recalcula `Fila.posicao` (`5º`) e `Atendimento.tempoEstimado` (`18 min`); muda status para `Convocado` e dispara `Notificacao.enviar()`. | **View 3 (Acompanhamento)** exibe alerta verde pulsante `"É a sua vez — Sala 03"`. | `RF03`, `RF04`, `RNF03` |
| **Ação Destrutiva: Cancelamento** | Paciente clica em *Cancelar Senha* e confirma no modal de segurança | `FilaController.cancelarAtendimento()` | Altera `Atendimento.status` para `Cancelado` e reordena os demais pacientes da `Fila`. | Exibe modal de confirmação e retorna ao estado inicial com feedback visual. | `RF06` |
