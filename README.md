<img width="2400" height="1792" alt="Salutis-logo" src="https://github.com/user-attachments/assets/9ee6bf90-d270-4823-8e98-b2afe484faa9" />

#  Salutis

> Plataforma digital de acolhimento, triagem e gestão de espera hospitalar.

[![demo](https://img.shields.io/badge/demo-Lovable-ff69b4)](https://pixel-perfect-playback-9267.lovable.app) ![status](https://img.shields.io/badge/status-protótipo%20funcional-brightgreen) ![metodologia](https://img.shields.io/badge/metodologia-Scrum-blue) ![licença](https://img.shields.io/badge/licen%C3%A7a-MIT-green)

## Sobre
Filas desorganizadas, lentidão no acolhimento e falta de visibilidade do tempo de espera sobrecarregam a equipe de saúde e desgastam pacientes, principalmente idosos e pessoas com doenças crônicas. O Salutis oferece **check-in digital, pré-triagem, classificação de risco, fila em tempo real e notificação de chamada**.

##  Protótipo
**Demo navegável:** https://pixel-perfect-playback-9267.lovable.app

| Módulo | Link Direto |
|---|---|
| Paciente (check-in, pré-triagem, fila em 3 telas) | [https://pixel-perfect-playback-9267.lovable.app/](https://pixel-perfect-playback-9267.lovable.app/) |
| Enfermeiro (classificação de risco) | [/enfermeiro](https://pixel-perfect-playback-9267.lovable.app/enfermeiro) |
| Coordenador (painel analítico) | [/coordenador](https://pixel-perfect-playback-9267.lovable.app/coordenador) |
| Arquitetura e documentação | [/arquitetura](https://pixel-perfect-playback-9267.lovable.app/arquitetura) |

##  Documentação e Entregáveis (Acesso Direto)
A estrutura física do repositório está dividida nas pastas `/docs`, `/manuais`, `/pitch` e `/prototipo`, com acesso direto abaixo:

| # | Documento | Pasta / Caminho | Conteúdo |
| --- | --- | --- | --- |
| 01 | [Visão e Escopo](docs/visao-e-escopo.md) | `/docs` | Termo de abertura, personas, escopo e consolidação das 3 telas |
| 02 | [Requisitos Funcionais](docs/requisitos-funcionais.md) | `/docs` | RF01–RF06 por módulo, prioridade MoSCoW e critérios de aceite |
| 03 | [Requisitos Não Funcionais](docs/requisitos-nao-funcionais.md) | `/docs` | Desempenho (< 3s), segurança, LGPD e acessibilidade (WCAG) |
| 04 | [Regras de Negócio](docs/regras-de-negocio.md) | `/docs` | Protocolo de Manchester, prioridade legal (idosos) e fila |
| 05 | [User Stories](docs/user-stories.md) | `/docs` | Histórias (Paciente Idoso, Enfermeiro, Coordenador) em Gherkin |
| 06 | [Financeiro e Viabilidade](docs/financeiro.md) | `/docs` | Custos reais (equipe, energia, nuvem, marketing) e prazos |
| 07 | [Riscos e Manutenção](docs/riscos.md) | `/docs` | Matriz de riscos, mitigações e ciclo de manutenção |
| 08 | [Arquitetura MVC e Stack](docs/arquitetura-e-stack.md) | `/docs` | Justificativa de Monolito Modular, 4 camadas e mapeamento MVC |
| 09 | [Roadmap e Produção](docs/roadmap.md) | `/docs` | Sprints, sequência de construção e rastreabilidade de commits |
| 10 | [Manual do Usuário](manuais/manual-usuario.md) | `/manuais` | Guia passo a passo das telas sem jargão técnico |
| 11 | [Manual Técnico](manuais/manual-tecnico.md) | `/manuais` | Instalação local, estrutura de código e regras de Git Flow |
| 12 | [Pitch e Canvas](pitch/Pitch.md) | `/pitch` | Roteiro de defesa, diferencial competitivo e [Canvas](pitch/Canvas.md) |
| 13 | [Protótipo e Exportações](prototipo/prototipo-lovable.md) | `/prototipo` | Link público, roteiro de teste e capturas de tela estáticas |

## 👥 Equipe
| Papel | Pessoa |
|---|---|
| Product Owner | Gabriel |
| Scrum Master | Eduardo |
| Developers | Gabriel, Eduardo, Renan, Erick |

## 💻 Como Executar o Protótipo Localmente
Caso deseje rodar o código-fonte em sua máquina além da versão hospedada:

```bash
# 1. Clone o repositório público
git clone [https://github.com/Eduardofreed/Projeto-Salutis.git](https://github.com/Eduardofreed/Projeto-Salutis.git)
# 2. Acesse a pasta do projeto
cd Projeto-Salutis

# 3. Instale as dependências
npm install

# 4. Inicie o servidor de desenvolvimento
npm run dev
