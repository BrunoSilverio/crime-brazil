# :oncoming_police_car: Crime Data in Brazil
O trabalho consiste em uma análise utilizando um dataset obtido no Kaggle, que
é uma comunidade open source de dados e machine learning. O dataset é sobre
crimes registrados no estado de São Paulo e por possuir muitos arquivos de diferentes
anos, escolhemos apenas um arquivo excel de um determinado ano. Os dados foram
separados em três classes, sendo elas Furto, Roubo, Estupro. Os dados estruturados
são ocorrências registradas pela PM (Polícia Militar do Estado de São Paulo). O
conjunto de dados estão inconsistentes, pois algumas vezes os dados demoravam
para serem coletados por completo e também por questões de privacidade. E estão
separados em diversas colunas referentes às características do crime e milhares de
ocorrências.

A tarefa de machine learning foi de tentar encontrar algum padrão em relação aos crimes cometidos com as regiões. E tentar melhorar a visualização do mapa do
estado de São Paulo para organizar e distribuir as patrulhas da PM da forma mais
correta possível.

### Dataset
O dataset usado como base foi ‘Crime Data in Brazil’ é referente aos crimes
ocorridos no estado de São Paulo em um período de 10 anos. São 18 arquivos de
boletins de ocorrência de 2007 até 2016 (BO_2007_1.csv ; BO_2007_2.csv ;
BO_2008_1.csv ; BO_2008_2.csv ; BO_2009_1.csv ; BO_2009_2.csv ; BO_2010_1.csv ;
BO_2010_2.csv ; BO_2011_1.csv ; BO_2011_2.csv ; BO_2012_1.csv ; BO_2012_2.csv ;
BO_2013_1.csv ; BO_2013_2.csv ; BO_2014_1.csv ; BO_2014_2.csv ; BO_2015.csv ;
BO_2016.csv ; RDO_1.csv ; RDO_2.csv ; RDO_3.csv ; RDO_column_description.csv ;
RDO_methodology.txt).

Escolhemos o arquivo do excel ‘BO_2016.csv’, que é composto por 774663
dados (linhas) e possuindo 30 colunas.

Antes de começar a análise do dataset foi feito um pré-tratamento na base de
dados para acomodar à nossas necessidades, sendo ela agrupar os crimes pela
localização.

De início foi diminuído o número de colunas para somente 3, resultando assim
em uma base de dados com as colunas RUBRICA, LONGITUDE e LATITUDE. Após decidir
quais dados seriam usados foi feito um tratamento para retirar todos os dados
inconsistentes, como por exemplo linhas de latitude e longitude preenchidos com
NULL.

Com o dataset limpo e com a garantia que não existe nenhum NULL,
convertemos as coordenadas negativa para positivas, para poder realizar o
agrupamento com k-means, e plotar os gráficos tendo seus eixos positivos.

Por fim foi escolhido entre 39 tipos diferentes de crime registrados, resultando
em apenas três dos crimes no qual consideramos como os mais relevantes e em maior
quantidade, sendo eles, Furto (art. 155), Roubo (art. 157) e Estupro (art. 213). Para fins
de análise foi agrupado todos os subtipos dos crimes referentes ao mesmo crime,
como exemplo furtos denunciados na delegacia e furtos registrados pelo boletim de
ocorrência online, e porque também havia diferentes parágrafos para o mesmo artigo,
um exemplo claro é a divisão dentro do artigo Art. 121 do Código Penal - Decreto Lei
2848/40, referente ao Homicídio, podendo ser separado em Homicídio Simples,
Qualificado, Feminicídio, Culposo, entre outros.

### :warning: Conclusão
Os resultados esperados foram tentar agrupar todos os tipos de crimes
registrados, por facilitar o tratamento e visibilidade dos dados, foi decidido que dos 39
tipos de crime, somente 3 seriam utilizados, sendo eles os mais expressivos, furto,
roubo e estupro.

Com o tratamento e análise dos resultados obtidos, foi percebido que não seria
possível provar de uma forma correta que determinados crimes ocorrem mais em
determinadas regiões do que em outras, porém é possível notar que em certa região
(cluster) a ocorrência de crimes em geral é maior que nas outras.

Não existe um padrão em relação a distribuição dos crimes, o que acaba
fazendo com que não tenha uma concentração de somente um tipo de crime,
resultando em um gráfico com bastante diversidade conforme mostrado nas figuras
acima.

![alt text](https://github.com/BrunoSilverio/crime-brazil/blob/master/plotBase.PNG?raw=true)

![alt text](https://github.com/BrunoSilverio/crime-brazil/blob/master/plotCluster.PNG?raw=true)

![alt text](https://github.com/BrunoSilverio/crime-brazil/blob/master/plotCluster2.PNG?raw=true)

![alt text](https://github.com/BrunoSilverio/crime-brazil/blob/master/plotCluster3.PNG?raw=true)

#### :construction: Referência
- (https://www.kaggle.com/inquisitivecrow/crime-data-in-brazil): Dataset : Crime Data in Brazil
