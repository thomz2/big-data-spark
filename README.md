
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

### Hashtags e Tweets

#### Hashtags mais usadas pela manhã, tarde e noite:
Para identificar as hashtags mais usadas pela manhã, tarde e noite, fazemos uma análise temporal dos tweets, categorizando-os em diferentes períodos do dia (manhã, tarde e noite) com base no horário em que foram postados. 

Em seguida, fazemos a contagem das hashtags mais frequentes em cada período e os resultados são apresentados em gráficos de barras, mostrando as 10 hashtags mais populares em cada período do dia:

#### Hashtags mais usadas em cada dia
A análise das hashtags mais usadas em cada dia é feita através da contagem das hashtags presentes nos tweets de cada dia, agrupadas por data. 

Filtramos os tweets que possuem hashtags, contabilizamos a frequência das hashtags em cada dia e apresentamos os resultados em gráficos de barras, exibindo as 10 hashtags mais utilizadas em cada dia:

#### Número de tweets por hora a cada dia
Calculamos o número de tweets por hora em cada dia, agrupando os tweets por hora do dia e contabilizando a quantidade de tweets em cada período. 

Em seguida, apresentamos os resultados em um gráfico de linha, mostrando a distribuição temporal do número de tweets ao longo das horas do dia:

### Figuras políticas

#### Principais sentenças relacionadas à palavra “Dilma”
Para identificar as principais sentenças relacionadas à palavra "Dilma", carregamos os tweets relacionados à campanha eleitoral do dataset e filtramos aqueles que contêm a palavra-chave "Dilma", após isso, realizamos a limpeza e formatação dos dados, removendo caracteres especiais e stopwords da língua portuguesa. 

Após essa etapa, utilizamos a técnica de n-gramas para identificar sequências de 3 a 5 palavras mais frequentes nos tweets, selecionando dessas, as 10 expressões mais comuns:

#### Principais sentenças relacionadas à palavra “Aécio”
Utilizamos o mesmo processo para identificarmos as principais sentenças relacionadas à palavra "Aécio".

Fizemos isso apenas trocando a constante `WORD` que era `dilma` para `aecio`: