[riscos.md](https://github.com/user-attachments/files/35054518/riscos.md)

# Matriz de Riscos

Prob. e Impacto: 1 (baixo) a 5 (alto). Severidade = P × I.

| ID | Risco | P | I | Sev. | Mitigação | Responsável |
|---|---|:-:|:-:|:-:|---|---|
| R-01 | Idosos com dificuldade no app | 4 | 4 | 16 | Fonte grande, alto contraste, jornada curta, totem assistido, testes de usabilidade (RF06, RF42, RNF01) | PO |
| R-02 | Violação da LGPD / vazamento de dado de saúde | 3 | 5 | 15 | Anonimização em painel, RBAC, criptografia, RIPD, auditoria, pentest (RNF03–RNF10) | Dev líder |
| R-03 | Falha de rede/indisponibilidade | 4 | 4 | 16 | Modo contingência, buffer local, sincronização (RF41) | Dev |
| R-04 | Resistência da equipe de saúde | 3 | 4 | 12 | Envolver enfermeiros no design, treinamento, piloto | PO |
| R-05 | Estimativa de espera imprecisa gera frustração | 4 | 3 | 12 | Exibir como "aproximado", calibrar com dados reais, métrica de erro | Dev |
| R-06 | Classificação automática errada (risco clínico) | 2 | 5 | 10 | Decisão sempre do enfermeiro, sugestão rotulada, protocolo versionado, revisão clínica (RN02) | PO |
| R-07 | Estouro de escopo (GPS, chat, ambulância) | 5 | 3 | 15 | MoSCoW, MVP congelado, mudança via issue `requisito` | SM |
| R-08 | Estouro de orçamento/prazo | 3 | 4 | 12 | Burn rate por sprint, contingência 15%, cenário enxuto | SM |
| R-09 | **Chamada de ambulância pelo app em vez de 192**: atraso/falha de socorro, responsabilidade civil e integração com SAMU | 3 | 5 | 15 | Não substituir o 192; integrar/redirecionar ao SAMU, fase futura com parecer jurídico | PO |
| R-10 | Enquadramento regulatório (ANVISA / normas COFEN-CFM) | 3 | 4 | 12 | Consulta regulatória antes de produção; posicionar como apoio, não diagnóstico | PO |
| R-11 | Integração com sistemas legados do hospital | 4 | 3 | 12 | API aberta, FHIR, adaptadores por hospital | Dev |
| R-12 | Dependência de terceiros (mapas, SMS, nuvem) | 2 | 3 | 6 | Abstrações, alternativas, monitorar custo | Dev |
| R-13 | Equipe pequena (4 pessoas), ausência de QA/UX dedicado | 4 | 3 | 12 | Testes automatizados, revisão cruzada de PR, UX testado com usuários | SM |
| R-14 | Sobrecarga do sistema em pico/emergência em massa | 2 | 5 | 10 | Teste de carga, autoscaling, degradação graciosa | Dev |
| R-15 | Uso indevido de localização/chat (privacidade, assédio) | 2 | 4 | 8 | Consentimento, retenção mínima, moderação/auditoria | PO |

## Observação sobre RF37/RF38 (ambulância)
A ideia de "chamar ambulância sem ligar para o 192" é atraente, mas é o ponto mais delicado do projeto: o atendimento pré-hospitalar é regulado (SAMU), e falha de entrega ou atraso tem impacto direto na vida do paciente. Sugestão: no MVP, o app deve **exibir botão que liga para o 192** e, em fases futuras, integrar com a central de regulação, nunca criar um canal paralelo.
