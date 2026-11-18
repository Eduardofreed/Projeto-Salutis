[protótipo.md](https://github.com/user-attachments/files/35054411/prototipo.md)

# Protótipo navegável (Lovable)

🔗 **Protótipo publicado:** https://pixel-perfect-playback-9267.lovable.app
✏️ **Projeto no Lovable (edição):** https://lovable.dev/projects/lovp_2pv5efkknf9wptzqzmtcszj205

> Dados 100% fictícios, apenas para demonstração. Nenhum dado real de paciente deve ser inserido.

## Páginas
| Módulo | Rota | URL | Persona |
|---|---|---|---|
| 1 · Jornada do Paciente (3 telas: Identificação → Pré-triagem e senha → Acompanhar fila) | `/` | https://pixel-perfect-playback-9267.lovable.app/ | Paciente/acompanhante |
| 2 · Triagem e Controle de Fila | `/enfermeiro` | https://pixel-perfect-playback-9267.lovable.app/enfermeiro | Enfermeiro |
| 3 · Painel Analítico | `/coordenador` | https://pixel-perfect-playback-9267.lovable.app/coordenador | Coordenador |
| 4 · Arquitetura e Documentação (para a banca) | `/arquitetura` | https://pixel-perfect-playback-9267.lovable.app/arquitetura | Banca/equipe |

Em todas as páginas há uma barra de acessibilidade: **aumentar fonte, alto contraste e leitura por voz**.

## Decisão de design: de 6 para 3 telas
As 6 telas previstas na Aula 3 foram consolidadas em 3 na jornada do paciente (meta de usabilidade: no máximo 3 telas para a tarefa principal):
1. **Identificação** (entrada + check-in por CPF/carteirinha)
2. **Pré-triagem e senha**
3. **Acompanhar fila** (posição, convocação, cancelar/remarcar)

O indicador gerencial ficou no painel do coordenador.

## Cobertura dos requisitos pelo protótipo
Legenda: ✅ demonstrado · 🟡 parcial · ⬜ ainda não demonstrado

| Requisito | Status | Onde / observação |
|---|:-:|---|
| RF01 Check-in por CPF/carteirinha | ✅ | Tela 1: campo CPF, "preencher CPF de exemplo", "escanear carteirinha digital" |
| RF05/RF42 Atendimento assistido | ✅ | Opção "Atendimento assistido no totem" |
| RF06 Totem simplificado | ✅ | Módulo 1 · Totem de autoatendimento |
| RF08 Pré-triagem de sintomas | ✅ | Tela 2 |
| RF09 Sinais vitais | 🟡 | `/enfermeiro`, seção "Aferição e classificação" (validar campos) |
| RF10 Classificação Manchester (5 cores) | ✅ | Filtros Vermelho/Laranja/Amarelo/Verde/Azul |
| RF11 Prioridade legal por idade | ✅ | Etiqueta "60+" na fila; faixa 80+ incluída (manutenção adaptativa) |
| RF16/RF17 Fila e ordenação | ✅ | Fila ordenada por risco com tempo estimado e busca por sintoma |
| RF18 Cancelar/remarcar senha | ✅ | Tela 3 |
| RF20/RF24 Convocação | 🟡 | Tela 3 (convocação); alerta sonoro/push real não implementado |
| RF28 Painel analítico | ✅ | Tempo médio por risco e volume por gravidade |
| RF29 Alerta de sobrecarga | ✅ | "Alerta de remanejamento de equipe" |
| RF41 Modo contingência | 🟡 | Indicador de sincronização local (simulado) |
| RF43 Acessibilidade | ✅ | Fonte, contraste, leitura por voz |
| RNF08/RN11 Anonimização | ✅ | CPF mascarado; nome nunca em painel público; iniciais na fila interna |
| RN03 Metas por cor | ✅ | Alvos 0/10/60/120/240 min no painel do coordenador |
| RF03 Login e perfis (RBAC) | ⬜ | Navegação livre entre perfis |
| RF04 Consentimento LGPD | ⬜ | Sem termo/consentimento |
| RF19 Painel público (TV) | ⬜ | Não há tela dedicada |
| RF13/RF14 Reclassificação e sinais de alerta | ⬜ | — |
| RF30 Relatórios · RF33 Auditoria | ⬜ | — |
| RF34–RF38 GPS, chat, ambulância | ⬜ | Fase 2+ |

> Observação: esta análise foi feita pelo conteúdo visível das páginas publicadas, sem acesso ao código-fonte nem testes interativos. Valide cada item no protótipo antes de apresentar.

## Arquitetura do protótipo
Monolito modular em 4 camadas, com MVC:

| Camada | Pasta | Responsabilidade |
|---|---|---|
| 1 · Apresentação | `/src/presentation/views` | Telas, só exibem e chamam controllers |
| 2 · Aplicação | `/src/application/controllers` | Casos de uso: `realizarCheckIn`, `registrarPreTriagem`, `classificarRiscoEnfermagem`, `convocarPaciente`, `cancelarOuRemarcarSenha`, `filtrarFila` |
| 3 · Domínio | `/src/domain/models` | `Paciente`, `Triagem`, `Atendimento`, `Fila` — regras puras e testáveis |
| 4 · Infraestrutura | `/src/infrastructure/mocks` | Dados fictícios e fila inicial |

### Mapeamento MVC
| Passo | Regras alteradas | View | Ação |
|---|---|---|---|
| Tela 1 | Paciente (CPF mascarado) + Atendimento (Check-in, senha) | `PacienteJornadaView` · passo 1 | `CheckInController.realizarCheckIn` |
| Tela 2 | Triagem + Atendimento (Na fila) | `PacienteJornadaView` · passo 2 | `PreTriagemController.registrarPreTriagem` |
| Tela 3 | Fila + Atendimento (Convocado/Cancelado) | `PacienteJornadaView` · passo 3 | `ConvocacaoController.convocarPaciente` · `SenhaController.cancelarOuRemarcarSenha` |

## Ciclo de vida da manutenção (registrado no protótipo)
- **Corretiva:** busca da fila ignora maiúsculas e passa a buscar por sintoma (`filtrarFila`).
- **Adaptativa:** inclusão da faixa 80+ como prioridade legal (`faixaPorIdade` / `temPrioridadeLegal`).
- **Perfectiva:** consolidação de 6 para 3 telas.
- **Preventiva:** regras de ordenação/tempo isoladas na camada `domain`, com testes automatizados.

## Estrutura de repositório sugerida
```
salutis/
├── docs/        requisitos funcionais, de qualidade e user stories
├── manuais/     manual do paciente, do enfermeiro e do coordenador
├── pitch/       apresentação e roteiro para a banca
└── prototipo/   protótipo navegável (React + TypeScript)
```
Para versionar o código do protótipo: no Lovable, conecte o projeto ao GitHub (integração nativa) e traga o código para `prototipo/` (ou use `git subtree`/submódulo).
