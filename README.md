
# 🛍️ Projeto Individual PI2: Segmentação de Clientes (Clusterização)

## 🎯 Objetivo
Este projeto individual (PI2) aplica técnicas de **Aprendizado de Máquina Não Supervisionado** para resolver um problema de Clusterização (Agrupamento). O objetivo principal é identificar padrões de consumo e segmentar clientes de um shopping center, utilizando dados de renda e comportamento de gastos.

O projeto foca na aplicação e comparação visual de dois algoritmos distintos para descobrir grupos (clusters) implícitos nos dados, simulando um cenário real de estratégia de marketing direcionado.

## 🤖 Modelos e Metodologia
Foram implementados e avaliados dois algoritmos de Clusterização:

* **K-Means:** Utilizado como algoritmo de partição baseado em centroides. Foi aplicado o *Método do Cotovelo (Elbow Method)* para determinar matematicamente o número ideal de grupos ($K$).
* **Hierarchical Clustering (Agrupamento Hierárquico):** Utilizado para construir uma hierarquia de clusters. Foi gerado um *Dendrograma* para visualizar a formação dos grupos e decidir o ponto de corte ideal.

## 📊 Critérios de Avaliação
Diferente da aprendizagem supervisionada, não há "respostas corretas" (labels) prévias. A avaliação foi feita através de:
* **Inércia (WCSS):** Para avaliar a compactação dos clusters no K-Means.
* **Dendrograma:** Para análise visual da distância entre os agrupamentos.
* **Interpretabilidade:** Análise qualitativa de se os grupos formados faziam sentido para o negócio.

## 🔍 Estrutura do Projeto e Análise
O código segue as seguintes etapas obrigatórias:

1.  **ETL e Pré-processamento:** Geração de dados fictícios robustos, verificação de integridade e **Padronização dos dados (StandardScaler)**. A padronização foi crucial para garantir que a variável "Renda" (escala alta) não dominasse a variável "Score" (escala baixa) no cálculo de distâncias.
2.  **Definição de Hiperparâmetros:** Uso de gráficos (Elbow e Dendrograma) para definir $K = 5$ clusters.
3.  **Modelagem e Visualização:** Treinamento dos modelos e plotagem de gráficos de dispersão (Scatterplots) coloridos por cluster.
4.  **Análise e Interpretação:** Ambos os algoritmos convergiram para 5 perfis de clientes distintos:

| Perfil Identificado | Características (Renda vs Gastos) | Sugestão de Ação |
| :--- | :--- | :--- |
| **Econômicos** | Baixa Renda, Baixo Gasto | Promoções e descontos |
| **Impulsivos** | Baixa Renda, Alto Gasto | Crédito e parcelamento |
| **Massa (Padrão)** | Renda Média, Gasto Médio | Fidelidade genérica |
| **Poupadores** | Alta Renda, Baixo Gasto | Produtos de nicho/Investimentos |
| **VIPs** | Alta Renda, Alto Gasto | Atendimento exclusivo |

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** `pandas`, `numpy`, `scikit-learn` (KMeans, AgglomerativeClustering, StandardScaler), `scipy` (dendrograma), `matplotlib`, `seaborn`.
* **Ambiente:** Google Colab / Jupyter Notebook
