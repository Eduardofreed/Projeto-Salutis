[regras-de-Negocios.md](https://github.com/user-attachments/files/35054450/regras-de-Negocios.md)

# Regras de Negócio

| ID | Regra |
|---|---|
| RN01 | Todo paciente recebe uma senha única por atendimento, vinculada ao check-in. |
| RN02 | A classificação de risco só é efetivada após **confirmação do enfermeiro habilitado**. Antes disso o paciente fica em status "Aguardando triagem". |
| RN03 | Protocolo Manchester, com metas de tempo até o primeiro atendimento: 🔴 Vermelho (emergência) = imediato · 🟠 Laranja (muito urgente) = 10 min · 🟡 Amarelo (urgente) = 60 min · 🟢 Verde (pouco urgente) = 120 min · 🔵 Azul (não urgente) = 240 min. Metas configuráveis por unidade (RF31). |
| RN04 | Ordem da fila: (1) cor de risco; (2) dentro da mesma cor, prioridade legal (idosos ≥ 80, depois ≥ 60, gestantes, lactantes, PcD); (3) hora de chegada. |
| RN05 | Prioridade legal **não** ultrapassa pacientes de cor mais grave. |
| RN06 | Paciente que excede a meta de tempo da sua cor gera alerta ao coordenador (RF29). |
| RN07 | Paciente chamado e ausente: 2 chamadas com intervalo de 3 min; depois vai para "não compareceu" e pode retornar ao fim da sua faixa em até 30 min (configurável). |
| RN08 | Cancelamento registra motivo (desistência, encaminhamento externo, outro). Paciente classificado como laranja/vermelho que cancela gera alerta de revisão. |
| RN09 | Reclassificação exige justificativa e fica na trilha de auditoria; o histórico de cores é preservado. |
| RN10 | Tempo estimado de espera = f(posição, cor, média móvel dos últimos atendimentos, consultórios ativos). É estimativa, sempre exibida como "aproximado". |
| RN11 | Painéis públicos exibem apenas senha (ex.: A-042) e consultório. |
| RN12 | Cada perfil acessa apenas os dados necessários à sua função (recepção não vê sinais vitais; gestor vê dados agregados, não clínicos individuais). |
| RN13 | Localização (GPS) só é coletada com consentimento explícito, apenas enquanto o paciente estiver com atendimento ativo, e é descartada após o atendimento. |
| RN14 | Dados de pacientes são retidos conforme política jurídica; dados de analytics são anonimizados. |
| RN15 | Sinais de alerta (RF14) elevam o paciente a avaliação imediata, independentemente da fila. |
| RN16 | Chat não substitui atendimento: mensagens indicando emergência exibem orientação para procurar a equipe ou ligar 192. |
