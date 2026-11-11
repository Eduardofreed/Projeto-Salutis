<img width="2400" height="1792" alt="Salutis-logo" src="https://github.com/user-attachments/assets/9ee6bf90-d270-4823-8e98-b2afe484faa9" />

# ⛑️ Salutis

> Plataforma digital de acolhimento, triagem e gestão de espera hospitalar.

[![demo](https://img.shields.io/badge/demo-Lovable-ff69b4)](https://pixel-perfect-playback-9267.lovable.app) ![status](https://img.shields.io/badge/status-planejamento-yellow) ![metodologia](https://img.shields.io/badge/metodologia-Scrum-blue) ![licença](https://img.shields.io/badge/licen%C3%A7a-MIT-green)

## Sobre
Filas desorganizadas, lentidão no acolhimento e falta de visibilidade do tempo de espera sobrecarregam a equipe de saúde e desgastam pacientes, principalmente idosos e pessoas com doenças crônicas. O Salutis oferece **check-in digital, pré-triagem, classificação de risco, fila em tempo real e notificação de chamada**.

## 🚀 Protótipo
**Demo navegável:** https://pixel-perfect-playback-9267.lovable.app

| Módulo | Link |
|---|---|
| Paciente (check-in, pré-triagem, fila) | [https://pixel-perfect-playback-9267.lovable.app/](https://pixel-perfect-playback-9267.lovable.app/) |
| Enfermeiro (classificação de risco) | [/enfermeiro](https://pixel-perfect-playback-9267.lovable.app/enfermeiro) |
| Coordenador (painel analítico) | [/coordenador](https://pixel-perfect-playback-9267.lovable.app/coordenador) |
| Arquitetura e documentação | [/arquitetura](https://pixel-perfect-playback-9267.lovable.app/arquitetura) |

## Documentação
| #   | Documento                                                         | Conteúdo                                                   |
| --- | ----------------------------------------------------------------- | ---------------------------------------------------------- |
| 01  | [Visão e Escopo](docs/01-visao-e-escopo.md)                       | Termo de abertura, personas, escopo, premissas, restrições |
| 02  | [Requisitos Funcionais](docs/02-requisitos-funcionais.md)         | RF por módulo, prioridade MoSCoW, critérios de aceite      |
| 03  | [Requisitos Não Funcionais](docs/03-requisitos-nao-funcionais.md) | Desempenho, segurança, LGPD, acessibilidade etc.           |
| 04  | [Regras de Negócio](docs/04-regras-de-negocio.md)                 | Manchester, prioridade legal, regras de fila               |
| 05  | [User Stories](docs/05-user-stories.md)                           | Histórias com critérios de aceite (Gherkin)                |
| 06  | [Financeiro](docs/06-financeiro.md)                               | Custos, orçamento, cenários, modelo de receita             |
| 07  | [Riscos](docs/07-riscos.md)                                       | Matriz de riscos e mitigações                              |
| 08  | [Arquitetura e Stack](docs/08-arquitetura-e-stack.md)             | Visão técnica sugerida e integrações                       |
| 09  | [Roadmap](docs/09-roadmap.md)                                     | Releases, sprints e Definition of Done                     |
| 10  | [Protótipo (Lovable)](docs/10-prototipo-lovable.md)               | Link, páginas, cobertura de requisitos, arquitetura MVC    |
| —   | [Backlog](docs/backlog.md)                                        | Épicos e issues prontos para o GitHub                      |

## Equipe
| Papel | Pessoa |
|---|---|
| Product Owner | Gabriel |
| Scrum Master | Eduardo |
| Developers | Gabriel, Eduardo, Renan, Erick |

## Como usar este repositório
1. Crie o repositório no GitHub e envie estes arquivos.
2. Instale o [GitHub CLI](https://cli.github.com/) e rode `bash scripts/setup-github.sh` para criar labels, milestones e issues.
3. Crie um **GitHub Project** (Board) com as colunas: `A Fazer`, `Fazendo`, `Em Revisão`, `Feito`.
4. Veja o [CONTRIBUTING](CONTRIBUTING.md) para fluxo de branches e PRs.

> ⚠️ Projeto acadêmico (protótipo). Não usar com dados reais de pacientes sem avaliação jurídica e regulatória (ver [Riscos](docs/07-riscos.md)).
