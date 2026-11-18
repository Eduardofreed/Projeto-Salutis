[road-map.md](https://github.com/user-attachments/files/35054544/road-map.md)

# Roadmap

| Release | Meses | Conteúdo | Milestone |
|---|---|---|---|
| **R0 — Fundação** | 1 | Discovery, protótipo de telas, arquitetura, CI/CD, auth/RBAC | `M0 Fundação` |
| **R1 — MVP** | 2–4 | Check-in, pré-triagem, triagem, fila, chamada, painel público, painel gestor, contingência | `M1 MVP` |
| **R2 — Piloto** | 5 | Notificações completas, relatórios, acessibilidade, testes de carga, segurança, piloto | `M2 Piloto` |
| **R3 — Expansão** | 6+ | GPS, chat, integração planos/FHIR | `M3 Expansão` |
| **R4 — Emergência** | futuro | Integração SAMU/ambulância (após parecer jurídico) | `M4 Emergência` |

## Sprints (2 semanas)
| Sprint | Entregas |
|---|---|
| 1 | Setup repo, CI, design system acessível, protótipo navegável (Aula 3, ✅ publicado) |
| 2 | Auth, perfis, consentimento LGPD (US05, US13) |
| 3 | Check-in totem/app + cadastro (US01, US04) |
| 4 | Pré-triagem + registro de triagem (US06, US02) |
| 5 | Fila e regras Manchester/prioridade legal (US08, RN03–RN05) |
| 6 | Chamada, painel público anonimizado, cancelar/remarcar (US09, US10) |
| 7 | Notificações push/sonoras (US11) |
| 8 | Painel gestor e alertas (US03) |
| 9 | Modo contingência (US17) |
| 10 | Reclassificação, auditoria, relatórios (US07, US12) |
| 11 | Acessibilidade, carga, segurança, pentest (US18) |
| 12 | Piloto, correções, documentação, retrospectiva final |

## Telas da Aula 3
Protótipo publicado em https://pixel-perfect-playback-9267.lovable.app (ver [10 · Protótipo](prot%C3%B3tipo.md)). As 6 telas planejadas foram consolidadas em 3 na jornada do paciente (Identificação · Pré-triagem e senha · Fila e convocação), mais os painéis do enfermeiro e do coordenador.

**Pendente de prototipar:** painel público (TV), login/consentimento LGPD, reclassificação.

## Definition of Done
Ver [CONTRIBUTING](../CONTRIBUTING.md).

## KPIs de produto
Tempo de check-in · tempo até classificação · % dentro da meta por cor · erro da estimativa · taxa de abandono · NPS de pacientes/equipe · uptime.
