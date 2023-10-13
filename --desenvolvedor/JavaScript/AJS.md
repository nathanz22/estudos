# JavaScript

JavaScript é uma linguagem de programação focada em desenvolvimento web.

## Tag '`<script>`'

Scripts JavaScript podem ser incorporados à arquivos HTML por meio da tag **`<script>`**.

``` html
<body>
    <h1 id="titulo">Olá, Mundo!</h1>
    <script>
        document.getElementById('titulo').innerHTML = 'Olá, JS!';
    </script>
</body>
```

No exemplo acima, ao invés de ser mostrado o título nível 1 "Olá, Mundo!", será mostrado o título "Olá, JS!".

Podem haver vários scripts, e além disso, scripts podem ser colocados em qualquer lugar do documento HTML, seja no `<body>`, `<head>`, fora deles, ou em ambos.

### JavaScript Externo

São arquivos com a extensão **`.js`**, chamados ainda pela tag **`<script>`**, porém com o atributo `src` (source) com o valor do arquivo que contém o script.

``` js
// Arquivo "meu_script.js"
var elemento = document.getElementById('titulo');
elemento.innerHTML = 'Olá, JS!';
```

``` html
<!-- Arquivo "index.html" -->
<body>
    <h1 id="titulo">Olá, Mundo!</h1>
    <script src="meu_script.js"></script>
</body>
```

## Sintaxe JavaScript

### Declarações

Declarações em JavaScript podem ser terminadas imediatamente com ponto e vírgula ('**`;`**'), possibilitando mais de uma declaração em uma única linha.

``` js
let num1 = 5; let num2 = 10; let num3 = 20;
```

### Identificadores

São usados para nomear variáveis, funções e classes.

Identificadores devem começar com algum dos itens abaixo:

* Uma letra (A-Z ou a-z)
* Um cifrão ("$")
* Um underline ("_")

## Comentários

Para comentários de uma linha, é usado **`//`**.

Tudo que está entre **`/*`** e **`*/`** também é considerado comentário, sendo mais usado em comentário de múltiplas linhas.

``` js
// Isso é um comentário de uma linha

/*
Isso também é um comentário!
*/
```

## Variáveis

Em JavaScript, variáveis precisam ser declaradas com **`var`** ou **`let`** antes do identificador, ou elas se tornam variáveis globais, que nem sempre é necessário.

> Normalmente, os identificadores (nome da variável) são escritos em ***camelCase***.

### Variáveis com '`var`'

Variáveis declaradas com a palavra-chave **`var`** podem ter seu valor reatribuído e a própria variável pode ser declarada novamente.

``` js
var msg; // Declara a variável `msg`
msg = 'Olá, Mundo!'; // Atribui o valor "Olá, Mundo!" à variável `msg`
```

### Variáveis com '`let`'

Variáveis declaradas com a palavra-chave **`let`** são como variáveis declaradas com `var`, porém, elas não podem ser declaradas novamente.

``` js
let msg; // Declara a variável `msg`
msg = 'Olá, Mundo!'; // Atribui o valor "Olá, Mundo!" à variável `msg`

let msg; // Ocorrerá um erro
```

### Variáveis com Inicialização

As variáveis declaradas com `var` ou `let` podem ser inicializas já com um valor atribuído a elas.

``` js
var num1 = 10;
let num2 = 5;
// As variáveis são declaradas ao mesmo tempo que um valor é atribuído a elas.
```

### Declarar Variáveis em Uma Única Linha

Você pode declarar mais de uma variável em uma linha separando-as com vírgula.

``` js
let num1 = 5, num2 = 10, num3 = 20;
```

## Constantes

São declaradas a partir da palavra-chave **`const`**, e são como variáveis, porém com valores constantes, ou seja, que não podem ser alterados.

> Normalmente, os identificadores para as constantes são escritos em letras maiúsculas.

``` js
const MENSAGEM = 'Olá, Mundo!';
```

Diferente das variáveis, as constantes não podem ser declaradas sem atribuir um valor imediatamente.

``` js
const MENSAGEM; // Isto não é permitido
MENSAGEM = 'Olá, Mundo!';
```

## Tipos Primitivos

Em JavaScript, são:

