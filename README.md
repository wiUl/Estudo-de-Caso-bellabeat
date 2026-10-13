# Estudo de Caso Bellabeat — Google Data Analytics Capstone

Estudo de caso final do certificado **Google Data Analytics**. A análise usa dados públicos de atividade física de dispositivos Fitbit para identificar padrões de uso de wearables e propor recomendações de marketing e produto para a **Bellabeat**, empresa de tecnologia voltada ao bem-estar feminino.

**Estado:** concluído (novembro de 2025).

## Pergunta de negócio

Como os consumidores utilizam dispositivos inteligentes de monitoramento da saúde física, e como esses hábitos podem orientar decisões estratégicas da Bellabeat?

## Principais resultados

Valores conforme o relatório do estudo ([docs/Estudo de Caso - Bellabeat.md](docs/Estudo%20de%20Caso%20-%20Bellabeat.md)):

- Média de **7.247 passos por dia**, com **mais de 16 horas diárias** de comportamento sedentário.
- Sono médio de **7,7 horas** por noite.
- Intensidades diárias médias: ~20 min intensa, ~14 min moderada e ~185 min leve.
- Passos em dias úteis (7.271) e em fins de semana (7.188) são semelhantes.
- Baixa adesão ao registro de sono e de peso, o que limita análises mais profundas.

**Recomendações:** notificações inteligentes de movimento, metas personalizadas de atividade e sono, conteúdos educativos, campanhas voltadas a mulheres com rotinas intensas e incentivo a registros consistentes de sono e peso.

## Etapas do estudo

O relatório segue as seis fases do ciclo de análise do curso:

1. **Perguntar** — objetivo, pergunta de negócio e perguntas secundárias.
2. **Preparar** — fonte, formato, credibilidade, privacidade e verificação de integridade dos dados.
3. **Processar** — padronização de datas, conversão de tipos, remoção de duplicatas (525 linhas em `minuteSleep_merged`), checagem de campos vazios e de consistência entre distâncias.
4. **Analisar** — descobertas gerais, padrões e insights.
5. **Compartilhar** — resultados e visualizações.
6. **Agir** — conclusão e recomendações.

## Dados

- **Fonte:** [Fitbit Fitness Tracker Data (Kaggle)](https://www.kaggle.com/datasets/arashnic/fitbit), dados públicos e anonimizados.
- **Limitações (apontadas no relatório):** amostra pequena (35 usuários), sem dados demográficos e sem como confirmar que a base representa o público feminino da Bellabeat.
- **No repositório:** arquivos `.csv` compactados em `.zip`, em duas versões, **brutos** e **limpos**, para dois períodos do dataset (pastas `12-03-2016~11-04-2016` e `12-04-2016~12-05-2016`). Os arquivos incluem atividade diária, sono, calorias, intensidade, passos, batimentos cardíacos e peso (por exemplo, `dailyActivity_merged.csv`, `minuteSleep_merged.csv`, `heartrate_seconds_merged.csv`, `weightLogInfo_merged.csv`).

## Ferramentas

- **Conforme o relatório:** Google Planilhas (verificações e limpeza), Python (padronização de datas) e MySQL (organização dos dados em tabelas separadas para atividade diária, sono, calorias, intensidade, passos, batimentos e peso).
- **R:** parte das análises foi feita em R. Os scripts em R **não estão neste repositório**; estão disponíveis apenas os resultados (relatório e visualizações).
- **Scripts SQL:** a pasta `sql/` está reservada; os scripts SQL não foram incluídos.

## Visualizações

PDFs na pasta [`visualizações/`](visualizações/):

- Impacto da Duração do Sono sobre o Desempenho Físico Diário
- Relação entre Intensidade da Atividade Física, Gasto Calórico e Batimentos Cardíacos
- Relação entre Peso e Componentes de Atividade Física

## Estrutura do repositório

```text
.
├── dados/
│   ├── brutos/        # dados originais compactados (.zip), por período
│   └── limpos/        # dados após o tratamento (.zip), por período
├── docs/              # relatório completo (.md, .docx e .pdf)
├── sql/               # reservada (sem scripts)
├── visualizações/     # gráficos em PDF
└── README.md
```

## Relatório completo

- [Relatório em Markdown](docs/Estudo%20de%20Caso%20-%20Bellabeat.md)
- Também disponível em [.docx](docs/Estudo%20de%20Caso%20-%20Bellabeat.docx) e [.pdf](docs/Estudo%20de%20Caso%20-%20Bellabeat.pdf).

## Autor

**Willian Gomes** — [LinkedIn](https://www.linkedin.com/in/willian-gomes-242240174/)
