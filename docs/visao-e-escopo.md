# Visão do Produto e Consolidação do Escopo Herdado
## 1. Identidade do Produto
- **Nome do Sistema:** Salutis — Plataforma Digital de Acolhimento, Triagem e Gestão de Espera Hospitalar.
- **Problema em uma frase:** Filas desorganizadas, morosidade no acolhimento inicial e falta de visibilidade sobre tempos de espera no pronto atendimento hospitalar geram sobrecarga na equipa clínica e desgaste excessivo aos pacientes, em especial idosos com mobilidade reduzida ou doenças crónicas.
- **Objetivo Central:** Desenvolver uma solução digital de autoatendimento e triagem integrada que reduza o tempo de espera no acolhimento, estruture a classificação de risco e ofereça previsibilidade da fila em tempo real.

---

## 2. Foco: Utilizador Principal e Tarefa Central
- **Utilizador Primário:** Paciente idoso (e/ou acompanhante familiar) em busca de atendimento de urgência.
- **Utilizadores Operacionais e Gestores:** Enfermeiros de triagem, rececionistas e coordenação hospitalar.
- **Tarefa Central do Protótipo:** Permitir que o paciente idoso realize o check-in simplificado, informe os seus sintomas iniciais de pré-triagem e acompanhe em tempo real a sua posição na fila até à convocação para a sala de consulta, em **até 3 telas**.

---

## 3. Fronteiras do Escopo

### Dentro do Escopo (Implementado no Protótipo)
- **RF01:** Check-in no pronto atendimento informando CPF (fictício/mascarado) ou lendo carteirinha digital.
- **RF02:** Registo de pré-triagem pelo paciente e aferição de sinais vitais/classificação de risco pela enfermagem (Protocolo de Manchester + prioridade legal por idade).
- **RF03:** Exibição da fila de espera atualizada em tempo real com posição estimada (`5°`) e tempo aproximado (`18 min`).
- **RF04:** Envio de alertas visuais e sonoros no telemóvel/totem e no painel público ao convocar o paciente (`Senha A047 -> Sala 03`).
- **RF05:** Painel analítico para o coordenador com tempo médio de espera e volume de pacientes por faixa de gravidade.
- **RF06:** Cancelamento (com confirmação em ação destrutiva) ou remarcação de senha em caso de desistência.

### Fora do Escopo (Explicitamente Excluído)
- Módulo completo de Prontuário Eletrónico do Paciente (PEP) e prescrição médica de medicamentos.
- Faturação hospitalar e auditoria de contas médicas.
- Integração financeira profunda com operadoras de planos de saúde.

---

## 4. Requisitos Não Funcionais e User Stories Rastreáveis

### Requisitos Não Funcionais
- **RNF01 (Usabilidade & Acessibilidade):** Conformidade com padrões WCAG, oferecendo botões funcionais de **Aumentar Fonte**, **Alto Contraste** e **Leitura por Voz**, além de opção de atendimento assistido.
- **RNF02 (Segurança & LGPD):** Dados sensíveis protegidos e anonimizados. Nenhum nome completo, CPF aberto ou diagnóstico é exibido no painel público (apenas código da senha `A047` e iniciais). Zero dados pessoais reais utilizados no repositório.
- **RNF03 (Desempenho & Disponibilidade):** Atualização da fila em menos de 3 segundos, resposta visual imediata em buscas, estados vazios (*empty states*) tratados e operação em modo contingência (buffer local).
- **RNF04 (Portabilidade):** Interface responsiva adaptada tanto para totens de autoatendimento quanto para navegadores web móveis.

### User Stories Atendidas
- **US01 (Paciente Idoso):** *"Como um paciente idoso em busca de atendimento de urgência, quero realizar o meu check-in rapidamente por meio de uma tela simples e de fácil leitura, para que eu não precise ficar em pé em filas extensas de receção e garanta a minha prioridade legal."*
- **US02 (Enfermeiro de Triagem):** *"Como enfermeiro do setor de triagem, quero registar os sintomas e a classificação de risco do paciente numa interface ágil, para que a fila de espera seja ordenada automaticamente conforme a gravidade clínica."*
- **US03 (Coordenador Hospitalar):** *"Como coordenador do pronto atendimento, quero acompanhar em tempo real o tempo médio de espera de cada classificação de risco, para que eu possa remanejar equipas de atendimento antes que ocorra sobrecarga na unidade."*
