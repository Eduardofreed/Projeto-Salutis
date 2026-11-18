[user-stories.md](https://github.com/user-attachments/files/35054570/user-stories.md)

# User Stories

Pontuação em *story points* (Fibonacci). Épicos: **E1** Identificação · **E2** Triagem · **E3** Fila · **E4** Notificações · **E5** Gestão · **E6** Localização/Comunicação · **E7** Plataforma/Qualidade.

## E1 — Identificação
### US01 · Check-in do paciente idoso (RF01, RF06, RNF01) — 8 pts · M
**Como** paciente idoso, **quero** fazer check-in por uma tela simples e legível, **para que** eu não precise ficar em pé em filas e garanta minha prioridade legal.
```gherkin
Cenário: Check-in no totem
  Dado que estou no totem com fonte ampliada
  Quando informo meu CPF e confirmo
  Então recebo minha senha e vejo minha posição na fila
  E o fluxo exige no máximo 5 toques
```
### US04 · Check-in assistido (RF05, RF42) — 5 pts · M
**Como** recepcionista, **quero** fazer o check-in em nome do paciente, **para que** quem não usa o app seja atendido sem atrito.
### US05 · Cadastro e consentimento (RF02, RF04) — 5 pts · M
**Como** paciente, **quero** me cadastrar e aceitar/revogar o uso dos meus dados, **para que** eu tenha controle sobre minha privacidade.
```gherkin
Cenário: Revogar consentimento
  Dado que estou logado
  Quando revogo o consentimento de localização
  Então o app para de coletar GPS imediatamente
```

## E2 — Triagem
### US02 · Registro de triagem (RF08–RF11) — 8 pts · M
**Como** enfermeiro de triagem, **quero** registrar sintomas, sinais vitais e classificação em uma interface ágil, **para que** a fila seja ordenada automaticamente pela gravidade.
```gherkin
Cenário: Classificar paciente
  Dado um paciente com pré-triagem concluída
  Quando registro sinais vitais e confirmo a cor amarela
  Então o paciente entra na fila na posição correta
  E o evento é gravado na trilha de auditoria
```
### US06 · Pré-triagem pelo paciente (RF08) — 5 pts · M
**Como** paciente, **quero** responder perguntas guiadas sobre meus sintomas, **para que** a triagem presencial seja mais rápida.
### US07 · Reclassificação (RF13, RF14) — 5 pts · M
**Como** enfermeiro, **quero** reclassificar um paciente que piorou na espera, **para que** ele seja atendido a tempo.

## E3 — Fila
### US08 · Acompanhar a fila (RF16, RF17) — 8 pts · M
**Como** paciente/acompanhante, **quero** ver minha posição e tempo aproximado, **para que** eu saiba quanto falta.
### US09 · Chamar paciente (RF20) — 3 pts · M
**Como** médico/enfermeiro, **quero** chamar o próximo paciente para um consultório, **para que** o fluxo seja contínuo.
### US10 · Cancelar/remarcar (RF18) — 3 pts · M
**Como** paciente, **quero** cancelar ou remarcar minha senha, **para que** a fila reflita a realidade.

## E4 — Notificações
### US11 · Ser avisado da chamada (RF24, RF25) — 5 pts · M
**Como** acompanhante, **quero** receber alerta no celular quando o paciente for chamado, **para que** eu possa aguardar com conforto.

## E5 — Gestão
### US03 · Painel do coordenador (RF28, RF29) — 8 pts · M
**Como** coordenador, **quero** acompanhar o tempo médio de espera por classificação, **para que** eu remaneje equipes antes da sobrecarga.
### US12 · Relatórios (RF30) — 5 pts · S
**Como** diretor, **quero** exportar indicadores por período, **para que** eu avalie eficiência e preste contas.
### US13 · Gestão de usuários (RF32, RF33) — 5 pts · M
**Como** administrador, **quero** gerenciar perfis e ver a trilha de auditoria, **para que** o acesso seja seguro.

## E6 — Localização e Comunicação (Fase 2)
### US14 · Distância até o hospital (RF34) — 5 pts · C
**Como** paciente a caminho, **quero** compartilhar minha localização, **para que** a equipe saiba quando chego.
### US15 · Chat com a equipe (RF35) — 8 pts · C
**Como** paciente, **quero** conversar com a equipe, **para que** eu tire dúvidas sem voltar ao balcão.
### US16 · Solicitar ambulância (RF37, RF38) — 13 pts · W
**Como** pessoa em emergência, **quero** acionar socorro pelo app, **para que** a ajuda seja enviada sem ligar. *(integrar ao 192/SAMU — ver Riscos R-09)*

## E7 — Plataforma
### US17 · Modo contingência (RF41, RNF14) — 8 pts · M
**Como** equipe do pronto atendimento, **quero** continuar operando sem rede, **para que** uma queda de internet não pare o atendimento.
### US18 · Acessibilidade (RF43, RNF02) — 5 pts · M
**Como** paciente com baixa visão, **quero** leitor de tela e alto contraste, **para que** eu use o app com autonomia.