* **String**: Sequência de caracteres.
* **Number**: Números.
* **Boolean**: Valores booleanos (true e false)
* **Null**: Representa um valor nulo ou ausente.
* **Undefined**: Valor de uma variável quando nenhum outro valor for atribuído.
* **Symbol**: São usados como identificadores de propriedades de objetos.
* **BitInt**: Usado para representar números muito grandes.

### Função '`typeof`'

A função '`typeof`' retorna o tipo primitivo de uma variável.

``` js
var str = 'Olá, Mundo!';
var int = 5;
var float = 2.7;

typeof str; // -> 'string'
typeof int; // -> 'number'
typeof float; // -> 'number'
```

## Operadores

### Operadores Aritméticos

* **'`+`'**: Adição.
* **'`-`'**: Subtração.
* **'`*`'**: Multiplicação.
* **'`/`'**: Divisão.
* **'`%`'**: Módulo.
* **'`**`'**: Potenciação.
* **'`++`'**: Incremento.
* **'`--`'**: Decremento.

### Operadores de Comparação

* **'`==`'**: Igual.

    ``` js
    5 == 5;     // -> true
    7 == 2;     // -> false
    8 == '8';   // -> true
    ```

* **'`===`'**: Valor e tipo iguais.

    ``` js
    9 === 9;     // -> true
    5 === 2;     // -> false
    3 === '3';   // -> false
    ```

* **'`!=`'**: Diferente.

    ``` js
    5 != 2;     // -> true
    4 != 5;     // -> true
    4 != '4';   // -> false
    ```

* **'`!==`'**: Diferente em valor e tipo.

    ``` js
    2 !== 3;     // -> true
    5 !== 5;     // -> false
    6 !== '6';   // -> true
    ```

* **'`>`'**: Maior que.

    ``` js
    3 > 2;  // -> true
    5 > 7;  // -> false
    4 > 4;  // -> false
    ```

* **'`<`'**: Menor que.

    ``` js
    2 < 5;  // -> true
    8 < 7;  // -> false
    3 < 3;  // -> false
    ```

* **'`>=`'**: Maior ou igual.

    ``` js
    6 >= 5;  // -> true
    2 >= 7;  // -> false
    4 >= 4;  // -> true
    ```

* **'`<=`'**: Menor ou igual.

    ``` js
    1 <= 2;  // -> true
    2 <= 2;  // -> true
    4 <= 3;  // -> false
    ```

### Operador Ternário

São os operadores **`?`** e **`:`**.

``` js
let idade = 20;
let str = idade >= 18 ? 'Maior de idade' : 'Menor de idade';

console.log(str); // Maior de idade
```

### Operadores Lógicos

* **'`&&`'**: **and**. Verdadeiro se ambos os valores forem verdadeiros.

    ``` js
    (5 > 2 && 2 < 3);   // -> true
    (4 < 7 && 2 < 1);   // -> false
    (3 > 5 && 4 < 9);   // -> false
    ```

* **'`||`'**: **or**. Verdadeiro se pelo menos um dos valores for verdadeiro.

    ``` js
    (1 > 2 || 3 < 5);   // -> true
    (5 > 1 || 2 < 7);   // -> true
    (3 < 2 || 8 > 9);   // -> false
    ```

* **'`!`'**: **not**. Inverte o valor, ou seja, se for verdadeiro se torna falso e vice-versa.

    ``` js
    !(5 > 7);   // -> true
    !(7 < 2);   // -> true
    !(9 > 5);   // -> false
    ```

### Operador de Coalescência Nula

O operador **`??`** retorna o primeiro argumento se a variável ou expressão não for `null` ou `undefined`.

``` js
let str = null;
str = 'Olá, Mundo!' ?? str;

console.log(str); // Output: Olá, Mundo!
```

No exemplo acima, a variável `str` só recebeu o valor "Olá, Mundo!" porque ela era nula antes.

### Operador de Encadeamento Opcional

O operador **`?.`** verifica se o objeto à esquerda não é `null` ou `undefined` antes de tentar acessá-lo. Se o objeto for nulo ou indefinido, é retornado `undefined` em vez de gerar um erro.

``` js
let pessoa = {
    nome: 'Lucas',
    idade: 22,
    altura: 1.76
};

typeof pessoa.nome; // -> string
typeof pessoa.peso; // -> undefined
```
