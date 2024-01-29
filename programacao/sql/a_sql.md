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

**Principais palavras-chave:**

* **'`SELECT`'**: Consulta de dados.
* **'`INSERT`'**: Inserção de dados.
* **'`UPDATE`'**: Atualização de dados.
* **'`DELETE`'**: Exclusão de dados.
* **'`CREATE TABLE`'**: Criação de tabela.

**Regras:**

* Palavras-chave não são case sensitive, ou seja, `update` é o mesmo que `UPDATE`.

* Na maioria dos sistemas é necessário usar um ponto e vírgula no final de cada declaração.

### Comentários

Comentários são definidos com **`--`**.

**Exemplo:**

``` sql
-- Isso é um comentário
```

## Seleção de Dados

A declaração **`SELECT`** é usada para selecionar dados de um banco de dados.

**Sintaxe:**

``` sql
SELECT coluna1, coluna2, ... FROM nome_tabela;
```

Para selecionar todas as colunas, use `*`:

``` sql
SELECT * FROM nome_tabela;
```

### Declaração `SELECT DISTINCT`

A declaração é **`SELECT DISTINCT`** usada para retornar apenas valores diferentes.

**Sintaxe:**

``` sql
SELECT DISTINCT coluna1, coluna2, ... FROM nome_tabela;
```

Com `SELECT DISTINCT` serão retornados apenas um de cada valor.

## Inserção de Registros

A declaração **`INSERT INTO`** é usada para inserir novos registros em uma tabela.

**Há duas maneiras de declarar um `INSERT INTO`:**

1. Especificando os nomes das colunas e os valores que serão inseridos.

    ``` sql
    INSERT INTO tabela (coluna1, coluna2, ...)
    VALUES (valor1, valor2, ...);
    ```

1. Adicionar valores para todas as colunas da tabela.

    ``` sql
    INSERT INTO tabela VALUES (valor1, valor2, ...)
    ```

    Dessa maneira, a ordem dos valores devem ser a mesma que suas respectivas.

Para inserção em múltiplas linhas:

``` sql
INSERT INTO tabela (coluna1, coluna2, ...)
VALUES
(linha1, linha2, ...),
(linha1, linha2, ...),
(linha1, linha2, ...);
```

## Operadores

### Operadores Lógicos

Os operadores lógicos são:

* **'`AND`'**: Verdadeiro caso ambos os operandos forem verdadeiros.
* **'`OR`'**: Verdadeiro se pelo menos um dos operandos for verdadeiro.
* **'`NOT`'**: Inverte o resultado (se for verdadeiro, se torna falso e vice-versa).

## Filtro de Registros

A cláusula **`WHERE`** é usada para filtrar registros, retornando apenas os registros que correspondem a uma condição específica.

**Sintaxe:**

``` sql
SELECT coluna1, coluna2, ... FROM nome_tabela WHERE condicao;
```

> **OBS.:** `WHERE` pode ser usado com outras declarações além de `SELECT`.

## Organização de Registros

A cláusula **`ORDER BY`** é usada para organizar um conjunto de resultados em ordem crescente ou decrescente.

**Sintaxe:**

``` sql
SELECT coluna1, coluna2, ... FROM tabela
ORDER BY coluna1, coluna2, ... ASC|DESC
```

**`ASC`** significa crescente e **`DESC`** significa decrescente.

O mesmo pode ser feito da seguinda maneira:

``` sql
SELECT coluna1, coluna2, ... FROM tabela
ORDER BY coluna1 ASC, coluna2 DESC, ...;
```

É possível também organizar por colunas.

``` sql
SELECT coluna1, coluna2, ... FROM tabela
ORDER BY coluna1, coluna2, ...
-- Organiza primeiro pela `coluna1` e depois pela `coluna2`
```

## Alteração de Registros

A declaração **`UPDATE`** altera um registro existente na tabela.

**Sintaxe:**

``` sql
UPDATE tabela
SET coluna1 = valor1, coluna2 = valor2, ...
WHERE condicao;
```

* **'`UPDATE`'**: Modifica os dados em registros existentes.
* **'`SET`'**: Especifica quais colunas serão atualizados.
* **'`WHERE`'**: Condição para definir quais registros serão atualizados.

> **OBS.:** Se omitir a cláusula `WHERE`, todos os registros serão alterados.

## Exclusão de Registros

A declaração **`DELETE`** exclui um registro na tabela.

**Sintaxe:**

