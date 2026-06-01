# ETL de Dados Excel para PostgreSQL

![Python](https://img.shields.io/badge/Python-3.x-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data_Processing-green)
![ETL](https://img.shields.io/badge/ETL-Pipeline-orange)

## Sobre o Projeto

Este projeto implementa um processo de ETL (Extract, Transform and Load) utilizando Python para extrair dados de planilhas Excel, realizar tratamentos e transformações necessárias e carregar as informações em um banco de dados PostgreSQL.

O pipeline foi desenvolvido para automatizar a carga de informações relacionadas a:

* Fornecedores
* Produtos por filial
* Pedidos de compra
* Entradas de mercadoria
* Vendas

Durante o processo são realizados tratamentos de dados, conversão de datas provenientes do Excel, padronização de informações e validações para evitar duplicidade de registros.

---

## Contexto do Projeto

Este projeto foi desenvolvido com base em uma necessidade real de negócio relacionada à integração e consolidação de dados operacionais para análise e acompanhamento de indicadores.

Por questões de confidencialidade e proteção das informações corporativas, os dados originais não foram disponibilizados neste repositório. Todos os dados utilizados foram substituídos por dados fictícios que reproduzem a mesma estrutura, relacionamentos e regras de negócio do cenário real.

O objetivo desta publicação é demonstrar a implementação de um pipeline ETL completo utilizando Python e PostgreSQL, aplicando conceitos utilizados em ambiente corporativo.

---

## Arquitetura do Processo

```text
Excel (.xlsx)
      │
      ▼
 Extração (Pandas)
      │
      ▼
 Transformação
 ├─ Tratamento de datas
 ├─ Limpeza de dados
 ├─ Conversão de tipos
 ├─ Tratamento de valores nulos
 └─ Regras de negócio
      │
      ▼
 Carga (PostgreSQL)
```

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
├── dados/
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
* Padronização de campos textuais
* Cálculo de quantidade pendente dos pedidos
* Tratamento de inconsistências

### Load

Carga dos dados nas tabelas PostgreSQL:

* fornecedor
* produtos_filial
* pedido_compra
* entradas_mercadoria
* venda

Utilização de `ON CONFLICT DO NOTHING` para evitar registros duplicados durante as cargas.

---

## Configuração

### 1. Clone o repositório

```bash
git clone https://github.com/RafaelaMrtns/etl-postgresql.git
```

### 2. Acesse a pasta do projeto

```bash
cd etl-postgresql
```

### 3. Crie um ambiente virtual

```bash
python -m venv venv
```

### 4. Ative o ambiente virtual

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### 5. Instale as dependências

```bash
pip install -r requirements.txt
```

### 6. Configure o arquivo .env

Crie um arquivo `.env` na raiz do projeto:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=Aula_Fametro
DB_USER=postgres
DB_PASSWORD=sua_senha
```

### 7. Execute o ETL

```bash
python src/etl.py
```

---

## Principais Funcionalidades

* Importação automática de múltiplas planilhas Excel
* Conversão de datas em formato serial do Excel
* Tratamento de valores nulos
* Padronização de dados
* Controle de duplicidade de registros
* Inserção automatizada em PostgreSQL
* Organização do processo em etapas ETL

---

## Resultados

* Automação do processo de carga de dados
* Redução de atividades manuais
* Padronização das informações
* Maior confiabilidade dos dados
* Processo reproduzível e escalável

---

## Competências Demonstradas

* ETL (Extract, Transform and Load)
* Engenharia de Dados
* Python
* Pandas
* PostgreSQL
* Manipulação de arquivos Excel
* Integração de dados
* Qualidade de dados
* Automação de processos

---

## Autor

**Rafaela Martins**

Projeto baseado em uma solução aplicada em ambiente corporativo, adaptado para portfólio utilizando dados fictícios para preservar a confidencialidade das informações.

📌 GitHub: https://github.com/RafaelaMrtns
