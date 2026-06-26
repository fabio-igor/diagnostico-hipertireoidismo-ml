# Diagnostico Preditivo de Hipertireoidismo com Machine Learning

Projeto Final - Curso de Ciencia de Dados EBAC

## Sobre o Projeto

Este projeto simula uma demanda real de um endocrinologista que
precisa de um modelo de machine learning para auxiliar no diagnostico
de disfuncao tireoidiana, priorizando a minimizacao de falsos negativos.

## 1. Coleta de Dados

A base contem 3.772 pacientes e 30 atributos, incluindo dados
demograficos, historico clinico e exames laboratoriais (TSH, T3,
TT4, T4U, FTI). A variavel target e binaria: P (doente) ou N (saudavel).

Fonte: Garavan Institute / UCI Machine Learning Repository - Thyroid
Disease Dataset.

## 2. Preparacao e Analise Exploratoria

- Tratamento de valores faltantes (mediana para exames laboratoriais)
- Remocao da coluna TBG (100% nula)
- Correcao de outlier critico (idade registrada incorretamente)
- Identificacao de TSH, FTI e TT4 como as variaveis mais correlacionadas
  com o diagnostico

## 3. Modelagem

Foram comparados tres modelos:

| Modelo | Acuracia | AUC |
|--------|----------|-----|
| Random Forest | 100% | 1.0000 |
| **XGBoost** | **99.87%** | **0.9999** |
| Regressao Logistica | 97.62% | 0.9658 |

Tecnicas aplicadas:
- Balanceamento de classes com SMOTE
- Validacao cruzada (5 folds)
- Otimizacao de hiperparametros com GridSearchCV

## 4. Resultado Final

O modelo XGBoost otimizado atingiu **zero falsos negativos** no
conjunto de teste, atendendo ao requisito clinico critico de nao
deixar nenhum caso de disfuncao tireoidiana passar despercebido.

**Feature Importance:** TSH concentra 89.5% do poder preditivo do
modelo, confirmando coerencia com o conhecimento medico estabelecido.

## Relatorio Completo

O relatorio executivo completo, com analise detalhada e recomendacoes
para uso clinico, esta disponivel em:
[Relatorio_Diagnostico_Hipertireoidismo.pdf](./Relatorio_Diagnostico_Hipertireoidismo.pdf)

## Tecnologias Utilizadas

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- Matplotlib, Seaborn

## Autor

Fabio Igor da Silva Oliveira
