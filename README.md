# ⚽ Premier League Player Profiling: Association Rules
### Data Mining | Association Learning Project

Projeto de **Mineração de Dados** aplicado à descoberta de padrões e relações entre estatísticas de jogadores da Premier League (Campeonato Inglês).

O objetivo foi identificar **regras de associação** que conectam nacionalidade, posição em campo e produtividade ofensiva, utilizando técnicas de aprendizado de máquina não supervisionado.

---

## 📌 Contexto do Problema

No futebol moderno, a análise de dados (*Soccermetrics*) é fundamental para:

- Entender a demografia das ligas.
- Identificar correlações entre posicionamento e eficiência.
- Validar hipóteses táticas com dados reais.
- Apoiar decisões de recrutamento baseadas em perfis de sucesso.

Este projeto busca responder:

> Existem padrões ocultos que associam a nacionalidade e a posição de um jogador ao seu volume de golos na liga mais competitiva do mundo?

---

## 📊 Dataset

- Dados detalhados de jogadores da Premier League.
- Estatísticas de desempenho por 90 minutos.
- Variáveis demográficas e posicionais.

**Principais features utilizadas:**
- **Nacionalidade (Nation):** Origem do atleta.
- **Posição (Pos):** Especialização em campo (FW, MF, DF, GK).
- **Golos (Goals):** Volume de golos marcados (categorizados para análise).
- **Assistências, Minutos e Idade:** Utilizados no contexto exploratório.

---

## ⚙️ Pipeline do Projeto

### 1️⃣ Data Cleaning & Preprocessing
- **Tratamento de Strings:** Limpeza de prefixos de nacionalidade.
- **Categorização (Binning):** Transformação da variável contínua "Golos" em categorias discretas (ex: baixo, médio, alto) para permitir a mineração de regras.
- **One-Hot Encoding:** Transformação do dataframe em uma matriz booleana (transações) para compatibilidade com o algoritmo.
- **Filtragem:** Seleção de atributos categóricos relevantes para a análise de associação.

---

### 2️⃣ Modelagem (Mineração de Regras)
Algoritmo utilizado: **Apriori**

Principais métricas de avaliação:
- **Suporte (Support):** Frequência com que a combinação de itens aparece no dataset.
- **Confiança (Confidence):** Probabilidade de o item B ocorrer dado que o item A está presente.
- **Lift:** Força da associação (quão mais frequente é a regra do que o esperado se os itens fossem independentes).



---

### 3️⃣ Análise de Resultados
- Geração de regras de associação com métricas de suporte e confiança mínimas.
- Filtragem de regras com `lift > 1` para garantir associações positivas e relevantes.
- Visualização de dispersão (Scatter Plot) para identificar as regras com melhor equilíbrio entre suporte e confiança.

---

## 📈 Resultados

O modelo identificou associações interessantes, tais como:

- **Perfil de Finalizadores:** Forte associação entre a posição *Forward* (FW) e categorias de golos mais elevados.
- **Predomínio Geográfico:** Padrões de nacionalidade que dominam certas funções táticas na liga.
- **Validação Tática:** Regras que confirmam a baixa probabilidade de defensores (DF) atingirem altos volumes de golos, validando a consistência dos dados.

---

## 🛠️ Stack Tecnológica

- **Python**
- **Pandas:** Manipulação e limpeza de dados.
- **MLxtend:** Implementação do Algoritmo Apriori e Association Rules.
- **Matplotlib / Seaborn:** Visualização de dados e gráficos estatísticos.
- **Jupyter Notebook:** Ambiente de desenvolvimento.
