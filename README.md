# ETL de Dados Excel para PostgreSQL

## Sobre o Projeto

Este projeto realiza um processo de ETL (Extract, Transform and Load) utilizando Python para importar dados de planilhas Excel e carregá-los em um banco de dados PostgreSQL.

O pipeline foi desenvolvido para automatizar a carga de informações relacionadas a:

* Fornecedores
* Produtos por filial
* Pedidos de compra
* Entradas de mercadoria
* Vendas

Durante o processo são realizadas transformações de dados, tratamento de datas provenientes do Excel e validações para evitar duplicidade de registros utilizando `ON CONFLICT`.

---

## Tecnologias Utilizadas

* Python 3.x
* Pandas
* PostgreSQL
* Psycopg2
* Python-dotenv
* OpenPyXL

---

## Estrutura do Projeto

```text
etl-postgresql/
│
├── data/
│   └── base_teste.xlsx
│
├── src/
│   └── etl.py
│
├── .env.example
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Processo ETL

### Extract

Leitura dos dados a partir de múltiplas abas do arquivo Excel:

* fornecedor
* produtos_filial
* pedido_compra
* entradas_mercadoria
* venda

### Transform

Tratamentos realizados:

* Conversão de datas do formato serial do Excel
* Tratamento de valores nulos
* Conversão de tipos de dados
* Cálculo de quantidade pendente nos pedidos de compra
* Padronização de campos textuais

### Load

Carga dos dados nas tabelas PostgreSQL:

* fornecedor
* produtos_filial
* pedido_compra
* entradas_mercadoria
* venda

Utilização de `ON CONFLICT DO NOTHING` para evitar duplicidades.

---

## Configuração

### 1. Clone o repositório

```bash
git clone https://github.com/RafaelaMrtns/etl-postgresql.git
```

### 2. Crie um ambiente virtual

```bash
python -m venv venv
```

### 3. Ative o ambiente virtual

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### 4. Instale as dependências

```bash
pip install -r requirements.txt
```

### 5. Configure o arquivo .env

Crie um arquivo `.env` na raiz do projeto:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=Aula_Fametro
DB_USER=postgres
DB_PASSWORD=sua_senha
```

### 6. Execute o ETL

```bash
python src/etl.py
```

---

## Resultados

* Importação automatizada de múltiplas tabelas
* Tratamento de inconsistências nos dados
* Inserção segura no PostgreSQL
* Processo reproduzível e escalável

---

## Autor

Desenvolvido por Rafaela como projeto de estudo e portfólio em Engenharia de Dados e Análise de Dados.
