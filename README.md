# 📊 Projeto de Limpeza e Tratamento de Dados

## Descrição do Projeto
Este projeto tem como objetivo aplicar técnicas de **limpeza, padronização e tratamento de dados** em diferentes datasets, abordando problemas comuns encontrados em bases reais, como:

- Valores ausentes (missing values)  
- Duplicatas exatas e aproximadas  
- Inconsistências em dados categóricos  
- Outliers e valores extremos  

---

## Etapas de Tratamento de Dados

### 1. Exploração Inicial
- Análise de estatísticas descritivas (média, mediana, desvio padrão)  
- Contagem de valores ausentes e duplicatas  
- Visualização de distribuições e padrões de missing values com gráficos (`histplot`, `boxplot`, `missingno`)

### 2. Tratamento de Valores Ausentes
- **Numéricos:** imputação usando **mediana** ou média  
- **Categóricos:** substituição por valores padrão, como "Desconhecido"  
- Documentação do impacto na quantidade de registros e distribuição dos dados  

### 3. Duplicatas
- **Duplicatas exatas:** removidas diretamente com `drop_duplicates()`  
- **Duplicatas aproximadas:** detectadas usando **fuzzy matching** em colunas-chave  
- Estratégia de manutenção: manter registros mais recentes ou combinar informações relevantes  

### 4. Padronização de Dados Categóricos
- Remoção de espaços extras  
- Capitalização consistente (`title case`)  
- Uniformização de valores específicos (ex.: "United-States" → "United States")

### 5. Detecção e Tratamento de Outliers
- **Métodos utilizados:**  
  - **Z-score** (valores >3 desvios padrão)  
  - **IQR (Interquartile Range)** (valores fora de 1,5×IQR)  
- **Estratégias aplicadas:**  
  - Remoção de outliers  
  - Capping (substituição por limites inferior e superior)  
  - Transformações matemáticas (log, raiz quadrada)  
- Comparação do impacto nas estatísticas descritivas

### 6. Normalização de Dados Numéricos
- **Min-Max Scaling:** transforma dados para o intervalo [0,1]  
- **Z-score Standardization:** centraliza média 0 e desvio padrão 1  
- **Robust Scaling:** menos sensível a outliers, baseado na mediana e IQR  

### 7. Criação de Novas Features
- Exemplo: categorização de preços (`Price_Category`)  
- Extração de informações úteis para análise e modelagem  

---

## Resultados Esperados
Após a aplicação do pipeline completo de limpeza e tratamento de dados, espera-se:

- Redução de inconsistências e duplicatas  
- Distribuição mais uniforme de dados numéricos  
- Valores ausentes devidamente imputados  
- Outliers tratados de maneira que não distorçam análises  
- Dataset pronto para análise exploratória e modelagem  

---

## Bibliotecas Utilizadas
- `pandas`, `numpy` – manipulação de dados  
- `matplotlib`, `seaborn` – visualização de dados  
- `missingno` – análise de valores ausentes  
- `scipy.stats` – detecção de outliers (Z-score)  
- `sklearn.preprocessing` – normalização e scaling  
- `fuzzywuzzy` – detecção de duplicatas aproximadas  
