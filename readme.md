## Introdução
Projeto Desenvolvido no Bootcamp de engenharia de dados da DIO. O projeto consistia em realizar a modelagem de dados de um e-commerce com base em uma [planilha](Dados/Financial%20Sample.xlsx) fornecida. O objetivo era criar um Star Schema atendendendo os requisitos do Desafio.


[Instruções do desafio](https://academiapme-my.sharepoint.com/:w:/g/personal/renato_dio_me/EW76WjPAA8RGgC3i44ofFq4BBiWzM-CN5S312YwOQCIwBA?rtime=Byn5PW303Eg)


## Print Star Schema
<img src="Imagem Star Schema/Star Schema.png" alt="">


## Tabelas
### Tabela Financials
É a tabela original do desafio. Mantive caso seja necessário modificar alguma coisa futuramente.


### Tabela FAT_Vendas
É a tabela fato que contém informações referentes a vendas. 


### Tabela DIM_Produto
Conectada com a tabela fato através do ID do produto. Contém informações estátisticas sobre os produtos.


### Tabela DIM_Produto_Detalhes
Conectada com a tabela fato através do ID do produto. Contém informações mais detalhadas sobre os produtos.

### Tabela Dim_Desconto
 Conectada com a tabela fato através do ID do produto. Contém informações referentes ao desconto.

### Tabela DIM_Detalhes:
Contém Informações que restaram das dimensões que podem ser úteis.


Para fazer a conexão da dimensão detalhes com a tabela fato foi criado uma id que é a junção das colunas Product, Country, Segment e Discount Band. A mesma coluna foi criada na tabela fato.

### Tabela DIM_Calendar:
Tabela dimensão criada usando Fórmulas dax.
Comandos DAX na criação da tabela Calendar:

    1- Table Date = CALENDARAUTO(12)


    2-Year = Year('Table Date'[Date])


    3.Day of the week Number = WEEKDAY('Table Date'[Date])


    4.Day of the week Name = Day of the week name = FORMAT('Table Date'[Date],"DDDD")


    5.Month Name = FORMAT(DATE(1,'Table Date'[Month Number],1),"MMM")

