# smtx_tst
Teste arquivo ASCII Nasa

Prezado candidato. 
Gostaríamos de fazer um teste que será usado para sabermos a sua proficiência nas habilidades para a vaga. O teste consiste em algumas perguntas e exercícios práticos sobre Spark e as respostas e códigos implementados devem ser armazenados no GitHub. O link do seu repositório deve ser compartilhado conosco ao final do teste. 
Quando usar alguma referência ou biblioteca externa, informe no arquivo README do seu projeto. Se tiver alguma dúvida, use o bom senso e se precisar deixe isso registrado na documentação do projeto. 
Qual o objetivo do comando cache em Spark? 
O objetivo é melhorar o desempenho na execução dos dados.

O mesmo código implementado em Spark é normalmente mais rápido que a implementação equivalente em MapReduce. Por quê?     
Porque o modelo MapReduce representa uma sobrecarga significativa, muitos processamentos realizados com os mesmos dados, sendo lido uma única vez, mas interagindo várias vezes. Diferentemente o Spark executa o processamento em memória, usando RDDs
Qual é a função do SparkContext? 
É um objeto que tem a função de acessar o cluster.

Explique com suas palavras o que é Resilient Distributed Datasets (RDD). 
São blocos de dados resilientes distribuídos, que serve como conjuntos para tolerar falhas de elementos executados em paralelo.

GroupByKey é menos eficiente que reduceByKey em grandes dataset. Por quê? 
No GroupByKey é menos eficiente porque é aplicado diretamente em toda a rede.
Já no reduceByKey a operação de redução é aplicada na primeira partição e 
depois ela é usada na rede, reduzindo o tráfego.

Explique o que o código Scala abaixo faz. 
val textFile = sc.textFile("hdfs://...") 
val counts = textFile.flatMap(line => line.split(" ")) 
.map(word => (word, 1)) 
.reduceByKey(_ + _)
counts.saveAsTextFile("hdfs://...") 

1. Lê o arquivo no diretório do hdfs;
2. O split separa as palavras ao encontrar um espaço vazio, o flatMap transforma o conjunto de linhas em conjuntos de palavras;
3. No map aplica transformação em cada elemento, resultando em vários outros elementos;
4. o reduceByKey serve para achatar os elemtentos para uma dimensão apenas;
5. Por fim, salva o arquivo de texto counts no diretório do hdfs.


HTTP requests to the NASA Kennedy Space Center WWW server 
Fonte oficial do dateset: http://ita.ee.lbl.gov/html/contrib/NASA-HTTP.html 
Dados: 
● Jul 01 to Jul 31, ASCII format, 20.7 MB gzip compressed, 205.2 MB. 
● Aug 04 to Aug 31, ASCII format, 21.8 MB gzip compressed, 167.8 MB. 
Sobre o dataset: Esses dois conjuntos de dados possuem todas as requisições HTTP para o servidor da NASA Kennedy 
Space Center WWW na Flórida para um período específico. 
Os logs estão em arquivos ASCII com uma linha por requisição com as seguintes colunas: 
● Host fazendo a requisição. Um hostname quando possível, caso contrário o endereço de internet se o nome 
não puder ser identificado. 
● Timestamp no formato "DIA/MÊS/ANO:HH:MM:SS TIMEZONE" 
● Requisição (entre aspas) 
● Código do retorno HTTP 
● Total de bytes retornados 
Questões 
Responda as seguintes questões devem ser desenvolvidas em Spark utilizando a sua linguagem de preferência. 
1. Número de hosts únicos. 
2. O total de erros 404. 
3. Os 5 URLs que mais causaram erro 404. 
4. Quantidade de erros 404 por dia. 
5. O total de bytes retornados.

Referências: https://spark.apache.org/docs/latest/index.html
