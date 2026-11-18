[requisitos-não-funcionais.md](https://github.com/user-attachments/files/35054512/requisitos-nao-funcionais.md)

# Requisitos Não Funcionais

| ID | Categoria | Requisito | Métrica / Verificação | Pri. |
|---|---|---|---|---|
| RNF01 | Usabilidade | Interface do paciente com fonte ampliável, alto contraste, jornada de check-in em ≤ 5 toques | Teste com ≥ 5 idosos; ≥ 80% concluem sem ajuda | M |
| RNF02 | Acessibilidade | Conformidade WCAG 2.2 nível AA, leitor de tela (TalkBack/VoiceOver), alvos de toque ≥ 48 px | Auditoria axe/Lighthouse + teste manual | M |
| RNF03 | Segurança | Criptografia em trânsito (TLS 1.3) e em repouso (AES-256) | Scan SSL + revisão de infra | M |
| RNF04 | Segurança | Autenticação com senha forte/MFA para perfis operacionais; sessão expira por inatividade (ex.: 10 min no totem) | Teste de segurança | M |
| RNF05 | Segurança | Controle de acesso por perfil (RBAC), princípio do menor privilégio | Testes de autorização automatizados | M |
| RNF06 | Segurança | Proteção OWASP Top 10 / OWASP MASVS (mobile); dependências sem CVE crítica | SAST/DAST + Dependabot | M |
| RNF07 | LGPD | Dados de saúde tratados como sensíveis (art. 11); base legal registrada; minimização de dados | RIPD aprovado | M |
| RNF08 | LGPD | Painéis públicos sem nome completo, CPF ou diagnóstico | Teste de aceite RF19 | M |
| RNF09 | LGPD | Direitos do titular: acesso, correção, exclusão/anonimização, portabilidade | Fluxo implementado e testado | S |
| RNF10 | LGPD | Política de retenção definida e job de expurgo/anonimização | Revisão jurídica | S |
| RNF11 | Desempenho | Atualização do painel de fila < 3 s (p95) | Teste de carga | M |
| RNF12 | Desempenho | Resposta de API < 500 ms (p95) em carga nominal; app abre em < 3 s | k6/JMeter | M |
| RNF13 | Disponibilidade | ≥ 99,5% mensal no painel de fila (≈ 3,6 h/mês de indisponibilidade) | Monitoramento uptime | M |
| RNF14 | Resiliência | Modo contingência offline com sincronização sem perda/duplicidade | Teste de caos de rede | M |
| RNF15 | Escalabilidade | Suportar ≥ 10.000 usuários ativos e ≥ 500 check-ins/hora por unidade, com escala horizontal | Teste de carga | S |
| RNF16 | Recuperação | RPO ≤ 15 min, RTO ≤ 1 h; backups diários testados | Simulado de restauração | S |
| RNF17 | Portabilidade | App Android 9+ e iOS 15+; web responsivo em Chrome/Safari/Firefox; totem em navegador kiosk | Matriz de dispositivos | M |
| RNF18 | Compatibilidade | Funcionar em redes 3G/4G e Wi-Fi instável; payloads leves | Teste de rede limitada | S |
| RNF19 | Interoperabilidade | Expor API REST documentada (OpenAPI); preparar modelo para HL7 FHIR | Swagger publicado | S |
| RNF20 | Observabilidade | Logs estruturados sem dados pessoais, métricas, tracing e alertas | Dashboard + alertas | S |
| RNF21 | Auditabilidade | Registro imutável de acessos e alterações em dados clínicos, guardado conforme política | Revisão de logs | M |
| RNF22 | Manutenibilidade | Cobertura de testes ≥ 70% no código novo; lint e CI obrigatórios; código revisado por PR | Pipeline CI | M |
| RNF23 | Internacionalização | Interface em pt-BR; textos externalizados (preparado para en/es) | Revisão | C |
| RNF24 | Confiabilidade clínica | Sugestões automáticas sempre rotuladas como apoio; decisão final humana; versão do protocolo registrada | Revisão clínica | M |
| RNF25 | Usabilidade operacional | Registro de triagem concluído em ≤ 90 s por paciente | Teste cronometrado com enfermeiros | S |
| RNF26 | Custo | Infra do MVP dentro do orçamento definido em [Financeiro](financeiro.md) | Acompanhamento mensal | S |

## Restrições técnicas e legais
- LGPD (Lei 13.709/2018), Marco Civil da Internet (Lei 12.965/2014).
- Prioridade de atendimento: Lei 10.048/2000 e Estatuto da Pessoa Idosa (Lei 10.741/2003).
- Classificação de risco é atividade do enfermeiro (verificar normativa COFEN vigente).
- Possível enquadramento como *software como dispositivo médico* (ANVISA) caso o sistema passe a sugerir condutas clínicas — avaliar antes de operar em produção.

> Não sou advogado; estes itens precisam de validação jurídica antes de uso real.