``` sql
DELETE FROM tabela WHERE condicao;
```

> **NOTA:** Omitir a cláusula `WHERE` resultará na exclusão de todos os registros.

## Exclusão de Tabela

Para excluir uma tabela completamente, é utilizado **`DROP TABLE`**.

**Sintaxe:**

``` sql
DROP TABLE tabela;
```

## Restrições

Uma ***constraint*** é uma regra ou condição aplicada a uma ou mais colunas de uma tabela para garantir a integridade dos dados armazenados.

**Os tipos de *constraint* são:**

* **`PRIMARY KEY`**
* **`UNIQUE`**
* **`NOT NULL`**
* **`CHECK`**
* **`DEFAULT`**

### Chave Primária

Uma chave primária é um campo ou uma combinação de campos que identifica de forma exclusiva cada registro em uma tabela. A chave primária não pode conter valores nulos e deve ser única para cada registro na tabela.

**Uma chave principal é:**

* **Unicidade**: A chave primária garante que cada valor na coluna (ou combinação de colunas) seja único em toda tabela. Nenhum outro registro pode ter o mesmo valor na chave primária.
* **Não Nulidade**: A chave primária garante que os valores na coluna (ou combinação de colunas) não sejam nulos.

**Sintaxe:**

``` sql
CREATE TABLE NomeTabela (
    coluna1 tipo PRIMARY KEY,
    coluna2 tipo,
    coluna3 tipo
);
```

Acima, apenas a primeira coluna é uma chave primária.

> **NOTA:** Em uma tabela só pode haver uma chave primária.

### `UNIQUE`

Colunas únicas podem possuir diferentes valores para cada linha, podendo esses valores ser nulos ou não. Uma coluna única é semelhante a uma chave primária, com as exceções que em uma tabela podem haver várias colunas únicas, e essas colunas podem ser nulas.

**Sintaxe:**

``` sql
CREATE TABLE NomeTabela (
    coluna1 tipo,
    coluna2 tipo UNIQUE,
    coluna3 tipo UNIQUE
);
```

Acima, `coluna2` e `coluna3` são colunas únicas. Isso significa que cada valor nessas colunas deve ser único em toda a tabela, e essas colunas podem conter valores nulos.

### `NOT NULL`

Define que o valor da coluna não deve ser nulo.

**Sintaxe:**

``` sql
CREATE TABLE NomeTabela (
    coluna1 tipo NOT NULL,
    coluna2 tipo NOT NULL,
    coluna3 tipo NOT NULL,
)
```

Acima, as três colunas não aceitam o valor nulo.

### `CHECK`

Define uma condição que os valores de uma coluna devem atender.

**Sintaxe:**

``` sql
CREATE TABLE NomeTabela (
    coluna1 tipo CHECK (CONDICAO)
    coluna2 tipo CHECK (CONDICAO)
    coluna3 tipo CHECK (CONDICAO)
);
```

Acima, as três colunas aceitam uma condição.

### `DEFAULT`

Define um valor padrão para para a coluna caso um outro valor não seja definido.

**Sintaxe:**

``` sql
CREATE TABLE NomeTabela (
    coluna1 tipo DEFAULT valor_padrao,
    coluna2 tipo DEFAULT valor_padrao,
    coluna3 tipo DEFAULT valor_padrao,
)
```

## Funções Agregadas

As ***aggregate functions*** são funções que realizam uma operação em um conjunto de valores e retornam um único valor resumido.

**Principais funções agregadas:**

* **'`COUNT()`'**: Conta o número de linhas em um conjunto de resultados.

    ``` sql
    SELECT COUNT(*) FROM tabela;
    ```

* **'`SUM()`'**: Calcula a soma de valores em uma coluna.

    ``` sql
    SELECT SUM(coluna) FROM tabela;
    ```

* **'`AVG()`'**: Calcula a média dos valores em uma coluna.

    ``` sql
    SELECT AVG(coluna) FROM tabela;
    ```

* **'`MAX()`'**: Analisa qual é o valor máximo em uma coluna.

    ``` sql
    SELECT MAX(coluna) FROM tabela;
    ```

* **'`MIN()`'**: Analisa qual é o valor mínimo em uma coluna.

    ``` sql
    SELECT MIN(coluna) FROM tabela;
    ```

* **'`ROUND()`'**: Arredonda um número para o número inteiro mais próximo ou para um número específico de casas decimais.

    ``` sql
    SELECT ROUND(numero, casas_decimais);
    ```
