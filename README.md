# Projeto de Detecção de Fraudes em Transações Pix

## Sobre o Projeto

Este projeto tem como objetivo desenvolver um modelo de Machine Learning para identificar transações anômalas (potencialmente fraudulentas) em um dataset sintético de transações Pix, disponível no Kaggle. O projeto percorre todas as etapas de um pipeline de Ciência de Dados, desde a análise exploratória até a avaliação de modelos de classificação.

**Link para o Dataset:** [Pix Fraud Detection Dataset no Kaggle](https://www.kaggle.com/datasets/juniorbueno/pix-banking-transaction)

## Objetivo de Negócio

Com o crescimento exponencial das transações digitais, a detecção de fraudes em tempo real tornou-se crucial. O objetivo deste projeto é construir um modelo que possa alertar analistas sobre transações suspeitas com alta precisão, otimizando o tempo da equipe e minimizando perdas financeiras.

## Ferramentas Utilizadas
- **Linguagem:** Python
- **Bibliotecas:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

## Metodologia

1.  **Análise Exploratória de Dados (EDA):** Investigação inicial dos dados para entender suas características, distribuições e a proporção de anomalias (1%).
2.  **Engenharia de Features:** Criação de novas features a partir da coluna `DataHora` para extrair informações relevantes como a hora do dia e o dia da semana.
3.  **Modelagem:**
    * **Modelo Base (Regressão Logística):** Um primeiro modelo foi treinado, que, após o balanceamento de classes (`class_weight='balanced'`), atingiu um recall de 87%, mas com uma precisão de apenas 1%, gerando muitos falsos positivos.
    * **Modelo Avançado (Random Forest):** Para otimizar a precisão, um modelo Random Forest foi treinado. Este modelo se mostrou muito superior para o caso de uso.
4.  **Avaliação:** Os modelos foram avaliados usando Matriz de Confusão e Relatório de Classificação, com foco nas métricas de Precisão e Recall para a classe minoritária (anomalia).

## Resultados

O modelo final escolhido foi o **Random Forest**, que apresentou um excelente equilíbrio entre a capacidade de detectar fraudes e a eficiência operacional:

- **Precisão:** 89% (de cada 10 alertas gerados, quase 9 são fraudes reais)
- **Recall:** 53% (capacidade de detectar mais da metade de todas as fraudes)
- **Falsos Positivos:** Apenas 1 em um conjunto de teste de quase 2000 transações.

## Como Executar o Projeto

1. Clone o repositório: `git clone https://github.com/seu-usuario/seu-repositorio.git`
2. Execute o notebook Jupyter ou o script Python.
