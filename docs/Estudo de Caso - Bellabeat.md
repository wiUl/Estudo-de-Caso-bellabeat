# 📘 **Estudo de Caso – Bellabeat**

##  **Fase 1 — Perguntar**

### **Objetivo da análise**
Investigar como usuários de dispositivos Fitbit utilizam seus aparelhos e identificar padrões de comportamento relacionados à saúde física.

### **Pergunta de negócio**
Como os consumidores utilizam dispositivos inteligentes voltados ao monitoramento da saúde física e como esses hábitos podem orientar decisões estratégicas da Bellabeat?

### **Perguntas secundárias**
- Quais são as tendências no uso de dispositivos inteligentes?
- Como essas tendências podem se aplicar às clientes da Bellabeat?
- Como elas podem influenciar a estratégia de marketing da empresa?

### **Resumo da tarefa de negócios**
A Bellabeat deseja expandir sua presença no mercado de dispositivos inteligentes e de bem-estar. Esta análise busca compreender o comportamento dos usuários para gerar recomendações estratégicas alinhadas ao perfil do público feminino da marca.

---

##  **Fase 2 — Preparar**

### **Fonte dos dados**
Os dados utilizados estão disponíveis no Kaggle:  
https://www.kaggle.com/datasets/arashnic/fitbit/data

### **Formato dos dados**
Os arquivos estão no **formato longo**, registrando atividades por usuário por dia.

### **Credibilidade e limitações**
- Amostra pequena (35 usuários).  
- Ausência de dados demográficos (sexo, idade, altura).  
- Não é possível saber se a base representa especificamente o público feminino — principal público da Bellabeat.  
- Possível viés por falta de diversidade de perfis.

### **Privacidade e licenciamento**
- Dados públicos.  
- Usuários anonimizados.  
- Uso permitido para análise.

### **Verificação de integridade**
- Remoção de duplicatas.  
- Checagem de campos vazios.  
- Consistência lógica entre distâncias.  
- Padronização de datas e tipos numéricos.

### **Problemas encontrados**
- Inconsistências entre TotalDistance e distâncias parciais (possível erro de GPS).  
- No arquivo minuteSleep_merged: centenas de duplicatas foram removidas.  
- Usuários com registros incompletos de sono e peso.  

### **Resumo da operação**
Os dados foram limpos, inconsistências pequenas foram justificadas e duplicatas removidas. Apesar das limitações, o dataset está apto para análises exploratórias.

---

##  **Fase 3 — Processar**

### **Ferramentas utilizadas**
- Google Spreadsheets  
- Python  
- MySQL  

### **Procedimentos de limpeza**
- Padronização de datas  
- Conversão de tipos numéricos  
- Remoção de duplicatas  
- Checagem de valores vazios  
- Verificação de coerência entre valores relacionados (atividades × distância)  

### **Critérios de validação**
- Chave composta **ID + Data** única por registro  
- Distâncias consistentes com atividades  
- Outliers analisados individualmente  
- Arquivos duplicados removidos antes da carga no banco  

### **Quadro de limpeza e tratamento dos dados**

| Etapa | Descrição | Ferramenta | Justificativa | Resultado |
|------|-----------|------------|---------------|-----------|
| Padronização do formato de data | Ajuste para padrão AAAA-MM-DD HH:MM:SS | Python | Datas interpretadas de forma inconsistente | Ex.: 4/12/2016 → 2016-04-12 00:00:00 |
| Remoção de duplicatas | Exclusão de linhas repetidas | Spreadsheets | Evitar duplicidade | 525 linhas removidas em minuteSleep_merged |
| Verificação de campos vazios | Filtro para campos nulos | Spreadsheets | Evitar distorções nas análises | Nenhum campo vazio encontrado |
| Conferência de consistência | Comparação de distâncias | Spreadsheets | Detectar erros de GPS | Diferenças pequenas aceitas; discrepâncias marcadas |

### **Organização para análise**
Após o tratamento, os dados foram importados para um banco MySQL com tabelas separadas para: atividade diária, sono, calorias, intensidade, passos, batimentos e peso.

---

##  **Fase 4 — Analisar**

### **Descobertas gerais**
- Usuários apresentam perfis variados.  
- Média diária: **7.247 passos**.  
- Tempo sedentário elevado.  
- Sono médio: **7,7 horas**.  
- Baixa adesão ao registro de sono e peso.

### **Padrões identificados**
- Sono adequado relaciona-se a maior equilíbrio energético.  
- Rotinas semelhantes entre dias úteis e fins de semana.  
- Atividades intensas são raras, mas influenciam o gasto calórico.  
- Uso irregular do dispositivo por alguns usuários.

### **Insights chave**
- Sono + atividade física explicam grande parte do gasto calórico.  
- Há oportunidade de aumentar engajamento.  
- Predominância de comportamento sedentário.

---

##  **Fase 5 — Compartilhar**

### **1. Panorama geral de atividade física**
Valores médios:
- **2.264 kcal** gastas por dia  
- **5,19 km** percorridos  
- **7.247 passos/dia**

### **2. Distribuição do tempo por intensidade e sono**
- **43,4%** do tempo inativo diário é sono.  
- Mais de **16 horas/dia** de comportamento sedentário.  
- Intensidades diárias:
  - Intensa: ~20 min  
  - Moderada: ~14 min  
  - Leve: ~185 min  

### **3. Comparativo de passos — dias úteis vs. fim de semana**
- Semana: **7.271 passos**  
- Fim de semana: **7.188 passos**  

### **Visualizações produzidas**

#### 🔗 Impacto da Duração do Sono sobre o Desempenho Físico Diário  
[📄 Download PDF](../visualizações/Impacto%20da%20Duração%20do%20Sono%20sobre%20o%20Desempenho%20Físico%20Diário.pdf)

#### 🔗 Relação entre Intensidade da Atividade Física, Gasto Calórico e Batimentos Cardíacos  
[📄 Download PDF](../visualizações/Relação%20entre%20Intensidade%20da%20Atividade%20Física,%20Gasto%20Calórico%20e%20Batimentos%20Cardíacos.pdf)

#### 🔗 Relação entre Peso e Componentes de Atividade Física  
[📄 Download PDF](../visualizações/Relação%20entre%20Peso%20e%20Componentes%20de%20Atividade%20Física.pdf)

---

##  **Fase 6 — Agir**

### **Conclusão geral**
O comportamento típico das usuárias é predominantemente sedentário, mesmo com sono adequado. Atividades físicas são distribuídas em pequenos períodos, limitando benefícios metabólicos.

### **Recomendações**
- Notificações inteligentes de movimento.  
- Metas personalizadas de atividade e sono.  
- Conteúdos educativos.  
- Campanhas voltadas para mulheres com rotinas intensas.  
- Incentivo a registros consistentes de sono e peso.

