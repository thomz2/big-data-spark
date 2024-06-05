
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

### Figuras Políticas

#### Principais sentenças relacionadas à palavra “Dilma”
Para identificar as principais sentenças relacionadas à palavra "Dilma", carregamos os tweets relacionados à campanha eleitoral do dataset e filtramos aqueles que contêm a palavra-chave "Dilma", após isso, realizamos a limpeza e formatação dos dados, removendo caracteres especiais e stopwords da língua portuguesa. 

Após essa etapa, utilizamos a técnica de n-gramas para identificar sequências de 3 a 5 palavras mais frequentes nos tweets, selecionando dessas, as 10 expressões mais comuns:

#### Principais sentenças relacionadas à palavra “Aécio”
Utilizamos o mesmo processo para identificarmos as principais sentenças relacionadas à palavra "Aécio".

Fizemos isso apenas trocando a constante `WORD` que era `dilma` para `aecio`:

## 🗼 Reviews Relacionados à Visita da Torre Eiffel em Paris

### Palavras e Expressões

#### Palavras mais utilizadas nas avaliações
Para encontrar as palavras mais utilizadas nas avaliações, nós seguimos um processo sistemático de limpeza e análise de texto. Primeiro, carregamos os dados das avaliações, focando nas colunas de título e texto. Removemos quaisquer valores ausentes para garantir a integridade dos dados. Em seguida, realizamos a limpeza das colunas, removendo caracteres especiais e mantendo apenas letras e números.

Depois disso, tokenizamos o texto, transformando as frases em listas de palavras individuais. Para aumentar a precisão da análise, removemos as palavras comuns (stop words) que geralmente não carregam muito significado, como "e", "de", "a", etc. Em seguida, usamos a função explode para separar cada palavra em uma linha própria. Contamos a frequência de cada palavra usando a função groupBy e ordenamos os resultados em ordem decrescente de frequência. Por fim, plotamos as 10 palavras mais frequentes em um gráfico de barras:

#### Expressões mais usadas nas avaliações
Para encontrar as expressões mais usadas nas avaliações, começamos com o mesmo processo de limpeza e tokenização usado para as palavras individuais. Em seguida, criamos n-grams para identificar expressões comuns.

Depois de gerar essas expressões, explodimos as listas de n-grams, assim como fizemos com as palavras individuais, para que cada expressão tivesse sua própria linha. Agrupamos essas expressões e contamos a frequência de cada uma, ordenando-as em ordem decrescente de contagem. Combinamos os resultados de n-grams de textos e títulos, agrupamos novamente e somamos as frequências para obter as expressões mais frequentes no conjunto de dados completo. Finalmente, apresentamos as 10 expressões mais usadas em um gráfico de barras:

#### Principais tópicos relacionados às revisões
Jaja sai

### Distribuições

#### Distribuição temporal das revisões
Para mapearmos a distribuição temporal das revisões, começamos selecionando a coluna createdAt do DataFrame e removendo valores nulos. Ajustamos a política do parser de datas do Spark para "legacy" (importante) e convertemos as datas para o formato yyyy-MM, criando a coluna year_month. Em seguida, agrupamos as revisões por year_month e contamos o número de revisões para cada período, organizando os dados em ordem crescente.

Com os dados agrupados, utilizamos seaborn e matplotlib para criar um gráfico de linhas que mostra a contagem de revisões ao longo do tempo. Esse gráfico revela padrões e sazonalidades nas revisões da Torre Eiffel, permitindo-nos identificar períodos de maior ou menor atividade nos comentários dos visitantes:

#### Distribuição dos sentimentos das revisões
Para analisar a distribuição dos sentimentos das revisões, utilizamos TextBlob para calcular a polaridade do sentimento de cada texto de revisão. Extraímos a coluna text do DataFrame, limpamos os dados convertendo para minúsculas e removendo caracteres não alfabéticos, e aplicamos uma função UDF para determinar a polaridade, que varia de -1 (negativo) a 1 (positivo).

Convertemos o DataFrame resultante para um DataFrame do Pandas e criamos um histograma, o qual nos permite entender melhor a predominância de sentimentos positivos, negativos ou neutros nas reviews: