
# ⚡ Big Data - Apache Spark

Aplicando ciência de dados em cima de grandes volumes de dados através do paradigma de divisão e conquista com Apache Spark




## 💻 Ambiente

Fizemos nosso trabalho usando dois ambientes distintos: um ambiente local e o Google Colab. Optamos por essa abordagem pois não tinhamos recursos suficientes para o processamento de dados dos tweets.

No ambiente local, configuramos nosso próprio ambiente de desenvolvimento Spark em nossas máquinas. Usamos esse ambiente principalmente para a análise das reviews, pois podíamos acessar facilmente os conjuntos de dados locais e executar nossos scripts Spark diretamente em nossas máquinas.

Por outro lado, usamos o Google Colab para a campanha política. Optamos por essa plataforma porque ela oferece recursos computacionais poderosos e uma integração fácil com o Spark. Como a campanha política envolvia o processamento de grandes volumes de dados em escala, o ambiente do Google Colab nos proporcionou os recursos necessários para lidar com essa demanda computacional.

Além disso, utilizamos os seguintes recursos/ferramentas:
 - Python
 - Jupyter
 - Pyspark
 - Pandas
 - Matplotlib
 - Seaborn
 - Regex
 - Natural Language Toolkit
 - TextBlob

## 🐤 Tweets da Campanha Eleitoral de 2014

### [Hashtags e Tweets](https://github.com/thomz2/big-data-spark/blob/main/analysis/election_campaign/hashtags_and_tweets.ipynb)

#### Hashtags mais usadas pela manhã, tarde e noite:
Para identificar as hashtags mais usadas pela manhã, tarde e noite, fazemos uma análise temporal dos tweets, categorizando-os em diferentes períodos do dia (manhã, tarde e noite) com base no horário em que foram postados. 

Em seguida, fazemos a contagem das hashtags mais frequentes em cada período e os resultados são apresentados em gráficos de barras, mostrando as 10 hashtags mais populares em cada período do dia:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/29461700-ba80-45b4-baf8-4087a305f49c)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/5ddfe7f3-a70f-416b-8c00-18ca3e588376)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/0f917453-105d-469b-a376-456edfed091a)

#### Hashtags mais usadas em cada dia
A análise das hashtags mais usadas em cada dia é feita através da contagem das hashtags presentes nos tweets de cada dia, agrupadas por data. 

Filtramos os tweets que possuem hashtags, contabilizamos a frequência das hashtags em cada dia e apresentamos os resultados em gráficos de barras, exibindo as 10 hashtags mais utilizadas em cada dia:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/2b854da1-dc38-4c8e-a5be-6aba4a79162d)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/a3f41341-509b-4a8b-a051-173957c4f476)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/27678806-1865-4a5c-84c1-c39923557c22)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/7f1d44db-382c-4474-a63b-4313c19eb32a)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/5a004644-d180-4a98-9e6b-0ac750ded28a)
![image](https://github.com/thomz2/big-data-spark/assets/82160387/35314cc2-10ad-475c-ac88-dc6ba5c07645)

#### Número de tweets por hora a cada dia
Calculamos o número de tweets por hora em cada dia, agrupando os tweets por hora do dia e contabilizando a quantidade de tweets em cada período. 

Em seguida, apresentamos os resultados em um gráfico de linha, mostrando a distribuição temporal do número de tweets ao longo das horas do dia:

![image](https://github.com/thomz2/big-data-spark/assets/82160387/291ff125-d9f3-4d74-9e5e-23d77483e5a7)

### Figuras Políticas

#### [Principais sentenças relacionadas à palavra “Dilma”](https://github.com/thomz2/big-data-spark/blob/main/analysis/election_campaign/dilma.ipynb)
Para identificar as principais sentenças relacionadas à palavra "Dilma", carregamos os tweets relacionados à campanha eleitoral do dataset e filtramos aqueles que contêm a palavra-chave "Dilma", após isso, realizamos a limpeza e formatação dos dados, removendo caracteres especiais e stopwords da língua portuguesa. 

Após essa etapa, utilizamos a técnica de n-gramas para identificar sequências de 3 a 5 palavras mais frequentes nos tweets, selecionando dessas, as 10 expressões mais comuns:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/c0fe029f-2e82-4b78-91e6-037300b1ec35)

#### [Principais sentenças relacionadas à palavra “Aécio”](https://github.com/thomz2/big-data-spark/blob/main/analysis/election_campaign/aecio.ipynb)
Utilizamos o mesmo processo para identificarmos as principais sentenças relacionadas à palavra "Aécio".

Fizemos isso apenas trocando a constante `WORD` que era `dilma` para `aecio`:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/6435e1d6-1e4f-468a-99be-58ae1f3c6eae)

## 🗼 Reviews Relacionados à Visita da Torre Eiffel em Paris

### [Palavras e Expressões](https://github.com/thomz2/big-data-spark/blob/main/analysis/eiffel_tower/most_frequent_words_and_expressions.ipynb)

#### Palavras mais utilizadas nas avaliações
Para encontrar as palavras mais utilizadas nas avaliações, nós seguimos um processo sistemático de limpeza e análise de texto. Primeiro, carregamos os dados das avaliações, focando nas colunas de título e texto. Removemos quaisquer valores ausentes para garantir a integridade dos dados. Em seguida, realizamos a limpeza das colunas, removendo caracteres especiais e mantendo apenas letras e números.

Depois disso, tokenizamos o texto, transformando as frases em listas de palavras individuais. Para aumentar a precisão da análise, removemos as palavras comuns (stop words) que geralmente não carregam muito significado, como "e", "de", "a", etc. Em seguida, usamos a função explode para separar cada palavra em uma linha própria. Contamos a frequência de cada palavra usando a função groupBy e ordenamos os resultados em ordem decrescente de frequência. Por fim, plotamos as 10 palavras mais frequentes em um gráfico de barras:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/7b917330-c775-4654-958d-c27e8a47cfce)

#### Expressões mais usadas nas avaliações
Para encontrar as expressões mais usadas nas avaliações, começamos com o mesmo processo de limpeza e tokenização usado para as palavras individuais. Em seguida, criamos n-grams para identificar expressões comuns.

Depois de gerar essas expressões, explodimos as listas de n-grams, assim como fizemos com as palavras individuais, para que cada expressão tivesse sua própria linha. Agrupamos essas expressões e contamos a frequência de cada uma, ordenando-as em ordem decrescente de contagem. Combinamos os resultados de n-grams de textos e títulos, agrupamos novamente e somamos as frequências para obter as expressões mais frequentes no conjunto de dados completo. Finalmente, apresentamos as 10 expressões mais usadas em um gráfico de barras:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/55df194b-b0f8-4c25-aaab-08006ca18354)

#### Principais tópicos relacionados às revisões
Para encontrar os principais tópicos relacionados às revisões, começamos lematizando as palavras do texto. Utilizamos a biblioteca NLTK para isso, especialmente o WordNetLemmatizer, que reduz as palavras à sua forma base. Em seguida, organizamos as palavras lematizadas em uma lista de palavras. 

Após essa etapa, vetorizamos essas palavras utilizando o CountVectorizer do Spark, transformando-as em características vetoriais. Então, aplicamos o modelo de Análise de Tópicos Latentes (LDA) para identificar os tópicos mais relevantes presentes nos dados de revisões. Finalmente, mapeamos os termos mais importantes de cada tópico de volta para as palavras originais usando a função topic_words e exibimos esses resultados em um DataFrame do Pandas para uma melhor visualização e análise:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/2d8eb776-2b72-48ee-b1db-d68f6afd3a11)

### [Distribuições](https://github.com/thomz2/big-data-spark/blob/main/analysis/eiffel_tower/distributions.ipynb)

#### Distribuição temporal das revisões
Para mapearmos a distribuição temporal das revisões, começamos selecionando a coluna createdAt do DataFrame e removendo valores nulos. Ajustamos a política do parser de datas do Spark para "legacy" (importante) e convertemos as datas para o formato yyyy-MM, criando a coluna year_month. Em seguida, agrupamos as revisões por year_month e contamos o número de revisões para cada período, organizando os dados em ordem crescente.

Com os dados agrupados, utilizamos seaborn e matplotlib para criar um gráfico de linhas que mostra a contagem de revisões ao longo do tempo. Esse gráfico revela padrões e sazonalidades nas revisões da Torre Eiffel, permitindo-nos identificar períodos de maior ou menor atividade nos comentários dos visitantes:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/550ddfa4-fc76-4664-9ebc-9e4b6d325152)

#### Distribuição dos sentimentos das revisões
Para analisar a distribuição dos sentimentos das revisões, utilizamos TextBlob para calcular a polaridade do sentimento de cada texto de revisão. Extraímos a coluna text do DataFrame, limpamos os dados convertendo para minúsculas e removendo caracteres não alfabéticos, e aplicamos uma função UDF para determinar a polaridade, que varia de -1 (negativo) a 1 (positivo).

Convertemos o DataFrame resultante para um DataFrame do Pandas e criamos um histograma, o qual nos permite entender melhor a predominância de sentimentos positivos, negativos ou neutros nas reviews:
![image](https://github.com/thomz2/big-data-spark/assets/82160387/c84a36f2-8cde-4eeb-b192-ec2c5ea84af5)
