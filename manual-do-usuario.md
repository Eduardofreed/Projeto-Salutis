# ⛑️ Manual do Usuário — Salutis

> Plataforma digital de acolhimento, triagem e gestão de espera hospitalar.
> **Versão do protótipo:** https://pixel-perfect-playback-9267.lovable.app
> Dados 100% fictícios, apenas para demonstração.

## Sumário
1. [O que é o Salutis](#1-o-que-é-o-salutis)
2. [Antes de começar](#2-antes-de-começar)
3. [Manual do Paciente e Acompanhante](#3-manual-do-paciente-e-acompanhante)
4. [Manual do Enfermeiro de Triagem](#4-manual-do-enfermeiro-de-triagem)
5. [Manual do Coordenador](#5-manual-do-coordenador)
6. [Recepcionista: atendimento assistido](#6-recepcionista-atendimento-assistido)
7. [Acessibilidade](#7-acessibilidade)
8. [Privacidade e segurança (LGPD)](#8-privacidade-e-segurança-lgpd)
9. [Quando a internet cai](#9-quando-a-internet-cai)
10. [Perguntas frequentes](#10-perguntas-frequentes)
11. [Problemas comuns](#11-problemas-comuns)
12. [Glossário](#12-glossário)

---

## 1. O que é o Salutis
O Salutis organiza o início do atendimento no pronto atendimento: você faz o **check-in**, responde a uma **pré-triagem**, recebe uma **senha**, acompanha a **fila** e é avisado quando for **chamado**. A equipe de enfermagem faz a **classificação de risco** e a coordenação acompanha os **tempos de espera**.

| Perfil | Para que usa | Onde |
|---|---|---|
| Paciente / acompanhante | Check-in, senha, acompanhar fila | Totem ou celular (`/`) |
| Recepcionista | Ajudar quem não usa o app | Totem (atendimento assistido) |
| Enfermeiro | Classificar risco e controlar a fila | `/enfermeiro` |
| Coordenador | Acompanhar tempos e volumes | `/coordenador` |

> ⚠️ **Emergência:** o Salutis **não substitui** o atendimento de urgência. Se você ou alguém estiver com falta de ar intensa, dor forte no peito, desmaio ou sangramento grave, avise imediatamente a equipe ou ligue **192 (SAMU)**. Não espere pela fila do app.

## 2. Antes de começar
- **Paciente:** tenha em mãos o **CPF** ou a **carteirinha digital** do plano de saúde.
- **Equipe:** acesso com seu perfil (enfermeiro/coordenador).
- Funciona em **navegador de celular** e em **totem** de atendimento.
- A **barra azul no topo** de todas as telas tem os recursos de acessibilidade (veja a seção 7).

---

## 3. Manual do Paciente e Acompanhante
A jornada tem **3 telas**.

### Tela 1 · Identificação (check-in)
1. Leia a mensagem **"Bem-vindo ao Salutis"**.
2. Escolha como se identificar:
   - **Digite seu CPF** no campo; ou
   - **Escanear carteirinha digital**.
3. (Demonstração) o botão **"Preencher CPF de exemplo (idoso 65+)"** preenche um CPF fictício.
4. Toque em **"Confirmar Check-in e Avançar"**.

💡 Seu CPF aparece **mascarado** e seu **nome nunca aparece em painéis públicos**.
💡 Precisa de ajuda? Use **"Atendimento assistido no totem"** ou chame um recepcionista.

### Tela 2 · Pré-triagem e senha
1. Informe seus **sintomas** (ex.: dor, febre, tontura, falta de ar) conforme as opções da tela.
2. Confirme para **receber sua senha** (ex.: A-042).
3. Guarde sua senha: é ela que aparece nos painéis.

Pacientes **idosos (60+)** e outros grupos com prioridade legal são tratados automaticamente conforme a lei, **sem passar na frente de casos mais graves**.

### Tela 3 · Acompanhar a fila
- Veja sua **posição** e o **tempo aproximado** até o atendimento.
- Quando for chamado, você verá/ouvirá o **aviso de convocação** com o consultório.
- Se precisar **desistir** ou for encaminhado a outro serviço, use **cancelar ou remarcar senha**.

⏱️ O tempo é uma **estimativa**: pode mudar se chegarem casos mais graves.

### Se você piorar enquanto espera
Avise **imediatamente** a equipe. O enfermeiro pode **reclassificar** seu atendimento.

---

## 4. Manual do Enfermeiro de Triagem
Acesse **`/enfermeiro`** (Módulo 2 · Triagem e Controle de Fila).

### 4.1 Ler a fila
Cada linha mostra: **posição**, **senha**, **iniciais do paciente**, **sintomas**, **cor de risco** (quando classificado), etiqueta **60+** (prioridade legal) e **tempo de espera**.

### 4.2 Filtrar e buscar
- Filtros por cor: **Todas · Vermelho · Laranja · Amarelo · Verde · Azul**.
- A **busca** ignora maiúsculas/minúsculas e encontra também por **sintoma**.
- **Limpar lista** remove filtros.

### 4.3 Aferir e classificar
1. Clique no paciente na fila.
2. Na seção **"Aferição e classificação"**, registre os **sinais vitais** (PA, FC, FR, temperatura, SpO₂, glicemia, dor).
3. Confirme a **cor de risco** pelo Protocolo de Manchester.
4. A fila é **reordenada automaticamente**.

| Cor | Prioridade | Tempo-alvo |
|---|---|---|
| 🔴 Vermelho | Emergência | Imediato |
| 🟠 Laranja | Muito urgente | 10 min |
| 🟡 Amarelo | Urgente | 60 min |
| 🟢 Verde | Pouco urgente | 120 min |
| 🔵 Azul | Não urgente | 240 min |

### 4.4 Boas práticas
- A **decisão final** é sempre do enfermeiro. O sistema apoia, não diagnostica.
- Paciente com **sinal de alerta** (dor torácica, falta de ar grave) deve ser avaliado **imediatamente**.
- Reclassifique sempre que o quadro mudar e registre a justificativa.

### 4.5 Convocar
Chame o próximo da fila e informe o **consultório**; o paciente é avisado no painel e no celular.

---

## 5. Manual do Coordenador
Acesse **`/coordenador`** (Módulo 3 · Painel Analítico).

| Elemento | Como interpretar |
|---|---|
| **Aguardando agora** | Pacientes na fila neste momento |
| **Convocados hoje** | Pacientes já chamados no dia |
| **Modo contingência / Última sincronização** | Mostra se há dados pendentes de sincronização |
| **Alerta de remanejamento de equipe** | Aparece quando a espera média passa do tempo-alvo de uma cor, com sugestão de ação |
| **Tempo médio de espera por risco** | Média por cor comparada ao alvo (ex.: Laranja 12 min / alvo 10 min = acima da meta) |
| **Volume por gravidade** | Quantidade de pacientes em cada cor, sem dados pessoais |

Como usar: se uma cor ficar **acima do alvo**, siga a sugestão do alerta (ex.: deslocar um técnico para a triagem) antes de a unidade sobrecarregar.

---

## 6. Recepcionista: atendimento assistido
1. No totem, use **"Atendimento assistido no totem"**.
2. Pergunte o **CPF** ou peça a **carteirinha** e faça o check-in com o paciente.
3. Entregue/explique a senha e onde acompanhar a chamada.
4. Em caso de queixa grave, **avise a enfermagem imediatamente**.

---

## 7. Acessibilidade
A **barra azul no topo** oferece:

| Botão | Função |
|---|---|
| **A+ Aumentar fonte** | Amplia o texto |
| **Alto contraste** | Reforça cores para quem tem baixa visão |
| **Leitura por voz** | Lê a tela em voz alta |

O Salutis segue as diretrizes de acessibilidade WCAG e foi pensado para **pessoas idosas**: letras grandes, poucos toques e opção de ajuda no totem.

## 8. Privacidade e segurança (LGPD)
- Dados de saúde são **dados sensíveis** e são protegidos.
- **Painéis públicos** mostram só **senha e consultório**; nunca nome completo nem diagnóstico.
- Cada perfil só vê o que precisa (**controle de acesso**).
- As comunicações são **criptografadas**.
- Você pode pedir **acesso, correção ou exclusão** dos seus dados ao hospital.

## 9. Quando a internet cai
O sistema entra em **modo contingência**: a fila continua funcionando **localmente** e **sincroniza sozinho** quando a conexão voltar. O painel do coordenador mostra a **última sincronização** e os **eventos pendentes**. Se houver falha, a equipe segue o **fluxo manual** (senha de papel) até normalizar.

## 10. Perguntas frequentes
**Preciso de celular?** Não. Use o totem ou peça ajuda ao atendimento assistido.
**Por que quem chegou depois foi chamado antes?** A fila é por **gravidade** (cor) e depois prioridade legal e ordem de chegada.
**O tempo de espera é garantido?** Não, é aproximado.
**Posso sair e voltar?** Fale com a equipe antes; se sair sem avisar, sua senha pode ser tratada como não comparecimento.
**Meu nome aparece na TV?** Não, só a senha.
**Posso cancelar?** Sim, pelo cancelar/remarcar da tela 3 ou na recepção.

## 11. Problemas comuns
| Problema | O que fazer |
|---|---|
| CPF não é aceito | Confira os números; se persistir, use o atendimento assistido |
| Não consigo ler a tela | Use **A+** e **Alto contraste** ou **Leitura por voz** |
| Não recebo aviso de chamada | Fique atento ao painel e ao som; confirme sua senha na recepção |
| Tela travou no totem | Chame um recepcionista |
| Fila parece desatualizada | Verifique a conexão; o sistema sincroniza ao voltar a rede |
| Paciente piorou | Avise a equipe na hora |

## 12. Glossário
- **Check-in:** registro de chegada.
- **Pré-triagem:** perguntas iniciais sobre sintomas.
- **Triagem / classificação de risco:** avaliação feita pelo enfermeiro para definir a urgência.
- **Protocolo de Manchester:** método de 5 cores que define a prioridade clínica.
- **Prioridade legal:** preferência garantida por lei (ex.: idosos, gestantes, pessoas com deficiência).
- **Convocação:** chamada para o consultório.
- **Contingência:** funcionamento local quando não há internet.
- **LGPD:** Lei Geral de Proteção de Dados.

---
### Nota sobre esta versão
Este manual foi escrito com base no documento do projeto e nas páginas do protótipo. Passos das telas 2 e 3 do paciente e a tela de aferição de sinais vitais devem ser conferidos no protótipo e ajustados com prints antes da entrega final.
