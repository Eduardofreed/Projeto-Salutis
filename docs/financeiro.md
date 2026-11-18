[financeiro.md](https://github.com/user-attachments/files/35053553/financeiro.md)

# Levantamento Financeiro

> Todos os valores são **estimativas** com premissas explícitas, em R$ (câmbio de referência: US$ 1 ≈ R$ 5,50). Ajuste salários, câmbio e preços atuais antes de usar em proposta real.

## 1. Premissas
- Equipe: 4 desenvolvedores, 6 meses (12 sprints de 2 semanas).
- Salário médio bruto: **R$ 6.000/dev/mês** (perfil júnior/pleno).
- Encargos + benefícios (CLT): **+70%** sobre o salário.
- Produto mobile (Android + iOS) + web/totem + painel gerencial, ~10.000 usuários.
- Sem custos de espaço/equipamento (equipe já possui máquinas).
- Fora do orçamento: marketing, vendas, suporte 24h, certificações regulatórias completas.

## 2. Orçamento de desenvolvimento (6 meses)
| Item | Cálculo | Valor (R$) |
|---|---|---:|
| **Pessoal** (4 devs) | 4 × 6.000 × 1,7 × 6 | **244.800** |
| Cloud/infra (homologação + produção) | 2.500 × 6 | 15.000 |
| APIs de mapas/GPS (Fase 2) | estimativa de uso | 3.000 |
| SMS/WhatsApp (fallback de notificação) | estimativa | 3.000 |
| Ferramentas: Figma, GitHub Team, Sentry, domínio/certificados | ≈ 2.000 + 500 + 900 + 300 | 3.700 |
| Contas de loja (Apple US$ 99/ano + Google US$ 25 único) | ≈ | 700 |
| Consultoria jurídica LGPD/RIPD | pontual | 6.000 |
| Teste de invasão / auditoria de segurança | pontual | 8.000 |
| **Subtotal não-pessoal** | | **39.400** |
| Contingência (15% do não-pessoal) | | 5.910 |
| **TOTAL (6 meses)** | | **≈ R$ 290.110** |

Proporção: ~84% pessoal, ~16% demais custos. Consistente com a referência de **~R$ 290 mil em 6 meses**.

## 3. Cronograma de desembolso (aprox.)
| Mês | Pessoal | Outros | Total |
|---|---:|---:|---:|
| 1 | 40.800 | 6.000 | 46.800 |
| 2 | 40.800 | 4.500 | 45.300 |
| 3 | 40.800 | 5.500 | 46.300 |
| 4 | 40.800 | 6.500 | 47.300 |
| 5 | 40.800 | 9.500 | 50.300 |
| 6 | 40.800 | 13.310 | 54.110 |
| **Total** | **244.800** | **45.310** | **290.110** |

## 4. Custo do protótipo acadêmico
Usando planos gratuitos (Firebase/Supabase free, Vercel, GitHub Free, Figma Education, Expo) o custo de ferramentas tende a **R$ 0 a R$ 200**; o custo real é o tempo da equipe. Recomendado para a disciplina.

## 5. Custo operacional pós-lançamento (por mês, ~10 mil usuários)
| Item | R$/mês |
|---|---:|
| Cloud (API, banco, filas, tempo real, backups) | 3.500 – 5.000 |
| Mapas/GPS | 500 – 1.500 |
| SMS/WhatsApp | 800 – 2.000 |
| Monitoramento, logs, e-mail transacional | 600 |
| Seguro/jurídico/DPO terceirizado | 1.500 – 3.000 |
| **Infra e serviços** | **≈ 7.000 – 12.000** |
| Manutenção (2 devs, mesma premissa de custo) | ≈ 20.400 |
| **Total operacional** | **≈ 27.000 – 33.000** |

## 6. Modelo de receita (hipóteses a validar)
| Modelo | Descrição | Faixa hipotética |
|---|---|---|
| **SaaS B2B por unidade** (recomendado) | Mensalidade por hospital/UPA | R$ 8.000 – 15.000/mês |
| Setup/implantação | Integração, treinamento, totens | R$ 20.000 – 50.000 por unidade |
| Licença por volume | Valor por atendimento processado | R$ 0,50 – 2,00 |
| Setor público | Contrato/licitação | depende do edital |

**Ponto de equilíbrio (hipótese):** custo operacional ≈ R$ 30 mil/mês ÷ R$ 10 mil por unidade ⇒ **≈ 3 hospitais** pagantes. Recuperação do investimento de R$ 290 mil: ~12–24 meses após 3–5 unidades, dependendo de ciclo de venda (hospitais costumam levar 6–12 meses).

## 7. Cenários
| Cenário | Equipe | Prazo | Custo estimado |
|---|---|---|---:|
| MVP enxuto (check-in, triagem, fila, chamada, painel) | 4 devs | 4 meses | ≈ R$ 200 mil |
| **Base (este documento)** | 4 devs | 6 meses | ≈ R$ 290 mil |
| Completo (+GPS, chat, ambulância, FHIR, planos) | 6 pessoas (inclui QA/UX/DevOps) | 9–12 meses | R$ 650 mil – 1,1 mi |

## 7.1 Fatores que mais mexem no custo
1. **Ambulância/emergência** (RF37–38): exige integração com SAMU, alta disponibilidade e responsabilidade legal — maior risco e maior custo.
2. **Integração com sistemas hospitalares** (FHIR/HL7): cada hospital tem um legado diferente.
3. **Regulatório** (ANVISA, LGPD, jurídico): pode adicionar R$ 30–100 mil se o produto for tratado como dispositivo médico.
4. **Disponibilidade 99,5%+ com contingência:** infra redundante e testes de caos.

## 8. Controle financeiro
- Revisar burn rate a cada sprint (planejado × realizado).
- Registrar custos como issues/labels `custo` e acompanhar no GitHub Projects.
- Gatilho: se custo realizado > 10% do planejado, abrir issue de revisão de escopo.
