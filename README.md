[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/matheusfdamasio/mvp-machine-learning/blob/main/mvp_machinelearning.ipynb)

# MVP — Machine Learning & Analytics

**Aluno:** Matheus Fernandes Damasio

**Curso:** Pós-graduação em Ciência de Dados e Analytics

**Disciplina:** Machine Learning & Analytics

## Sobre o Projeto

Sistema de detecção de anomalias sobre as despesas da [Cota para Exercício da Atividade Parlamentar (CEAP)](https://dadosabertos.camara.leg.br/swagger/api.html?tab=staticfile), da Câmara dos Deputados, que reúne mais de 1,4 milhão de reembolsos autodeclarados por parlamentares entre 2019 e 2025.

Como os dados públicos não trazem rótulo de irregularidade, o problema é tratado como aprendizado não supervisionado: o modelo aprende o padrão de gasto normal e sinaliza despesas estatisticamente atípicas, priorizando quais registros merecem revisão humana e reduzindo o esforço manual de auditoria. O objetivo não é acusar fraude, e sim triar candidatos para análise.

A solução compara três abordagens sobre sete features de suspeição construídas a partir dos dados brutos: uma baseline por z-score, o Isolation Forest e o Local Outlier Factor (LOF).

## Estrutura do Repositório

```
├── mvp_machinelearning.ipynb        # Notebook com o MVP completo
├── dados/
│   ├── Ano-2019.csv.zip             # Cópia congelada da CEAP (2019)
│   ├── Ano-2020.csv.zip
│   ├── Ano-2021.csv.zip
│   ├── Ano-2022.csv.zip
│   ├── Ano-2023.csv.zip
│   ├── Ano-2024.csv.zip
│   └── Ano-2025.csv.zip             # Cópia congelada da CEAP (2025)
└── README.md
```

## Como Executar

1. Abra o notebook no [Google Colab](https://colab.research.google.com/github/matheusfdamasio/mvp-machine-learning/blob/main/mvp_machinelearning.ipynb).
2. Execute todas as células sequencialmente (Ambiente de execução > Executar tudo).
3. Os dados são carregados automaticamente a partir da cópia versionada neste repositório, sem download manual. Caso alguma URL do repositório falhe, o notebook recorre ao portal oficial da Câmara como fallback.

A cópia congelada em `dados/` garante reprodutibilidade: como o portal da CEAP é atualizado diariamente, executar direto dele produziria contagens ligeiramente diferentes a cada dia.

## Tecnologias Utilizadas

- Python 3
- Pandas / NumPy
- Matplotlib / Seaborn
- Scikit-learn (IsolationForest, LocalOutlierFactor, RobustScaler)

