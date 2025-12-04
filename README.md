# 🚕 Chicago Taxi Insights — EDA + Teste de Hipótese

## Sobre o Projeto
Aqui a missão é analisar dados de corridas de táxi em Chicago usando Python. Você recebe três arquivos CSV e precisa explorar, visualizar e testar uma hipótese relacionada ao impacto do clima na duração das viagens.

## 🎯 Objetivo Principal
Fazer uma análise exploratória rápida e clara dos bairros que mais recebem corridas, das empresas mais movimentadas e testar se **sábados chuvosos afetam o tempo médio de viagem do Loop para o Aeroporto O’Hare**.

## 📌 O Que Foi Feito

### **1. Importação e Inspeção dos Dados**
Arquivos utilizados:
- `project_sql_result_01.csv` — empresas de táxi e número de corridas (15–16 nov/2017).
- `project_sql_result_04.csv` — bairros de destino e média de viagens no mês.
- `project_sql_result_07.csv` — viagens do Loop → O’Hare, com timestamp, clima e duração.

Ações:
- Importação dos três CSVs.
- Verificação dos tipos de dados.
- Checagem de inconsistências, nulos e formatação.

### **2. Análise Exploratória (EDA)**
- Identificação das empresas de táxi mais ativas.
- Top 10 bairros com mais corridas finalizadas.
- Criação de gráficos:
  - empresas × número de corridas;
  - top 10 bairros como destinos.
- Interpretação de cada visualização: padrões de demanda, concentração de corridas e possíveis explicações.

### **3. Teste de Hipótese**
Hipótese analisada:
> *A duração média das viagens do Loop para o Aeroporto O’Hare muda nos sábados chuvosos.*

Definições:
- **H₀**: não há diferença na duração média das corridas entre sábados chuvosos e não chuvosos.
- **H₁**: há diferença.

Método:
- Teste **t de Welch** (versão robusta do t‑test para variâncias diferentes).
- Alfa escolhido: **0,05**.
- Variável analisada: `duration_seconds`.

Critério de decisão:
- `p ≤ 0,05` → rejeita H₀ → clima influencia.
- `p > 0,05` → não rejeita H₀ → sem evidência de mudança.

Justificativa:
- Dois grupos independentes (chuva vs. sem chuva).
- Dado contínuo.
- Amostras grandes.
- Welch é robusto quando as variâncias diferem.

### **4. Conclusão Geral**
Resumo das descobertas:
- As empresas mais movimentadas e bairros de destino mais frequentes.
- Comportamento da distribuição de viagens por região.
- Resultado do teste estatístico sobre a influência da chuva.

## 🚀 Resultado Esperado
Ao final, você terá:
- um EDA enxuto e visual;
- comparação clara entre empresas e bairros;
- análise estatística sólida sobre clima e duração das viagens;
- um relatório pronto pra apresentar.
