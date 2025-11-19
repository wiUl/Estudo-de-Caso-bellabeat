# 📘 Estudo de Caso – Bellabeat
## Fase 1 — Perguntar
Objetivo da análise

Investigar como usuários de dispositivos Fitbit utilizam seus aparelhos e identificar padrões de comportamento relacionados à saúde física.

Pergunta de negócio

Como os consumidores utilizam dispositivos inteligentes voltados ao monitoramento da saúde física e como esses hábitos podem orientar decisões estratégicas da Bellabeat?

Perguntas secundárias

Quais são as tendências no uso de dispositivos inteligentes?

Como essas tendências podem se aplicar às clientes da Bellabeat?

Como elas podem influenciar a estratégia de marketing da empresa?

Resumo da tarefa de negócios

A Bellabeat deseja expandir sua presença no mercado de dispositivos inteligentes e de bem-estar. Esta análise busca compreender o comportamento dos usuários para gerar recomendações estratégicas alinhadas ao perfil do público feminino da marca.

## Fase 2 — Preparar
Fonte dos dados

Os dados utilizados estão disponíveis no Kaggle:
https://www.kaggle.com/datasets/arashnic/fitbit/data

Formato dos dados

Os arquivos estão no formato longo, registrando atividades por usuário por dia.

Credibilidade e limitações

Amostra pequena (35 usuários).

Ausência de dados demográficos (sexo, idade, altura).

Não é possível saber se a base representa especificamente o público feminino — principal público da Bellabeat.

Possível viés por falta de diversidade de perfis.

Privacidade e licenciamento

Dados públicos.

Usuários anonimizados.

Uso permitido para análise.

Verificação de integridade

Remoção de duplicatas.

Checagem de campos vazios.

Consistência lógica entre distâncias.

Padronização de datas e tipos numéricos.

Problemas encontrados

Inconsistências entre TotalDistance e distâncias parciais (possível erro de GPS).

No arquivo minuteSleep_merged: centenas de duplicatas foram removidas.

Usuários com registros incompletos de sono e peso.

Resumo da operação

Os dados foram limpos, inconsistências pequenas foram justificadas e duplicatas removidas. Apesar das limitações, o dataset está apto para análises exploratórias.

## Fase 3 — Processar
Ferramentas utilizadas

Google Spreadsheets

Python

MySQL

Procedimentos de limpeza

Padronização de datas

Conversão de tipos numéricos

Remoção de duplicatas

Checagem de valores vazios

Verificação de coerência entre valores relacionados (atividades × distância)

Critérios de validação

Chave composta ID + Data única por registro

Distâncias consistentes com atividades

Outliers analisados individualmente

Arquivos duplicados removidos antes da carga no banco

Quadro de limpeza e tratamento dos dados
Etapa	Descrição	Ferramenta	Justificativa	Resultado
Padronização do formato de data	Ajuste para padrão AAAA-MM-DD HH:MM:SS	Python	Datas interpretadas de forma inconsistente	Ex.: 4/12/2016 → 2016-04-12 00:00:00
Remoção de duplicatas	Exclusão de linhas repetidas	Spreadsheets	Evitar duplicidade	525 linhas removidas em minuteSleep_merged
Verificação de campos vazios	Filtro para campos nulos	Spreadsheets	Evitar distorções nas análises	Nenhum campo vazio encontrado
Conferência de consistência	Comparação de distâncias	Spreadsheets	Detectar erros de GPS	Diferenças pequenas aceitas; discrepâncias marcadas
Organização para análise

Após o tratamento, os dados foram importados para um banco MySQL contendo tabelas separadas para: atividade diária, sono, calorias, intensidade, passos, batimentos e peso.

## Fase 4 — Analisar
Descobertas gerais

Usuários apresentam perfis variados: alguns altamente ativos, outros pouco ativos.

Média diária: 7.247 passos e grande quantidade de tempo sedentário.

Sono médio: 7,7 horas, com grande variação entre usuários.

Baixa adesão ao registro de sono e peso limita a profundidade das análises.

Padrões identificados

Sono adequado tende a se correlacionar com equilíbrio energético.

Pouca diferença entre dias úteis e finais de semana.

Atividades intensas são raras, mas influenciam fortemente o gasto calórico.

Alguns usuários têm uso irregular do dispositivo.

Insights chave

A combinação entre sono e atividade física explica boa parte do gasto calórico.

Há oportunidade de aumentar engajamento e regularidade.

Comportamento predominantemente sedentário — alvo direto de melhoria.

## Fase 5 — Compartilhar
1. Panorama geral de atividade física

Valores médios observados:

2.264 kcal gastas por dia

5,19 km percorridos

7.247 passos/dia

Esses indicadores refletem um nível moderado de atividade, mas abaixo de recomendações internacionais (10k passos/dia). Distância e gasto calórico acompanham a baixa intensidade geral.

2. Distribuição do tempo por intensidade e sono

43,4% do tempo inativo diário é sono (≈ 431 min)

Usuárias permanecem >16 horas/dia sedentárias, somando sono + inatividade acordada

Tempo médio diário por intensidade:

Intensa: ≈ 20 min

Moderada: ≈ 14 min

Leve: ≈ 185 min

O comportamento sedentário é predominante e consistente com o baixo volume de atividades intensas.

3. Comparativo de passos — dias úteis vs. fim de semana

Dias úteis: 7.271 passos

Fim de semana: 7.188 passos

A diferença é pequena, indicando rotina estável e consistente.

Visualizações produzidas (com links para download)
🔗 1. Relação entre Intensidade da Atividade Física, Gasto Calórico e Batimentos Cardíacos

📄 Download PDF

🔗 2. Impacto da Duração do Sono sobre o Desempenho Físico Diário

📄 Download PDF

🔗 3. Relação entre Peso e Componentes de Atividade Física

📄 Download PDF

(Certifique-se de ajustar o caminho conforme a pasta onde os PDFs serão armazenados.)

## Fase 6 — Agir
Conclusão geral

O comportamento típico das usuárias é predominantemente sedentário, mesmo com uma média adequada de horas de sono. As atividades físicas são fragmentadas, e a ausência de pausas regulares limita benefícios metabólicos.

Principais recomendações

Criar notificações inteligentes de movimentação.

Oferecer metas personalizadas de atividade e sono.

Reforçar educação sobre hábitos saudáveis.

Direcionar campanhas para mulheres com rotinas intensas.

Incentivar registros regulares de sono e peso.
