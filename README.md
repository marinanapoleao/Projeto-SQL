# Análise de Banco de Dados de Vendas com SQL


### Contexto do negócio:
Uma empresa possui uma base de vendas e deseja obter rapidamente informações sobre seus pedidos, produtos e indicadores de vendas para apoiar a tomada de decisões comerciais.


### Objetivo:	Demonstrar conhecimentos fundamentais em SQL por meio da consulta e análise de uma base de vendas utilizando SQLite.

- Manipulação de bancos de dados relacionais;
- Extração de informações utilizando SQL;
- Construção de indicadores analíticos;
- Integração entre Python e SQLite;
- Aplicação de funções de agregação para geração de métricas de negócio.


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


### Principais Consultas SQL:

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


# Projeto Final do Aprofundamento de Analytics
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/7c124977-1552-47f6-98b8-2b3acb81f9c5" />

### Contexto do negócio: 
Uma empresa de e-commerce possui duas bases de dados separadas: uma contendo informações cadastrais dos clientes e outra registrando as transações realizadas. Antes da construção de dashboards e análises gerenciais, é necessário consolidar essas informações em uma única base consistente, identificar registros sem correspondência e preparar os dados para consumo em ferramentas de Business Intelligence.

### Objetivo: 
- Integrar dados provenientes de diferentes tabelas;
- Identificar registros inconsistentes;
- Analisar clientes sem transações;
- Analisar transações sem cadastro correspondente;
- Gerar uma base consolidada;
- Preparar os dados para visualização em Power BI.

### LINGUAGENS E BIBLIOTECAS
- Python
- SQLite
- SQL
- Pandas
- Jupyter Notebook

### Tratamento dos Dados:
- União das bases por chave (id_client);
- Identificação de valores nulos;
- Separação de registros inconsistentes;
- Criação da base consolidada;
- Exportação para CSV.

### Principais Consultas SQL:
- #### Visualização das tabelas
  SELECT *
  FROM TB_CLIENTES

  SELECT *
  FROM TB_TRANSACOES

- #### Consolidação das tabelas:
  query_completa = """
  SELECT DISTINCT
  A.*,
  B.*
  FROM TB_CLIENTES AS A
  FULL JOIN TB_TRANSACOES AS B
  ON A.id_client = B.id_client
  """
  df_completa = run_query(query_completa)
  print(df_completa)

### Identificação de inconsistências:
- Clientes sem compras;
- Compras sem cliente cadastrado;
- Registros completos.
