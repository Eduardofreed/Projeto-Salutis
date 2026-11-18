[requisitos-funcionais.md](https://github.com/user-attachments/files/35054470/requisitos-funcionais.md)

# Requisitos Funcionais

**Legenda MoSCoW:** **M** = Must (MVP) · **S** = Should · **C** = Could · **W** = Won't agora (fase futura)
**Origem:** DOC = documento do grupo · NOVO = levantamento complementar

## Módulo A — Identificação e Cadastro
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF01 | Check-in no pronto atendimento informando CPF ou escaneando carteirinha digital (QR/código) | M | DOC |
| RF02 | Cadastro de paciente com CPF, nome, data de nascimento, celular, e-mail e dados da carteirinha do plano | M | DOC |
| RF03 | Autenticação por perfil (paciente, acompanhante, recepcionista, enfermeiro, gestor, admin) | M | NOVO |
| RF04 | Registro e revogação do consentimento LGPD (termo, versão, data/hora) | M | NOVO |
| RF05 | Modo assistido: acompanhante/recepcionista faz check-in em nome do paciente | M | NOVO |
| RF06 | Check-in por totem com interface simplificada (fonte grande, poucos toques) | M | DOC |
| RF07 | Check-in sem CPF (paciente inconsciente/estrangeiro) com identificação provisória | S | NOVO |

## Módulo B — Triagem e Classificação
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF08 | Pré-triagem digital: questionário guiado de sintomas (queixa principal, intensidade, duração, comorbidades) | M | DOC |
| RF09 | Enfermeiro registra sinais vitais (PA, FC, FR, temperatura, SpO₂, glicemia, dor 0–10) | M | DOC |
| RF10 | Classificação de risco no protocolo Manchester (5 cores) definida/confirmada pelo enfermeiro | M | DOC |
| RF11 | Aplicação automática de prioridade legal por idade (≥ 60 anos; ≥ 80 com preferência) e demais grupos prioritários (gestantes, PcD, lactantes) | M | DOC |
| RF12 | Sistema sugere classificação a partir da pré-triagem, **mas nunca a define sem confirmação do enfermeiro** | S | NOVO |
| RF13 | Reclassificação do paciente durante a espera (piora do quadro) com justificativa | M | NOVO |
| RF14 | Alerta de sinais de alerta (ex.: dor torácica, dispneia grave) com escalonamento imediato à equipe | M | NOVO |
| RF15 | Gestor/unidade define quais enfermeiros estão habilitados a classificar | S | DOC |

## Módulo C — Fila e Atendimento
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF16 | Fila de espera em tempo real com posição estimada e tempo aproximado até o atendimento | M | DOC |
| RF17 | Ordenação automática por cor de risco, prioridade legal e ordem de chegada | M | DOC |
| RF18 | Cancelamento ou remarcação de senha (desistência/encaminhamento externo) | M | DOC |
| RF19 | Painel público (TV) com senhas anonimizadas (senha/iniciais, nunca diagnóstico) | M | DOC |
| RF20 | Equipe chama o próximo paciente e atribui consultório | M | DOC |
| RF21 | Registro de não comparecimento (paciente chamado e ausente) com regra de retorno à fila | S | NOVO |
| RF22 | Fluxo de saída: alta, internação, transferência, evasão | S | NOVO |
| RF23 | Histórico de atendimentos do paciente no próprio app | C | NOVO |

## Módulo D — Notificações
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF24 | Alertas sonoros e visuais (painel público e celular) ao chamar o paciente | M | DOC |
| RF25 | Push notification de mudança relevante de posição ("faltam 3 pacientes") | S | NOVO |
| RF26 | Fallback por SMS/WhatsApp/e-mail quando push falhar | C | NOVO |
| RF27 | Paciente configura preferências de notificação | C | NOVO |

## Módulo E — Gestão e Analytics
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF28 | Painel analítico: tempo médio de espera e volume por faixa de gravidade, em tempo real | M | DOC |
| RF29 | Alertas de sobrecarga (ex.: tempo médio de laranja acima da meta) | S | DOC (US03) |
| RF30 | Relatórios exportáveis (CSV/PDF) por período, turno e cor | S | NOVO |
| RF31 | Configuração da unidade: consultórios, metas de tempo por cor, horários | S | NOVO |
| RF32 | Gestão de usuários e perfis (CRUD, ativação, desativação) | M | NOVO |
| RF33 | Trilha de auditoria (quem viu/alterou o quê e quando) | M | NOVO |

## Módulo F — Localização e Comunicação (Fase 2)
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF34 | GPS/localização em tempo real: distância e tempo de deslocamento até a unidade, mediante consentimento | C | DOC |
| RF35 | Chat paciente ↔ equipe de saúde (texto), com retenção e auditoria | C | DOC |
| RF36 | Entrada na fila de emergência pelo app (pré-check-in remoto) | C | DOC |
| RF37 | Solicitação de ambulância pelo app — **integrada ao SAMU 192, não substitutiva** | W | DOC |
| RF38 | Acompanhamento da ambulância no mapa e envio prévio de dados ao hospital | W | DOC |
| RF39 | Integração com operadoras para validar carteirinha | W | NOVO |
| RF40 | Integração FHIR/HL7 com sistemas do hospital (ADT) | W | NOVO |

## Módulo G — Operação e Resiliência
| ID | Requisito | Pri. | Origem |
|---|---|---|---|
| RF41 | Modo contingência: fila local em buffer sem rede e sincronização automática | M | DOC (risco 3) |
| RF42 | Alternativa de atendimento assistido/totem para quem não usa o app | M | DOC (risco 1) |
| RF43 | Suporte a idioma pt-BR com opção de acessibilidade (fonte, contraste, leitor de tela) | M | DOC |

## Critérios de aceite (principais)
**RF01 Check-in**
- Dado um CPF válido cadastrado, quando o paciente confirma, então recebe senha e posição na fila em ≤ 3 s.
- Dado CPF inválido, então vê mensagem clara e opção de ajuda assistida.

**RF11 Prioridade legal**
- Dado paciente ≥ 60 anos, então a fila aplica prioridade legal sem intervenção manual.
- Dado dois pacientes da mesma cor, o idoso é chamado primeiro; um paciente vermelho nunca é ultrapassado por prioridade legal.

**RF19 Painel público**
- Nenhum nome completo, CPF ou diagnóstico é exibido; apenas senha e consultório.

**RF41 Contingência**
- Dado queda de rede, o totem continua emitindo senhas localmente e sincroniza em ≤ 60 s após o retorno, sem duplicidade.

## Matriz de rastreabilidade (resumo)
| Objetivo | RFs |
|---|---|
| O1 acolhimento rápido | RF01, RF02, RF05, RF06 |
| O2 classificação de risco | RF08–RF14 |
| O3 previsibilidade | RF16, RF17, RF24, RF25 |
| O4 redução de abandono | RF18, RF21, RF24–RF26 |
| O5 acessibilidade | RF06, RF42, RF43 |
