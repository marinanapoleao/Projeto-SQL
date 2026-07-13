


# Análise de Banco de Dados de Vendas com SQL


### Objetivo:	Demonstrar conhecimentos fundamentais em SQL por meio da consulta e análise de uma base de vendas utilizando SQLite.

- Manipulação de bancos de dados relacionais;
- Extração de informações utilizando SQL;
- Construção de indicadores analíticos;
- Integração entre Python e SQLite;
- Aplicação de funções de agregação para geração de métricas de negócio.


### Problema de negócio: Uma empresa possui uma base de vendas e deseja obter rapidamente informações sobre seus pedidos, produtos e indicadores de vendas para apoiar a tomada de decisões comerciais.

### LINGUAGENS E BIBLIOTECAS
- Python
- SQLite
- SQL
- Pandas
- Jupyter Notebook


### BASE DE DADOS

A tabela principal é: TB_VENDAS

Possui as colunas: 
- ID_COMPRA
- ID_CLIENTE
- PRODUTO
- VALOR_UNID
- UNIDADES


### CONSULTAS REALIZADAS:

- #### Consulta completa:
  SELECT *
  FROM TB_VENDAS;

- #### Limitação de registros:
  SELECT PRODUTO
  FROM TB_VENDAS
  LIMIT 10;

- #### Média de indicadores:
  SELECT
  AVG(VALOR_UNID) AS MEDIA_VALOR_UNID,
  AVG(UNIDADES) AS MEDIA_UNIDADES
  FROM TB_VENDAS;

- #### Média de indicadores:
  SELECT
  AVG(VALOR_UNID) AS MEDIA_VALOR_UNID,
  AVG(UNIDADES) AS MEDIA_UNIDADES
  FROM TB_VENDAS;

- #### Criação de coluna calculada:
  SELECT
  ID_COMPRA,
  ID_CLIENTE,
  VALOR_UNID * UNIDADES AS Valor_Total_Gasto
  FROM TB_VENDAS;

- #### Média do valor gasto:
  SELECT
  AVG(VALOR_UNID * UNIDADES) AS Media_Total_Gasto
  FROM TB_VENDAS;


### COMPETÊNCIAS DEMONSTRADAS

* SQL
* SQLite
* Banco de Dados Relacional
* Consultas SQL
* Funções de agregação
* Cálculos em SQL
* Manipulação de dados
* Integração SQL + Python
* Análise de Dados
