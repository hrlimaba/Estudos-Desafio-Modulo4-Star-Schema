# Estudos-Desafio-Modulo4-Star-Schema
A partir da tabela Financial Sample, será estruturado um modelo Star Schema, com a criação de tabelas fato e dimensão a partir da seleção e organização das colunas relevantes.

EXPLICAÇÃO: 

Com base em uma única tabela disponibilizada, a Financials, serão derivadas novas tabelas utilizando no processo o esquema de modelagem star-schema.


A partir da tabela principal financials_Origem, foram criadas as seguintes tabelas de dimensão e fato:

dim_Produtos, dim_Produtos-Detalhes, dim_Descontos, dim_Detalhes,  Table_Date (*) e fato Vendas.


Em algumas das tabelas criadas foram executados agrupamentos para análise, como por exemplo, soma de unidades vendidas e de valores como médias, medianas e mínimos e máximos relacionado aos preços de vendas dos produtos.

Ex: Tabela dim_Produtos

Além dos agrupamentos, para melhor identificação e relacionamento entre as tabelas, em algumas delas foi criada uma coluna condicional para a coluna Product, onde foram adotados os seguintes valores de saída ou identificação para suas respectivas nomenclaturas existentes:

Product igual a CARRETERA, Saída: 0;

Product igual a MONTANA, Saída: 1

Product igual a PASEO, Saída: 2

Product igual a VELO, Saída: 3

Product igual a VTT, Saída: 4

Product igual a AMARILLA, Saída: 5


(*) Além das tabelas de dimensão criadas, foi criada a tabela calendário Table_Date, sendo também ciada para fins de treinamento a medida denominada Calendar, este processo como medida, não aparecerá como uma tabela visível mas é de grande valia para ser utilizada quando necessária.


Criação da tabela simples Table-Date utilizado na modelagem do desafio:

Campos/Colunas criadas: Year, Month Number, Week Number, Day of the week, Day of the week 2, Month Name e Month Year.

Alguns códigos utilizados para as colunas criadas:

Year = YEAR('Table Date'[Date])

Month Number = MONTH('Tabe Date'[Date])

Week Number = WEEKNUM('Tabe Date'[Date])

Day of the week = WEEKDAY('Tabe Date'[Date])

Day of the week 2 = FORMAT('Tabe Date'[Date], "DDDD")


Criação da medida Calendar:

Parâmetros de início e fim das vendas: Considerado neste desafio o período entre os anos 2013 e 2014.


Código utilizado para o desafio:

Calendar = CALENDAR(DATE(2013,1,1), DATE(2014,12,31))


CONCLUSÃO:

O desafio proposto mostrou a importância de entendermos melhor a estrutura de dados para que possamos executar melhor a modelagem criando o relacionamento entre as tabelas existentes. O objetivo foi transformar um conjunto de tabelas em um modelo dimensional no formato star-schema, identificando a tabela fato, separando as dimensões e garantindo que os relacionamentos sejam preferencialmente 1 → *.
