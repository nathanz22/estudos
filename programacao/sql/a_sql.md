# SQL

SQL (Structured Query Language) é uma linguagem padrão para acessar e manipular bancos de dados.

## RDBMS

*Relational Database Management System* (RDBMS) é um tipo de sistema de banco de dados baseado no modelo relacional. O modelo relacional organiza os dados em tabelas, que são estruturas compostas por linhas (registros) e colunas (campos), sendo as relações entre as tabelas estabelecidas por meio de chaves primárias e estrangeiras.

Os RDBMS são projetados para fornecer uma maneira eficiente e organizada de armazenar, gerenciar e recuperar dados.

**Exemplos de RDBMS:**

* MySQL
* PostgreSQL
* MariaDB
* Oracle Database
* Microsoft SQL Server

## Sintaxe Básica

As declarações em SQL são terminadas em `;`.

**Exemplo:**

``` sql
SELECT * FROM exemple;
```

Uma declação é composta por literais, palavras-chaves e identificadores.

### Literais

Literais são valores explícitos, e em SQL há três tipos:

* Strin
* Numeric
* Binary

#### String

Uma string é cercada por aspas simples.

**Exemplo:**

``` sql
'Hello, World!'
'23'
```

#### Numeric

Representa valores inteiros, decimais ou notação científica.

**Exemplo:**

``` sql
23
13.55
6.21E2
```

#### Binary

Valores binários utilizam a notação `x'0000'`, onde cada dígito é um valor hexadecimal.

**Exemplo:**

``` sql
x'22f'
```

### Palavras-Chaves

Palavras-chaves são palavras reservadas - o que significa que não podem ser usadas para nomear tabelas, colunas, etc - que são usadas para realizar alguma ação.

**Exemplos:**

* `SELECT`
* `INSERT`
* `UPDATE`
* `DELETE`

As palavras-chaves são *case-insensitive*, mas é comum escrevê-las com todas as letras maiúsculas.

### Identificadores

São os objetos especificados, como tabelas, colunas, indexes, etc. Eles são *case-insensitive*, porém é comum escrevê-los em minúsculo.

**Exemplo:**

``` sql
SELECT * FROM identificador;
```

### Comentários

Comentários de linhas são criados a partir de **`--`**.

**Exemplo:**

``` sql
-- Comentário!
```

Comentários de múltiplas linhas são criados a partir de **`/*`** até **`*/`**.

**Exemplo:**

``` sql
/*
Comentário
de
Múltiplas
Linhas
*/
```
