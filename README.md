# Projeto: Análise de Influenciadores do Instagram

## Descrição:

Este notebook analisa dados de influenciadores do Instagram para identificar fatores que influenciam a pontuação de influência. O código carrega o dataset "top_insta_influencers_data.csv" do Kaggle (https://www.kaggle.com/datasets/surajjha101/top-instagram-influencers-data-cleaned), realiza pré-processamento, seleciona características relevantes, treina um modelo KNN para prever a pontuação de influência e avalia seu desempenho.

## Base de Dados:

O dataset utilizado é "top_insta_influencers_data.csv" obtido do Kaggle. Ele contém informações sobre influenciadores do Instagram, incluindo:

* Classificação (rank)
* Informações do canal (canal_info) - removida por conter muitas informações textuais
* Pontuação de influência (influence_score)
* Número de posts (posts)
* Seguidores (followers)
* Média de curtidas (avg_likes)
* Taxa de engajamento de 60 dias (60_day_eng_rate)
* Média de curtidas em novos posts (new_post_avg_like)
* País (country)

## Instruções para Replicar o Projeto:

Obter o dataset: Baixe o dataset "top_insta_influencers_data.csv" do Kaggle e salve-o no mesmo diretório que este notebook.
ou execute o código a seguir:
```sh
# Biblioteca de importação
import gdown
# Baixar e fazer upload do dataset
!gdown '1g-Qo-tITl6bDGJxNP2S-dyB28uKKrURa'
```
Instalar as bibliotecas: Certifique-se de ter as seguintes bibliotecas Python instaladas:
* pandas
* numpy
* matplotlib.pyplot
* scikit-learn
* seaborn (opcional, para gráficos)
Executar o notebook: Abra o notebook em um ambiente Jupyter Notebook e execute todas as células de código (de cima para baixo).

## Resultados:

    O modelo KNN foi treinado com otimização de hiperparâmetros usando GridSearchCV.

    Os melhores hiperparâmetros encontrados foram:
        algoritmo: 'auto'
        métrica: 'manhattan'
        número de vizinhos (n_neighbors): 9
        pesos: 'distance'

    As métricas de avaliação do modelo KNN no conjunto de teste foram:
        Erro Absoluto Médio (MAE): 2.80
        Erro Quadrático Médio (MSE): 13.83
        Raiz do Erro Quadrático Médio (RMSE): 3.72
        Coeficiente de R² (R²): 0.29

    O código também analisa a distribuição dos influenciadores por continente e gera gráficos exploratórios para visualizar a relação entre as características e a pontuação de influência.

## Observações:

    O código lida com valores ausentes e realiza transformações para preparar os dados para o modelo.
    O país de origem do influenciador foi mapeado para um continente numérico. Países não mapeados foram identificados e contabilizados separadamente.

## Próximos Passos:

    Explorar outros modelos de aprendizado de máquina para a previsão de pontuação de influência.
    Analisar o impacto de características textuais (canal_info) após um pré-processamento adequado.
    Incorporar técnicas de feature engineering para criar novas características a partir das existentes.
