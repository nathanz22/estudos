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

### Declaração Múltipla de Variáveis

Você pode declarar mais de uma variável em uma linha separando-as com vírgula.

``` js
let num1 = 5, num2 = 10, num3 = 20;
```

## Constantes

São declaradas a partir da palavra-chave **`const`**, e são como variáveis, porém com valores constantes, ou seja, que não podem ser alterados.

> Normalmente, os identificadores para as constantes são escritos em letras MAIÚSCULAS.

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
* **Object**: Armazena propriedades e métodos.

### Função '`typeof`'

A função '`typeof`' retorna o tipo primitivo de uma variável.

``` js
let str = 'Olá, Mundo!';
let int = 5;
let float = 2.7;

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

São os operadores **'`?`'** e **'`:`'**.

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

#### Operadores Lógicos de Atribuição

* **'`&&=`'**: Se o primeiro valor for verdadeiro, o segundo valor é atribuído.

    ``` js
    let x = 5;
    x &&= 10; // -> 10
    ```

* **'`||=`'**: Se o primeiro valor for falso, o segundo valor é atribuído.

    ``` js
    let x = 5;
    x ||= 10; // -> 5
    ```

### Operador de Coalescência Nula

O operador **`??`** retorna o primeiro argumento se a variável ou expressão não for `null` ou `undefined`.

``` js
let str = null;
str = 'Olá, Mundo!' ?? str;

console.log(str); // Output: Olá, Mundo!
```

No exemplo acima, a variável `str` só recebeu o valor "Olá, Mundo!" porque ela era nula antes.

#### Operador de Coalescência Nula de Atribuição

O operador **`??=`** verifica se o primeiro valor é nulo ou indefinido, e se for, atrubui o segundo valor.

``` js
let x;
x ??= 10; // -> 10
```

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

## Strings

Podem ser escritas entre aspas simples ou duplas:

``` js
let str1 = 'Olá, Mundo!';
let str2 = "Olá, JS!";
```

### Largura de uma String

A propriedade `length` tem como valor a largura da string.

``` js
let str = 'Olá, Mundo!';
console.log(str.length); // Output: 11
```

### Quebra de Linhas Longas

Se um linha ficar muito longa, a melhor abordagem é fazer a quabra de linha em um operador:

``` js
document.getElementById('elemento').innerHTML =
'Olá, Mundo!';
```

Caso seja necessário quebrar de linha durante uma string, pode-se usar **`\`**.

``` js
let str = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmn\
opqrstuvwxyz1234567890';
```

### Métodos de String

* **'`toUpperCase()`'**: Retorna a string com todos os caracteres em maiúsculo.

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.toUpperCase());
    // Output: OLÁ, MUNDO!
    ```

* **'`toLowerCase()`'**: Retorna a string com todos os caracteres em minúsculo.

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.toLowerCase());
    // Output: olá, mundo!
    ```

* **'`charAt()`', `[]`**: Retorna o caractere da posição especificada.

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.charAt(0)); // Output: O
    console.log(str.charAt(1)); // Output: l
    console.log(str.charAt(2)); // Output: á

    // Ou

    console.log(str[0]) // Output: O
    console.log(str[1]) // Output: l
    console.log(str[2]) // Output: á
    ```

    Caso o índice não corresponda a nenhum caractere, o método **`charAt()`** retorna uma string vazia, já **`[]`** retorna `undefined`.

* **'`charCodeAt()`'**: Retorna o unicode do caractere que pertence ao índice especificado.

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.charCodeAt(0)); // 79
    console.log(str.charCodeAt(1)); // 108
    console.log(str.charCodeAt(2)); // 225
    ```

* **'`includes()`'**: Retorna `true` se a substring existir em qualquer lugar da string, ou `false`, caso não exista.

    São dois parâmetros:

    1. A substring a ser procurada.
    1. A posição em que a substring passada deve começar a ser procurada. (opcional)

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.includes('Olá'));       // Output: true
    console.log(str.includes('Olá', 3));    // Output: false
    ```

* **'`indexOf()`'**: Retorna a posição da primeira ocorrência da substring especificada.

    São aceitos dois argumentos:

    1. Substring a ser encontrada dentro da string.
    1. Posição que a substring deve começar a ser procurada. (opcional)

    ``` js
    let str = 'Olá, Mundo!';
    console.log(str.indexOf('M')); // Output: 5
    ```

    Caso a substring não exista dentro da string, irá retornar -1.

* **'`lastIndexOf()`'**: Retorna a posição do início da substring especificada dentro da string da direita para a esquerda.

    1. Substring a ser encontrada dentro da string.
    1. Posição que a substring deve começar a ser procurada. (opcional)

    ``` js
    let str = 'olá, mundo!';
    console.log(str.lastIndexOf('o')); // Output: 9
    ```

    Caso a substring não exista dentro da string, irá retornar -1.

* **'`replace()`'**: Substitui uma ocorrência na string por uma substring.

    São dois argumentos:

    1. Substring que vai ser substituída.
    1. Substring que vai substituir.

    ``` js
    let str = 'Olá, Mundo!';
    console.log(str.replace('Mundo', 'JS')); // Output: Olá, JS!
    ```

    Por padrão, o método `replace()` substitui apenas a primeira ocorrência de uma substring. Para substituir todas as ocorrências, será necessário utilizar expressão regular com o sinalizador `/g` (*global match*).

    ``` js
    let str = 'Olá, Mundo! Adeus, Mundo!';
    let newStr = str.replace(/Mundo/g, 'JS');
    console.log(newStr);
    // Output: Olá, JS! Adeus, JS!
    ```

* **'`search()`'**: É usado para pesquisas dentro da string, permitindo o uso de RegExp.

    ``` js
    let str = 'olá, Mundo!';
    let letraMaiuscula = /[A-Z]/g;
    let ponto = /[.]/g;

    console.log(str.search(letraMaiuscula));
    // Retorna 5, pois é o índice da primeira letra maiúscula

    console.log(str.search(ponto));
    // Retorna -1, pois não conseguiu encontrar um ponto na string
    ```

* **'`match()`'**: Retorna um array que contém o resultado de todas as ocorrências de uma substring ou expressão regular dentro da string.

    ``` js
    let str = 'O sol se põe no horizonte dourado, num abraço apertado, colorindo o céu de encantado';
    console.log(str.match(/do/g));
    // Output: [ 'do', 'do', 'do', 'do', 'do' ]
    ```

* **'`startsWith()`'**: Retorna `true` se a substring especificada esteja no começo da string, ou `false`, em caso contrário.

    São dois argumentos:

    1. A substring a ser procurada.
    1. A posição que deve se iniciar a procura pela substring especificada no primeiro argumento. (opcional)

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.startsWith('Olá'));     // Output: true
    console.log(str.startsWith('Olá', 3));  // Output: false
    ```

* **'`endsWith()`'**: Retorna `true` caso a substring especificada esteja ao fim da string, ou `false`, em caso contrário.

    São dois argumentos:

    1. A substring a ser procurada.
    1. A posição final na qual se espera que o argumento anterior seja encontrado. (opcional)

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.endsWith('Mundo!'));     // Output: true
    console.log(str.endsWith('Mundo!', 3));  // Output: false
    ```

* **'`concat()`'**: Concatena duas ou mais strings.

    ``` js
    let str1 = 'Olá, ';
    let str2 = 'Mundo!';

    console.log(str1.concat(str2)); // Output: Olá, Mundo!
    ```

* **'`trim()`'**: Retorna uma string sem os possíveis espaços em branco no início ou no fim da string.

    ``` js
    let str = '     Olá, Mundo!     ';

    console.log(str.trim());
    // Output: Olá, Mundo!
    ```

    Existem também os métodos **`trimStart()`**, que remove os espaços em branco apenas do início, e **`trimEnd()`**, que removem os espaços em branco apenas do fim da string.

* **'`split()`'**: Cria um array com a string a partir de um separador.

    Recebe dois argumentos:

    1. Separador.
    1. Limite de itens do array. (opcional)

    ``` js
    let str = 'É mais fácil lidar com uma má consciência do que com uma má reputação';

    console.log(str.split(' '));
    /*
    Output:
    [
        'É',     'mais',
        'fácil', 'lidar',
        'com',   'uma',
        'má',    'consciência',
        'do',    'que',
        'com',   'uma',
        'má',    'reputação'
    ]
    */

    console.log(str.split(' ', 3));
    // Output: [ 'É', 'mais', 'fácil' ]
    ```

* **'`slice()`'**: Retorna uma nova string a partir da string original, começando e/ou terminando em índices específicos.

    Seus argumentos são:

    1. Início (opcional)
    2. Fim (opcional)

    Se não houver nenhum dos dois argumentos, será retornada a string original.

    ``` js
    let str = 'É mais fácil lidar com uma má consciência do que com uma má reputação';

    console.log(str.slice(2));
    // Output: mais fácil lidar com uma má consciência do que com uma má reputação

    console.log(str.slice(0, 12));
    // Output: É mais fácil

    console.log(str.slice());
    // Output: É mais fácil lidar com uma má consciência do que com uma má reputação
    ```

* **'`substring()`'**: É parecido com o `slice()`, porém não permite valores negativos e, se caso o segundo argumento for maior que o primeiro, ele inverterá os argumentos.

    ``` js
    let str = 'Olá, Mundo!';
    console.log(str.substring(6, 0));
    // Output: Olá, M
    ```

* **'`padStart()`', '`padEnd()`'**: São métodos de preenchimento para o início e fim, respectivamente. Eles preenchem a string no começo ou fim com uma substring até que a string tenha um determinado comprimento.

    Para ambos os métodos, são dois argumentos:

    1. Comprimento que a string terá no total.
    1. Substring que irá preencher o espaço que resta para a string atingir o comprimento total.

    ``` js
    let str = ' Olá, Mundo! ';
    console.log(str.padStart(15, '-'));
    // Output: --- Olá, Mundo!

    console.log(str.padEnd(16, '-'));
    // Output:  Olá, Mundo! ---
    ```

* **'`repeat()`'**: Retorna uma nova string que repete o texto da string original determinadas vezes.

    ``` js
    let str = 'Olá, Mundo!';

    console.log(str.repeat(2));
    // Output: Olá, Mundo!Olá, Mundo!
    ```

* **'`fromCharCode()`'**: Retorna uma nova string criada a partir de uma sequência específica de valores Unicode.

    ``` js
    console.log(String.fromCharCode(65, 66, 67));
    // Output: ABC
    ```

* **'`fromCodePoint()`'**: Retorna uma nova string criada a partir de uma sequência específica de pontos de código.

    ``` js
    console.log(String.fromCodePoint(65, 66, 67));
    // Output: ABC
    ```

### Template String

Também chamadas de **Template Literals**, são strings que ficam entre crases ao invés de aspas. Elas permitem algumas coisas:

* String de Múltiplas Linhas:

    ``` js
    let str = `Olá,
    Mundo!`;
    console.log(str); // Output: Olá, Mundo! (mantém a quebra de linha)
    document.write(str); // Output: Olá, Mundo! (sem a quebra de linha)
    ```

* Interpolação:

    Variáveis ou expressões devem ser inseridas dentro de chaves, que sucessedem um cifrão (**`${}`**).

    ``` js
    let num1 = 5;
    let num2 = 7;
    let str = `${num1} + ${num2} = ${num1 + num2}`;
    console.log(str); // Output: 5 + 7 = 12
    ```

## Números

Em JavaScript, existe apenas um tipo de número, que pode ser escrito com ou sem casas decimais.

``` js
let x = 10;     // Número sem casas decimais
let y = 5.31;   // Número com casas decimais
```

### NaN

Significa Not a Number - em português "Não é um Número" - e é um valor retornado quando ocorre a tentativa de uma expressão matemática onde algum valor não é um número.

``` js
console.log(5 / 'Olá, Mundo!'); // Output: NaN
```

Porém, o JavaScript sempre tenta converter os valores para números em expressões matemáticas.

``` js
console.log(5 / '2'); // Output: 2.5
```

> Se o operador `+` for utilizado nesse caso, ocorrerá a concatenação.
>
> ``` js
> console.log(5 + '2'); // Output: 52
> ```

NaN é do tipo `number`.

``` js
console.log(typeof NaN); // Output: number
```

#### Função '`isNaN()`'

Esta função retorna `true` ou `false` dependendo se o valor passado for ou não um número.

``` js
console.log(isNaN(5));      // Output: false
console.log(isNaN('2'));    // Output: false
console.log(isNaN(7.9));    // Output: false
console.log(isNaN(-23));    // Output: false
console.log(isNaN('Olá'));  // Output: true
```

### Infinity

Valores infinitos são os maiores valores possíveis.

``` js
let num = 2;
while (num != Infinity) {
    num *= num;
}
console.log(num); // Output: Infinity
```

Infinity também é gerado quando há uma divisão por zero.

``` js
console.log(10 / 0); // Output: Infinity
```

Comparação com um número não infinito:

``` js
let valor1 = Infinity;
let valor2 = 100;

console.log(valor1 > valor2); // Output: true
```

Infinity é do tipo `number`.

``` js
console.log(typeof Infinity); // Output: number
```

### Bases Numéricas

Para converter números para outras bases numéricas, como hexadecimal ou binário, você pode utilizar o método `toString()`, que recebe como argumento a base numérica para qual o número será convertido.

``` js
let num = 22;

console.log(num.toString(2));   // Output: 10110
console.log(num.toString(8));   // Output: 26
console.log(num.toString(10));  // Output: 22
console.log(num.toString(16));  // Output: 16
console.log(num.toString(32));  // Output: m
```

Para representar as principais bases numéricas, deve-se utilizar prefixos:

* Binário: **`0b`**

    ``` js
    let num = 0b10110;
    console.log(num); // Output: 22
    ```

* Octal: **`0o`**

    ``` js
    let num = 0o26;
    console.log(num); // Output: 22
    ```

* Hexadecimal: **`0x`**

    ``` js
    let num = 0x16;
    console.log(num); // Output: 22
    ```

### Números Muito Grandes ou Muito Pequenos

Podem ser escritos utilizando notação científica.

``` js
console.log(5e5);       // Output: 500000
console.log(5e-5);      // Output: 0.00005

console.log(-2.5e5);    // Output: -200000
console.log(-2.5e-5);   // Output: -0.000025
```

### BigInt

Os números inteiros maiores que 15 dígitos são muito grandes, e por conta disso, perdem precisão.

``` js
let num1 = 999999999999999;
let num2 = 9999999999999999;

console.log(num1); // Output: 999999999999999
console.log(num2); // Output: 10000000000000000
```

Números do tipo BigInt(para números muito grandes) podem ser criados de duas formas:

* Acrescentando `n` ao fim do número.

    ``` js
    let x = 9999999999999999n;
    ```

* Chamando o construtor BigInt.

    ``` js
    let x = BigInt(9999999999999999);
    ```

Há uma diferença no resultado dependendo da maneira que foi criado o BigInt.

``` js
let x = 9999999999999999n;
let y = BigInt(9999999999999999);

console.log(x); // Output: 9999999999999999n
console.log(y); // Output: 10000000000000000n
```

Características do BigInt:

* Só podem ocorrer operações entre números do mesmo tipo (não é possível fazer operações entre `number` e `BigInt`).
* Não podem possuir casas decimais.
* Não permite o uso do operador `>>>`.

### Métodos de Números

* **'`toString()`'**: Retorna o número como string.

    ``` js
    let myBigInt = 21931321931212131231n;
    let myNumber = 311;

    console.log(typeof myBigInt.toString()); // Output: string
    console.log(typeof myNumber.toString()); // Output: string
    ```

    Como já dito anteriormente, este método pode receber como argumentos uma base de conversão para o número.

    ``` js
    let myBigInt = 21931321931212131231n;
    let myNumber = 311;

    console.log(myBigInt.toString(2));
    // Output:10011000001011011101101010001100101101100101000100000101110011111

    console.log(myNumber.toString(8)); // Output: 467
    ```

* **'`toExponential()`'**: Retorna uma string com o número representado em notação exponencial. Pode ser aplicando somente a números de ponto flutuante, ou seja, que possuem casas decimais.

    Pode receber um argumento, que deve ser numérico e define a quantidade de casas decimais que deverão ser incluídas na parte fracionária do número exponencial. Este argumento é opcional, e se omitido, o número será representado com o máximo de precisão possível.

    ``` js
    let x = 12345.6789;

    console.log(x.toExponential());     // Output: 1.23456789e+4
    console.log(x.toExponential(2));    // Output: 1.23e+4
    ```

* **'`toFixed()`'**: Retorna uma string com um número escrito com um número específico de casas decimais.

    ``` js
    let x = 50.231;

    console.log(x.toFixed(1)); // Output: 50.2
    console.log(x.toFixed(2)); // Output: 50.23
    console.log(x.toFixed(3)); // Output: 50.231
    ```

* **'`toPrecision()`'**: Retorna uma string com um número escritos com um número específico.

    ``` js
    let x = 50.231;

    console.log(x.toPrecision());  // Output: 50.231
    console.log(x.toPrecision(1)); // Output: 5e+1
    console.log(x.toPrecision(2)); // Output: 50
    console.log(x.toPrecision(3)); // Output: 50.2
    console.log(x.toPrecision(4)); // Output: 50.23
    console.log(x.toPrecision(5)); // Output: 50.231
    ```

    Se não receber nenhum argumento, retorna o próprio número como string.

* **'`valueOf()`'**: Converte o valor de um objeto `number` para um valor numérico primitivo.

    ``` js
    let x = new Number(55);

    console.log(x.valueOf());        // Output: 55
    console.log(typeof x.valueOf()); // Output: number
    ```

    Também pode ser usado para mostrar valores de expressões numéricas:

    ``` js
    console.log((512 + 7).valueOf()); // Output: 519
    ```

### Funções Que Convertem Para Número

* **'`Number()`'**: Converte seu argumento em número.

    ``` js
    let x = Number('22');

    console.log(x);        // Output: 22
    console.log(typeof x); // Output: number
    ```

    Esta função pode converter também valores booleanos para número, sendo `true` igual a 1 e `false` igual a 0.

    ``` js
    console.log(Number(true));  // Output: 1
    console.log(Number(false)); // Output: 0
    ```

    Pode tranquilamente converter números entre espaços em branco no começo ou fim da string.

    ``` js
    console.log(Number('   10'));  // Output: 10
    console.log(Number('502   ')); // Output: 502
    ```

    Caso seja passado uma string não numérica, será retornado `NaN`.

    ``` js
    console.log(Number('Olá, Mundo!')) // Output: NaN
    ```

* **'`parseInt()`'**: Converte seu argumento para um número inteiro.

    ``` js
    console.log(parseInt('55')); // Output: 55
    console.log(parseInt(21.6)); // Output: 21
    ```

* **'`parseFloat()`'**: Converte seu argumento para um número.

    ``` js
    console.log(parseFloat('55'));   // Output: 55
    console.log(parseFloat('62.5')); // Output: 62.5
    ```

* **'`isFinite()`'**: Retorna `true` se seu argumento for um número finito, ou `false` caso não for.

    ``` js
    console.log(Number.isFinite(23));       // Output: true
    console.log(Number.isFinite(Infinity)); // Output: false
    ```

* **'`isNaN`'**: Retorna `true` se seu argumento for `NaN`, ou `false` em caso contrário.

    ``` js
    console.log(isNaN(62 + 'a')); // Output: true
    console.log(isNaN(19 + 512)); // Output: false
    ```

### Métodos do Objeto `Number`

* **'`Number.isInteger()`'**: Retorna `true` se seu argumento for um número inteiro, ou `false`, caso não for.

    ``` js
    console.log(Number.isInteger(55));      // Output: true
    console.log(Number.isInteger(7.7));     // Output: false
    console.log(Number.isInteger('22'));    // Output: false
    ```

* **'`Number.isSafeInteger()`'**: Retorna `true` se seu argumento for um inteiro seguro.

    ``` js
    console.log(Number.isSafeInteger(12931123120));          // Output: true
    console.log(Number.isSafeInteger(62345228962297280));    // Output: false
    ```

### Propriedades do Objeto `Number`

* **'`Number.EPSILON`'**: Representa o menor intervalo entre dois números. Permite verificar se dois números são aproximadamente iguais.

    ``` js
    console.log(Number.EPSILON); // Output: 2.220446049250313e-16
    ```

    Exemplo de como usá-lo para verificar se dois números são aproximadamente iguais:

    ``` js
    function aproximadamenteIgual(a, b) {
        return Math.abs(a - b) < Number.EPSILON;
    }

    const numero1 = 0.1 + 0.2;
    const numero2 = 0.3;

    if (aproximadamenteIgual(numero1, numero2)) {
    console.log("Os números são aproximadamente iguais.");
    } else {
    console.log("Os números não são aproximadamente iguais.");
    }
    ```

* **'`Number.MAX_VALUE`'**: Representa o maior valor possível em JavaScript.

    ``` js
    console.log(Number.MAX_VALUE); // Output: 1.7976931348623157e+308
    ```

* **'`Number.MIN_VALUE`'**: Representa o menor valor possível em JavaScript.

    ``` js
    console.log(Number.MIN_VALUE); // Output: 5e-324
    ```

* **'`Number.MAX_SAFE_INTEGER`'**: Representa o maior inteiro seguro.

    ``` js
    console.log(Number.MAX_SAFE_INTEGER); // Output: 9007199254740991
    ```

* **'`Number.MIN_SAFE_INTEGER`'**: Representa o menor inteiro seguro.

    ``` js
    console.log(Number.MIN_SAFE_INTEGER); // Output: -9007199254740991
    ```

* **'`Number.NaN`'**: Tem como valor `NaN`.

    ``` js
    console.log(Number.NaN); // Output: NaN
    ```

* **'`Number.POSITIVE_INFINITY`'**: Tem como valor `Infinity`.

    ``` js
    console.log(Number.POSITIVE_INFINITY); // Output: Infinity
    ```

* **'`Number.NEGATIVE_INFINITY`'**: Tem como valor `-Infinity`.

    ``` js
    console.log(Number.NEGATIVE_INFINITY); // Output: -Infinity
    ```

### Objeto `Math`

`Math` é um objeto estático, ou seja, não é precisa ser criada uma instância para ser utilizado.

#### Propriedades de `Math`

* **`Math.E`**: Retorna o númeor de Euler.

    ``` js
    console.log(Math.E);        // Output: 2.718281828459045
    ```

* **`Math.PI`**: Retorna o valor de PI.

    ``` js
    console.log(Math.PI);       // Output: 3.141592653589793
    ```

* **`Math.LN2`**: Retorna o logaritimo natural de 2.

    ``` js
    console.log(Math.LN2);      // Output: 0.6931471805599453
    ```

* **`Math.LN10`**: Retorna o logaritimo natural de 10.

    ``` js
    console.log(Math.LN10);     // Output: 2.302585092994046
    ```

* **`Math.LOG2E`**: Retorna o logaritimo de base 2 de E.

    ``` js
    console.log(Math.LOG2E);    // Output: 1.4426950408889634
    ```

* **`Math.LOG10E`**: Retorna o logaritimo de base 10 de E.

    ``` js
    console.log(Math.LOG10E);   // Output: 0.4342944819032518
    ```

* **`Math.SQRT2`**: Retorna a raiz quadrada de 2.

    ``` js
    console.log(Math.SQRT2);    // Output: 1.4142135623730951
    ```

* **`Math.SQRT1_2`**: Retorna a raiz quadrada de 1/2.

    ``` js
    console.log(Math.SQRT1_2);  // Output: 0.7071067811865476
    ```

#### Métodos de `Math`

* **'`Math.round()`'**: Arredonda um número para o inteiro mais próximo.

    ``` js
    console.log(Math.round(10.2)); // Output: 10
    console.log(Math.round(13.9)); // Output: 14
    console.log(Math.round(25.5)); // Output: 26
    ```

* **'`Math.ceil()`'**: Arredonda um número para cima.

    ``` js
    console.log(Math.ceil(15.2)); // Output: 16
    console.log(Math.ceil(12.9)); // Output: 13
    console.log(Math.ceil(19.5)); // Output: 20
    ```

* **'`Math.floor()`'**: Arredonda um número para baixo.

    ``` js
    console.log(Math.floor(11.2)); // Output: 11
    console.log(Math.floor(15.6)); // Output: 15
    console.log(Math.floor(28.5)); // Output: 28
    ```

* **'`Math.trunc()`'**: Retorna a parte inteira de um número.

    ``` js
    console.log(Math.trunc(17.5)); // Output: 17
    console.log(Math.trunc(15.9)); // Output: 15
    console.log(Math.trunc(12.3)); // Output: 12
    ```

* **'`Math.sign()`'**: Retorna:

  * **'`1`'** se o valor for positivo
  * **'`-1`'** se o valor for negativo
  * **'`0`'** se o valor for zero
  * **'`-0`'** se o valor for zero com sinal de menos
  * **'`NaN`'** se o valor não for um número

    ``` js
    console.log(Math.sign(5));      // Output: 1
    console.log(Math.sign(-5));     // Output: -1
    console.log(Math.sign(0));      // Output: 0
    console.log(Math.sign(-0));     // Output: -0
    console.log(Math.sign(NaN));    // Output: NaN
    ```

* **'`Math.abs()`'**: Retorna o valor absoluto de um número.

    ``` js
    console.log(Math.abs(6));       // Output: 6
    console.log(Math.abs(-2));      // Output: 2
    console.log(Math.abs(5.3));     // Output: 5.3
    console.log(Math.abs(-8.4));    // Output: 8.4
    ```

* **'`Math.sqrt()`'**: Retorna a raiz quadrada de um número.

    ``` js
    console.log(Math.sqrt(25));     // Output: 5
    console.log(Math.sqrt(2));      // Output: 1.4142135623730951
    console.log(Math.sqrt(100));    // Output: 10
    ```

* **'`Math.pow()`'**: Calcula a potência, elevando o segundo argumento ao primeiro (igualmente o operador `**`).

    ``` js
    console.log(Math.pow(7, 5));     // Output: 16807
    console.log(Math.pow(5, 2));     // Output: 25
    console.log(Math.pow(2, 0));     // Output: 1
    ```

* **'`Math.sin()`'**: Retorna o seno de um valor.

    ``` js
    console.log(Math.sin(30 * Math.PI / 180));  // Output: 0.49999999999999994
    console.log(Math.sin(45 * Math.PI / 180));  // Output: 0.7071067811865475
    console.log(Math.sin(60 * Math.PI / 180));  // Output: 0.8660254037844386
    ```

* **'`Math.cos()`'**: Retorna o cosseno de um valor.

    ``` js
    console.log(Math.cos(30 * Math.PI / 180));  // Output: 0.8660254037844387
    console.log(Math.cos(45 * Math.PI / 180));  // Output: 0.7071067811865476
    console.log(Math.cos(60 * Math.PI / 180));  // Output: 0.5000000000000001
    ```

* **'`Math.tan()`'**: Retorna a tangente de um valor.

    ``` js
    console.log(Math.tan(30 * Math.PI / 180));  // Output: 0.5773502691896257
    console.log(Math.tan(45 * Math.PI / 180));  // Output: 0.9999999999999999
    console.log(Math.tan(60 * Math.PI / 180));  // Output: 1.7320508075688767
    ```

* **'`Math.min()`'**: Recebe múltiplos argumentos e retorna o menor valor entre eles.

    ``` js
    console.log(Math.min(5, 1, 3, 4, 7, 2, 6, 9, 8, 0)); // Output: 0
    ```

* **'`Math.max()`'**: Recebe múltiplos argumentos e retorna o maior valor entre eles.

    ``` js
    console.log(Math.max(5, 1, 3, 4, 7, 2, 6, 9, 8, 0)); // Output: 9
    ```

* **'`Math.log()`'**: Retorna o logaritimo natural de um número.

    ``` js
    console.log(Math.log(2));  // Output: 0.6931471805599453
    console.log(Math.log(5));  // Output: 1.6094379124341003
    console.log(Math.log(10)); // Output: 2.302585092994046
    ```

* **'`Math.log2()`'**: Retorna o logaritimo natural de base 2 de um número.

    ``` js
    console.log(Math.log2(2));  // Output: 1
    console.log(Math.log2(5));  // Output: 2.321928094887362
    console.log(Math.log2(10)); // Output: 3.321928094887362
    ```

* **'`Math.log10()`'**: Retorna o logaritimo natural de base 10 de um número.

    ``` js
    console.log(Math.log10(2));  // Output: 0.3010299956639812
    console.log(Math.log10(5));  // Output: 0.6989700043360189
    console.log(Math.log10(10)); // Output: 1
    ```

* **'`Math.random()`'**: Retorna um número aleatório entre 0 (inclusivo) e 1 (exclusivo).

    ``` js
    console.log(Math.random());  // Output: Número aleatório entre 0 e 1
    ```

##### Método `random()`

Como já dito, retorna um número aleatório entre 0 e 1, onde 0 é inclusivo e 1 é exclusivo.

Para conseguir um número aleatório entre 0 e 10, por exemplo, podemos utilizar o `random()` multiplicando seu resultado por 10, e utilizando o método `floor()` para arredondar o número para o inteiro mais abaixo.

``` js
// Retorna um número inteiro entre 0 e 10
Math.floor(Math.random() * 11);
```

Podemos criar uma função que recebe como argumentos o intervalo entre os valores.

``` js
// Esta função retorna um número inteiro entre um intervalo
function randomNumber(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

## `Undefined` e `Null`

Variáveis declaradas com valores não atribuídos são `undefined`.

``` js
let myVar;
console.log(myVar); // Output: undefined
```

Variávels que possuem o valor `null` são basicamente variáveis sem um valor.

``` js
let myVar = null;
console.log(myVar); // Output: null
```

Comparando os valores `undefined` e `null`, eles são iguais, porém não estritamente iguais.

``` js
let varUndefined = undefined;
let varNull = null;

console.log(varUndefined == varNull);   // Output: true
console.log(varUndefined === varNull);  // Output: false
```

O tipo primitivo de `undefined` e `null` são diferentes:

``` js
console.log(typeof undefined);  // Output: undefined
console.log(typeof null);       // Output: object
```

## Estruturas Condicionais

### Instruções `if`, `else` e `else if`

São **`if`**, **`else`** e **`else if`**.

A sintaxe é a seguinte:

``` js
if (condicao1) {
    // Executa quando `condicao1` for verdadeiro
} else if (condicao2) {
    // Executa quando `condicao2` for verdadeiro
} else {
    // Executa quando nenhuma das instruções acima forem verdadeiras
}
```

Exemplo:

``` js
let num = 3;

if (num > 5) {
    console.log('Valor é MAIOR que 5');
} else if (num < 5) {
    console.log('Valor é MENOR que 5');
} else {
    console.log('Valor é IGUAL a 5');
}
// Output: Valor é MENOR que 5
```

### Instrução `switch`

Dado uma expressão ou variável, executa um bloco dependendo do valor dessa expressão ou variável.

Cada caso é definido com a palavra-chave `case`.

A sintaxe é a seguinte:

``` js
switch (expressao) {
    case valor1:
        // Código a ser executado caso `expressao` seja `valor1`
        break;
    case valor2:
        // Código a ser executado caso `expressao` seja `valor2`
        break;
    case valor3:
        // Código a ser executado caso `expressao` seja `valor3`
        break;
    default:
        // Executa quando nenhum dos blocos acima é executado
}
```

Exemplo:

``` js
let num = 3;

switch (num) {
    case num > 5:
        console.log('Valor é MAIOR que 5');
        break;
    case num < 5:
        console.log('Valor é MENOR que 5');
        break;
    default:
        console.log('Valor é IGUAL a 5');
}
// Output: Valor é IGUAL a 5
```

A palavra-chave **`break`** sai da estrutura `switch` imediatamente. Se omitido, o próximo bloco `case` será executado mesmo que seu valor não corresponda à expressão.

O bloco **`default`** é executado sempre que nenhum bloco `case` corresponda ao valor da expressão.

O `if` marca o início da estrutura condicional, `else` e `else if` não são obrigatórios em uma estrutura condicional.

A instrução `else` será executada sempre que as instruções acima testarem falso, ou seja, não executarem.

Em uma estrutura condicional, pode haver apenas um `if`, um `else` e vários `else if`.

#### Comparação do `switch`

Os casos `switch` usam o comparador estrito (`===`).

``` js
let valor = '5';

switch (valor) {
    case 5:
        console.log('Valor é IGUAL a 5');
        break;
    default:
        console.log('Valor é DIFERENTE de 5');
}
// Output: Valor é DIFERENTE de 5
```

## Arrays

Permitem armazenar vários valores em uma única variável. Os valores devem estar dentro de colchetes, cada um deles separadados por uma vírgula.

Sintaxe:

``` js
const myArray = [valor1, valor2, valor3, ..., valor10];
```

Exemplo de array:

``` js
const myArray = [10, 'false', '22', true, 5.3];
```

Como pode ver no exemplo acima, é possível armazenar diversos valores em um array, ainda que os valores possuam tipos diferentes uns dos outros.

> É comum que arrays sejam declaradas como constantes.

### Acessar Valores do Array

Cada item dentro do array é acessado por suas respectivas posições, considerando que a primeira posição é 0.

Exemplo:

``` js
let myArray = ['a', 'b', 'c', 'd', 'e'];

console.log(myArray[0]); // Output: a
console.log(myArray[1]); // Output: b
console.log(myArray[2]); // Output: c
console.log(myArray[3]); // Output: d
console.log(myArray[4]); // Output: e
```

Caso fornecido um índice inexistente no array, é retornado `underfined`.

``` js
const myArray = ['a', 'b', 'c', 'd', 'e'];

console.log(myArray[5]); // Output: undefined
```

### Mutação de Array

Mesmo que um array seja declarado como constante, ainda é possível alterar seus valores. Porém, a variável em si é imutável.

``` js
const myArray = ['a', 'b', 'c', 'd', 'e'];
myArray = [1, 2, 3, 4, 5]; // Ocorrerá um erro
```

Como dito, por mais que a variável em que o array está armazenado seja constante, seus elementos podem ser alterados.

``` js
const myArray = ['a', 'b', 'c', 'd', 'e'];
myArray[0] = 1;
myArray[1] = 2;
myArray[2] = 3;
myArray[3] = 4;
myArray[4] = 5;

console.log(myArray); // Output: [ 1, 2, 3, 4, 5 ]
```

### Array Multidimensional

Assim são chamados os arrays que possuem outros arrays como elementos.

``` js
const myArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
```

No exemplo acima, há três arrays dentro de um único array, e para acessar seus valores, deve ser primeiro especificado a posição do array e em seguida a posição do elemento dentro do array.

Exemplo:

``` js
const myArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

console.log(myArray[0][0]); // Output: 1
console.log(myArray[0][1]); // Output: 2
console.log(myArray[0][2]); // Output: 3
console.log(myArray[1][0]); // Output: 4
console.log(myArray[1][1]); // Output: 5
console.log(myArray[1][2]); // Output: 6
console.log(myArray[2][0]); // Output: 7
console.log(myArray[2][1]); // Output: 8
console.log(myArray[2][2]); // Output: 9
```

### Comprimento de um Array

Com a propriedade **`length`** é possível obter o número de elementos que um array possui.

``` js
const myArray = ['A', 'B', 'C', 'D', 'E'];
console.log(myArray.length); // Output: 5
```

### Verificar Se Uma Variável é Um Array

Há duas maneiras:

* Utilizando o método `isArray()` de `Array`:

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    Array.isArray(myArray); // -> true
    ```

* Utilizando o operador `instanceOf`:

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    myArray instanceof Array; // -> true
    ```

### Métodos de Array

* **'`toString()`'**: Converte o array para string.

    ``` js
    const myArray = ['Olá', true, 2.1, false, 9];
    console.log(myArray.toString()); // Output: Olá,true,2.1,false,9
    ```

* **'`push()`'**: Adiciona um ou mais elementos ao fim do array.

    ``` js
    const myArray = [1, 2, 3];
    myArray.push(4, 5);

    console.log(myArray); // Output: [ 1, 2, 3, 4, 5 ]
    ```

* **'`unshift()`'**: Adiciona um ou mais elementos ao início do array.

    ``` js
    const myArray = [1, 2, 3];
    myArray.unshift(-1, 0);

    console.log(myArray); // Output: [ -1, 0, 1, 2, 3 ]
    ```

* **'`fill()`'**: Preenche o array com um elemento entre as posições de início e fim, especificadas nos argumentos.

    Recebe três argumentos:

    1. Elemento que irá preencher
    1. Início (inclusivo)
    1. Fim (exclusivo)

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    myArray.fill('X', 2, 3);

    console.log(myArray); // Output: [ 'A', 'B', 'X', 'D', 'E' ]
    ```

* **'`pop()`'**: Remove o último elemento do array e o retorna.

    ``` js
    const myArray = ['a', 'b', 'c', 'd', 'e'];
    const elementoRemovido = myArray.pop(); // -> e

    console.log(myArray); // Output: [ 'a', 'b', 'c', 'd' ]
    ```

* **'`shift()`'**: Remove o primeiro elemento da matriz e o retorna.

    ``` js
    const myArray = ['a', 'b', 'c', 'd', 'e'];
    const elementoRemovido = myArray.shift(); // -> a

    console.log(myArray); // Output: [ 'b', 'c', 'd', 'e' ]
    ```

* **'`slice()`'**: Cria uma cópia do array, começando e terminando pelas posições definidas.

    São dois argumentos:

    1. Índice do elemento que vai iniciar o array
    1. Índice do elemento que vai terminar o array

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    const copiaArray = myArray.slice(2, 5);

    console.log(copiaArray); // Output: [ 'C', 'D', 'E' ]
    ```

* **'`splice()`'**: Adiciona, remove ou substitui elementos a partir de uma posição específica no array.

    Recebe dois argumentos, e em seguida pode receber múltiplos argumentos.

    1. Posição em que começará as alterações
    1. Quantidade de valores que serão excluídos
    1. A partir daqui, pode receber múltiplos valores, que são os elementos a serem adicionados

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I'];
    const elementosExcluidos = myArray.splice(2, 4, 'X', 'Y', 'Z');

    console.log(myArray); // Output: [ 'A', 'B', 'X', 'Y', 'Z', 'G', 'H', 'I' ]
    console.log(elementosExcluidos); // Output: [ 'C', 'D', 'E', 'F' ]
    ```

    > OBS.: Essas modificações são feitas no array original.

* **'`concat()`'**: Concatena dois ou mais arrays.

    ``` js
    const array1 = [1, 2, 3];
    const array2 = [4, 5, 6];
    const array3 = [7, 8, 9];

    const myArray = array1.concat(array2, array3);
    console.log(myArray); // Output: [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
    ```

* **'`reverse()`'**: Inverte as posições dos elementos no array original.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    myArray.reverse();
    console.log(myArray); // Output: [ 'E', 'D', 'C', 'B', 'A' ]
    ```

* **'`includes()`'**: Retorna `true` se um elemento existir dentro do array, ou `false` em caso contrário.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    console.log(myArray.includes('B')); // Output: true
    console.log(myArray.includes('F')); // Output: false
    ```

* **'`sort()`'**: Organiza o array original em ordem alfabética ou numérica.

    ``` js
    const myArray = ['C', 'D', 'A', 'E', 'B'];
    myArray.sort();
    console.log(myArray); // Output: [ 'A', 'B', 'C', 'D', 'E' ]
    ```

    No caso de um array numérico:

    ``` js
    const myArray = [20, 100, 44, 12];
    myArray.sort();
    console.log(myArray); // Output: [ 100, 12, 20, 44 ]
    ```

    Isso acontece pois os valores são convertidos para string para a organização, logo, os números são ordenados lexicograficamente.

    Para que os números sejam ordenados de forma numérica, é possível fornecer uma função de comparação como argumento do método `sort()`.

    ``` js
    const myArray = [20, 100, 44, 12];
    myArray.sort(function (a, b) { return a - b; });
    console.log(myArray); // Output: [ 12, 20, 44, 100 ]
    ```

* **'`join()`'**: Cria uma string a partir dos elementos que compõem o array. Os elementos são separados por um separador especificado como argumento.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    const myStr = myArray.join(' > ');
    console.log(myStr); // Output: A > B > C > D > E
    ```

* **'`indexOf()`'**: Retorna a posição da primeira ocorrência do elemento especificado, ou `-1` caso o elemento não exista dentro do array.

    Pode receber dois argumentos:

    1. Elemento a ser encontrado
    1. Posição em que começará a busca

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    console.log(myArray.indexOf('A')); // Output: 0
    console.log(myArray.indexOf('B')); // Output: 1
    console.log(myArray.indexOf('C')); // Output: 2
    console.log(myArray.indexOf('D')); // Output: 3
    console.log(myArray.indexOf('E')); // Output: 4
    console.log(myArray.indexOf('F')); // Output: -1
    ```

* **'`lastIndexOf()`'**: Retorna a posição da última ocorrência do elemento especificado, ou `-1` caso o elemento não exista dentro do array.

    Pode receber dois argumentos:

    1. Elemento a ser encontrado
    1. Posição em que começará a busca

    ``` js
    const myArray = [1, 2, 7, 1, 5, 1];
    console.log(myArray.lastIndexOf(1)); // Output: 5
    console.log(myArray.lastIndexOf(8)); // Output: -1
    ```

* **'`flat()`'**: É aplicado à arrays multidimensionais, unindo todos os elementos em um novo array.

    ``` js
    const myArray = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ];
    const newArray = myArray.flat();
    console.log(newArray); // Output: [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
    ```

* **'`forEach()`'**: É um iterador que executa uma função para cada elemento do array.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];

    myArray.forEach(function (letra, indice) {
        console.log(`A letra ${letra} está no índice ${indice}`);
    });

    /* Output:
    A letra A está no índice 0
    A letra B está no índice 1
    A letra C está no índice 2
    A letra D está no índice 3
    A letra E está no índice 4
    */
    ```

* **'`map()`'**: É um iterador que cria um novo array aplicando uma função a cada elemento dentro do array.

    ``` js
    const myArray = [1, 2, 3, 4, 5];
    const newArray = myArray.map(function (num) {
        return num * 2;
    });
    console.log(newArray); // Output: [ 2, 4, 6, 8, 10 ]
    ```

* **'`flatMap()`'**: É um iterador que une os métodos `flat()` e `map()`.

    ``` js
    const myArray = ['olá', 'mundo'];
    const palavras = myArray.flatMap(function (palavra) {
        return palavra.split('');
    });

    console.log(palavras); // Output: [ o, l, á, m, u, n, d, o ]
    ```

* **'`filter()`'**: Itera sobre o array e retorna um novo array apenas com os elementos que testaram `true` para uma função.

    ``` js
    const myArray = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    const newArray = myArray.filter(function (num) {
        if (num % 2 == 0) return true; // Apenas valores pares
    });
    console.log(newArray); // Output: [ 0, 2, 4, 6, 8 ]
    ```

* **'`every()`'**: Itera sobre o array e retorna `true` apenas se todos os elementos testarem verdadeiro para uma função.

    ``` js
    function isPar(num) {
        if (num % 2 == 0) return true;
    }

    const array1 = [0, 3, 2, 1].every(isPar);
    const array2 = [2, 0, 6, 8].every(isPar);

    console.log(array1); // Output: false
    console.log(array2); // Output: true
    ```

* **'`some()`'**: Itera sobre o array e retorna `true` se pelo menos um elemento do array testar verdadeiro para uma função.

    ``` js
    function isPar(num) {
        if (num % 2 == 0) return true;
    }

    const array1 = [5, 3, 7, 9, 2].some(isPar);
    const array2 = [3, 7, 15, 11, 9].some(isPar);

    console.log(array1); // Output: true
    console.log(array2); // Output: false
    ```

* **'`reduce()`'**: Itera sobre o array e o reduz para um valor único de acordo com uma função.

    ``` js
    const myArray = [1, 2, 3, 4, 5];
    const newArray = myArray.reduce(function (acumulador, elemento) {
        return acumulador - elemento;
    });

    console.log(newArray); // Output: -13
    ```

* **'`reduceRight()`'**: O mesmo que o método `reduce()`, porém iniciando com os elementos da direita para a esquerda.

    ``` js
    const myArray = [1, 2, 3, 4, 5];
    const newArray = myArray.reduceRight(function (acumulador, elemento) {
        return acumulador - elemento;
    });

    console.log(newArray); // Output: -5
    ```

* **'`find()`'**: É um iterador que retorna o primeiro elemento que testar verdadeiro para uma função.

    ``` js
    const myArray = [2, 10, 13, 21, 22, 35];
    const elemento = myArray.find(function (elemento) {
        return elemento > 10;
    })

    console.log(elemento); // Output: 13
    ```

* **'`findIndex()`'**: É um iterador que retorna o índice do primeiro elemento que testar verdadeiro para uma função.

    ``` js
    const myArray = [2, 10, 13, 21, 22, 35];
    const indice = myArray.findIndex(function (elemento) {
        return elemento > 10;
    })

    console.log(indice); // Output: 2
    ```

* **'`keys()`'**: Itera sobre as chaves do array, ou seja, os índices.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    const chaves = myArray.keys();
    for (let x of chaves) {
        console.log(x);
    }
    /* Output:
    0
    1
    2
    3
    4
    */
    ```

* **'`entries()`'**: Itera sobre os pares chave/valor de um array.

    ``` js
    const myArray = ['A', 'B', 'C', 'D', 'E'];
    const kv = myArray.entries();
    for (let x of kv) {
        console.log(`${x[0]}: ${x[1]}`);
    }
    /* Output:
    0: A
    1: B
    2: C
    3: D
    4: E
    */
    ```

## Estruturas de Repetição

### Loop '`for`'

Executa um bloco uma quantidade específica de vezes.

A sintaxe é a seguinte:

``` js
for (inicializacao; condicao; incremento) {
    // Bloco de código que vai ser repetido
}
```

Exemplo:

``` js
for (let n = 0; n <= 10; n++) {
    console.log(n);
}
/* Output:
0
1
2
3
4
5
6
7
8
9
10
*/
```

### Loop  '`for...in`'

Percorre um objeto, enumerando cada propriedade/índice e executando seu bloco de código uma vez para cada uma propriedade/índice.

A sintaxe é a seguinte:

``` js
for (let propriedade in objeto) {
    // Bloco a ser repetido
}
```

Exemplo:

``` js
const myObj = {um: 1, dois: 2, tres: 3};

for (let p in myObj) {
    console.log(p);
}
/* Output:
um
dois
tres
*/
```

No exemplo acima, o loop `for...in` iterou sobre o objeto `myObj`, e a cada iteração a variável `p` possuia o nome de uma das propriedades de `myObj`.

Também é possível iterar sobre arrays:

``` js
const myArray = ['A', 'B', 'C', 'D', 'E'];

for (let i in myArray) {
    console.log(i);
}
/* Output:
0
1
2
3
4
*/
```

Quando utilizado em arrays, o loop `for...in` itera sobre os índices do array.

Quando usado para iterar sobre strings, funciona de maneira semelhante a arrays.

``` js
const myStr = 'Olá, Mundo!';

for (let i in myStr) {
    console.log(i);
}
/* Output:
0
1
2
3
4
5
6
7
8
9
10
*/
```

### Loop '`for...of`'

É parecido com o `for...in`, porém ao invés de iterar sobre os índices, o **`for...of`** itera sobre os valores.

> Não pode ser utilizado para iterar sobre objetos.

Exemplo com array:

``` js
const myArray = ['A', 'B', 'C', 'D', 'E'];

for (let v of myArray) {
    console.log(v);
}
/* Output:
A
B
C
D
E
*/
```

> É preferível o uso do loop `for...of` para arrays no lugar de `for...in` para evitar possíveis problemas de ordem.

Exemplo com string:

``` js
const myStr = 'Olá, Mundo!';

for (let v of myStr) {
    console.log(v);
}
/* Output:
O
l
á
,

M
u
n
d
o
!
*/
```

### Loop '`while`'

Executa um bloco de código enquanto a condição passada for verdadeira.

Sintaxe:

``` js
while (condicao) {
    // Bloco a ser repetido
}
```

Exemplo:

``` js
let contador = 0;
while (contador <= 5) {
    console.log(contador);
    contador++;
}
/* Output:
0
1
2
3
4
5
*/
```

### Loop '`do...while`'

É uma variante do loop `while` e executa um bloco uma vez, e suas próximas execuções ocorrem apenas se uma condição for verdadeira.

Sintaxe:

``` js
do {
    // Bloco a ser repetido
} while (condicao);
```

Exemplo:

``` js
let contador = 10;

do {
    console.log(contador)
    contador++;
} while (contador <= 5);
// Output: 10
```

### Declarações '`break`' e '`continue`'

São usadas para controlar os loops, onde **`break`** interrompe e sai de um loop imediatamente e **`continue`** pula para a próxima execução do loop.

Exemplo com `break`:

``` js
let contador = 0;

while (true) {
    console.log(contador);
    contador++;
    if (contador == 6) { break }
}
/* Output:
0
1
2
3
4
5
6
*/
```

No exemplo acima, temos um loop `while` infinito, que utilizada a declaração `break` para encerrar quando o contador for igual a 6.

Exemplo com `continue`:

``` js
for (let contador = 0; contador <= 10; contador++) {
    if (contador % 2 != 0) { continue }
    console.log(contador);
}
/* Output:
0
2
4
6
8
10
*/
```

No exemplo acima, temos um loop que imprime apenas os valores pares entre 0 e 10.

#### Etiquetas

As labels, ou etiquetas, são nomes dados a loops, muito úteis para redirecionar o controle de fluxo à loops específicos.

Sintaxe:

``` js
nomeLabel: instrucao

// Ou

nomeLabel:
instrucao
```

Exemplo:

``` js
label1: while (true) {
    label2: for (let c = 0; c <= 5; c++) {
        console.log(c);
        if (c == 2) { break label1} // Sai do loop `while`
    }
    console.log('Olá, Mundo!');
}
/* Output
0
1
2
*/
```

No exemplo acima, a mensagem "Olá, Mundo!" sequer é mostrada no console, isso acontece porquê no loop `for` existe uma declaração  `break` endereçada à etiqueta `label1`, que rotula o loop `while`, o qual a mensagem está dentro e é encerrado antes de mostrá-la.

> Etiquetas podem rotular qualquer instrução, como `if`, porém são usadas com as instruções de loop combinadas às declarações de controle de fluxo.

## Datas

São criadas a partir do construtor `new Date()`.

``` js
const myDate = new Date();
```

Dessa forma, são criados o horário e data atual.

### Datas a Partir de Strings

É possível criar datas a partir de strings, devem ser especificados:

``` js
const myDate = new Date('February 27, 2013 12:22:00');
console.log(myDate); // Output: 2013-02-27T15:22:00.000Z
```

O mesmo seria:

``` js
const myDate = new Date('2013-02-27, 12:22:00');
console.log(myDate); // Output: 2013-02-27T15:22:00.000Z
```

### Datas a Partir de Argumentos

É possível criar datas passando argumentos para ano, mês, dia, etc.

``` js
const myDate = new Date(2013, 1, 27, 12, 22, 0);
console.log(myDate); // Output: 2013-02-27T15:22:00.000Z
```

A ordem dos argumentos são:

1. Ano
1. Mês
1. Dia
1. Horas
1. Minutos
1. Segundos
1. Milissegundos

> Anos escritos com 1 ou dois dígitos são tratados como o século anterior.

> Os meses são escritos como índices, ou seja, janeiro é 0, fevereiro é 1, março é 3 e assim por diante.

### Datas a Partir de Milissegundos

Fornecer apenas um argumento ao `Date()` fará com que esse argumento seja tratado como milissegundos, e então gerará uma data através deles.

``` js
const myDate = new Date(10000000000);
console.log(myDate); // Output: 1970-04-26T17:46:40.000Z
```

O método **`Date.parse()`** converte uma data em milissegundos:

``` js
const myDate = Date.parse('2020-10-22');
console.log(myDate); // Output: 1603324800000
```

São contadas a partir do ano de 1970, ou seja, o argumento é a quantidade de milissegundos a mais ou a menos que o ano de 1970.

O método **`Date.now()`** retorna a quantidade de milissegundos desde o ano de 1970 até a data atual.

### Métodos de Exibição de Data

* **'`toDateString()`'**: Formata a data para uma melhor legibilidade.

    ``` js
    const myDate = new Date('2020-10-23');
    console.log(myDate.toDateString()); // Output: Thu Oct 22 2020
    ```

* **'`toUTCString()`'**: Converte a data usando um UTC padrão.

    ``` js
    const myDate = new Date('2020-10-22');
    console.log(myDate.toUTCString()); // Output: Thu, 22 Oct 2020 00:00:00 GMT
    ```

* **'`toISOString()`'**: Converte a data usando um ISO padrão.

    ``` js
    const myDate = new Date('2020-10-22');
    console.log(myDate.toISOString()); // Output: 2020-10-22T00:00:00.000Z
    ```

### Métodos Para Obter Datas

* **'`getFullYear()`'**: Retorna o ano de uma data.

    ``` js
    const myDate = new Date('2010-05-30');
    console.log(myDate.getFullYear()); // Output: 2010
    ```

* **'`getMonth()`'**: Retorna o mês da data.

    ``` js
    const myDate = new Date('2010-05-30');
    console.log(myDate.getMonth()); // Output: 4
    ```

    Lembrando que os meses são contados a partir do zero, ou seja, janeiro = 0 e dezembro = 11.

* **'`getDate()`'**: Retorna o dia do mês da data.

    ``` js
    const myDate = new Date('2010-05-30');
    console.log(myDate.getDate()); // Output: 29
    ```

* **'`getDay()`'**: Retorna o dia da semana da data.

    ``` js
    const myDate = new Date('2010-05-30');
    console.log(myDate.getDay()); // Output: 6
    ```

    Assim como os meses, os dias da semana são contados a partir do 0.

* **'`getHours()`'**: Retorna as hora da data (0 - 23).

    ``` js
    const myDate = new Date('2010-05-30, 11:55:32');
    console.log(myDate.getHours()); // Output: 11
    ```

* **'`getMinutes()`'**: Retorna os minutos da data (0 - 59).

    ``` js
    const myDate = new Date('2010-05-30, 11:55:32');
    console.log(myDate.getMinutes()); // Output: 55
    ```

* **'`getSeconds()`'**: Retorna os segundos da data (0 - 59).

    ``` js
    const myDate = new Date('2010-05-30, 11:55:32');
    console.log(myDate.getSeconds()); // Output: 32
    ```

* **'`getMilliseconds()`'**: Retorna os milissegundos da data (0 - 999).

    ``` js
    const myDate = new Date('2010-05-30, 11:55:32:16');
    console.log(myDate.getMilliseconds()); // Output: 16
    ```

* **'`getTime()`'**: Retorna o tempo em milissegundos.

    ``` js
    const myDate = new Date('2010-05-30, 11:55:32');
    console.log(myDate.getTime()); // Output: 1275231332000
    ```

* **'`getUTCDate()`'**: Retorna a data UTC.
* **'`getUTCFullYear()`'**: Retorna o ano UTC.
* **'`getUTCMonth()`'**: Retorna o mês UTC.
* **'`getUTCDay()`'**: Retorna o dia UTC.
* **'`getUTCHours()`'**: Retorna as horas UTC.
* **'`getUTCMinutes()`'**: Retorna os minutos UTC.
* **'`getUTCSeconds()`'**: Retorna os segundos UTC.
* **'`getUTCMilliseconds()`'**: Retorna os milissegundos UTC.
* **'`getTimezoneOffset()`'**: Retorna a diferença em minutos entre o horário local e o horário UTC.

### Métodos Para Definir Datas

* **'`setFullYear()`'**: Define o ano da data.
* **'`setMonth()`'**: Define o mês da data (0 - 11).
* **'`setDate()`'**: Define o dia da data (1 - 31).
* **'`setHours()`'**: Define as horas da data (0 - 23).
* **'`setMinutes()`'**: Define os minutos da data (0 - 59)
* **'`setSeconds()`'**: Define os segundos da data (0 - 59)
* **'`setMilliseconds()`'**: Define os milissegundos da data (0 - 999).

``` js
const myDate = new Date();
myDate.setFullYear(2007);
myDate.setMonth(1);
myDate.setDate(4);
myDate.setHours(0);
myDate.setMinutes(5);
myDate.setMilliseconds(0);

console.log(myDate); // Output: Sun Feb 04 2007 00:05:16 GMT-0200 (Horário de Verão de Brasília)
```

* **'`setTime()`'**: Define o tempo em milissegundos desde o dia 1 de janeiro de 1970.

    ``` js
    const myDate = new Date();
    myDate.setTime(1275231332000);
    console.log(myDate); // Output: 2010-05-30T14:55:32.000Z
    ```

## Objetos

Objetos armazenam pares chave-valor, e esses objetos podem ter métodos.

A sintaxe é a seguinte:

``` js
const myObject = {key1: 'value1', key2: 'value2'};
```

Exemplo:

``` js
const pessoa = {nome: 'Joel', idade: 25, sexo: 'masculino'};
```

No exemplo acima, `nome`, `idade` e `sexo` são propriedades, e Joel, 25 e masculino são os valores dessas propriedades.

### Acessar Valores das Propriedades

Pode ser feito de duas maneiras:

* `nomeObjeto.nomePropriedade`
* `nomeObjeto['nomePropriedade']`

Exemplo:

``` js
const pessoa = {nome: 'Joel', idade: 25, sexo: 'masculino'};

console.log(pessoa.nome);   // Output: Joel
console.log(pessoa.idade);  // Output: 25
console.log(pessoa.sexo);   // Output: masculino
```

Ou:

``` js
const pessoa = {nome: 'Joel', idade: 25, sexo: 'masculino'};

console.log(pessoa['nome']);   // Output: Joel
console.log(pessoa['idade']);  // Output: 25
console.log(pessoa['sexo']);   // Output: masculino
```

### Métodos

Métodos são, basicamente, funções como valores de propriedades. Esses métodos realizam ações no contexto do objeto, por exemplo:

``` js
const pessoa = {
    nome: 'Joel',
    idade: 25,
    sexo: 'masculino',
    apresentacao: function() {
        return 'Olá, eu sou ' + this.nome + '!';
    }
};

console.log(pessoa.apresentacao()); // Output: Olá, eu sou Joel!
```

No exemplo acima, o objeto `pessoa` possui o método `apresentacao()`, método esse que retorna uma mensagem de apresentação com a propriedade `nome` do próprio objeto.

#### Palavra-chave `this`

A palavra-chave **`this`**, no contexto de objetos, se refere ao próprio objeto.

``` js
const pessoa = {
    nome: 'Joel',
    idade: 25,
    sexo: 'masculino',
    apresentacao: function() {
        return 'Olá, eu sou ' + this.nome + '!';
    }
};
```

No objeto acima:

* **'`this.nome`'**: Se refere a Joel
* **'`this.idade`'**: Se refere a 25
* **'`this.sexo`'**: Se refere a masculino
* **'`this.apresentacao`'**: Se refere à função

### Alterar Valor de Propriedades

Para alterar o valor de uma propriedade é como alterar o valor de uma variável:

``` js
const pessoa = {nome: 'Joel', idade: 25, sexo: 'masculino'};
pessoa.idade = 52;
console.log(pessoa); // Output: { nome: 'Joel', idade: 52, sexo: 'masculino' }
```

### Adicionar Propriedade ao Objeto

Adicionar uma nova propriedade a um objeto é como alterar o valor de uma propriedade já existente, porém especificando uma propriedade que não existe:

``` js
const pessoa = {nome: 'Joel', idade: 25, sexo: 'masculino'};
pessoa.peso = '92kg';
console.log(pessoa); // Output: { nome: 'Joel', idade: 25, sexo: 'masculino', peso: '92kg' }
```

## Funções

Funções são criadas a partir da palavra-chave **`function`**, e podem ser construídas de três formas:

* Declaração de Função
* Expressão de Função
* Construtor de Função

### Declaração de Função

Na Declaração de Função, usa-se a palavra-chave **`function`**, e após ela o nome da função e parâmetros, e então um bloco com o conteúdo da função.

A sintaxe é a seguinte:

``` js
function nomeFuncao(param1, param2, ..., param10) {
    // Código que a função executa quando chamada
}
```

### Expressão de Função

Na Expressão de Função, a função é armazenada em uma variável, variável essa que passa a agir como uma função. Primeiro é declarada a variável, depois atribuída à essa variável a função, que é construída a partir da palavra-chave **`function`**, seguida de parênteses que contém dentro de si os parâmetros da função, e após isso vêm o bloco de código que a função vai executar ao ser chamada.

A sintaxe é a seguinte:

``` js
const nomeFuncao = function (param1, param2, ..., param10) {
    // Código que a função executa quando chamada
}
```

### Construtor de Funções

A função **`Function()`** é um construtor de funções, onde seus primeiros argumentos são os parâmetros da função e seu último argumento é o bloco que a função vai executar.

A sintaxe é a seguinte:

``` js
const isPar = new Function('param1', 'param2', 'param3', 'Código que a função executará quando chamada');
```

A palavra-chave **`new`** é usada, neste caso, para criar uma instâcia do construtor `Function()`.

### Parâmetros e Argumentos

Em JavaScript, não é verificado a quantidade de argumentos passados e nem o tipo de dado do argumento passado.

#### Valor Padrão Para Parâmetros

Por padrão, os valores dos argumentos não passados pelo usuário é `undefined`, e para definir um valor padrão para uma parâmetro, pode ser feito o seguinte:

``` js
function quadrado(x = 0) {
    return x ** 2;
}

console.log(quadrado()); // Output: 0
```

No exemplo acima, o parâmetro `x` terá o valor 0 se não for passado nenhum outro valor.

#### Operador Rest

O operador Rest permite passar vários valores como argumento para uma função, a partir daí, esses valores são armazenados como um array no parâmetro.

``` js
function soma(...valores) {
    let soma = 0;
    for (let i of valores) soma += i;
    return soma;
}

console.log(soma(5, 1, 2, 4, 6, 8, 9)); // 35
```

### Içamento de Funções

Primeiramente, içar - ou hoisting, em inglês - significa mover declações para o topo do código, de maneira que você possa, por exemplo, chamar uma função linhas antes de sua declaração.

O hoisting ocorre em funções declaradas, mas não em expressões de funções.

Exemplo com declaração de função:

``` js
console.log(isImpar(5)); // Isso funciona

function isImpar(valor) {
    return valor % 2 !== 0;
}
```

Exemplo com expressão de função:

``` js
console.log(isImpar(5)); // Isso não funciona
const isImpar = function(valor) {
    return valor % 2 !== 0;
}
```

### Funções que se Auto-invocam

Funções que se auto-invocam - ou se auto-chamam - são funções que podem ser anônimas(sem nome) que são chamadas assim que são declaradas.

Nessas funções, a função anônima deve estar dentro de parênteses, e ao fim da declaração, deve também haver um par de parênteses.

A sintaxe é a seguinte:

``` js
(function (param1, param2, ..., param10) {
    // Bloco que a função vai executar
})(arg1, arg2, ..., arg10);
```

Como visto no exemplo acima, os parâmetros são especificados entre os parênteses após a palavra-chave `function` e os argumentos são passados nos parênteses ao final da declaração.

Exemplo de função que se auto-invoca (sem parâmetros):

``` js
(function () {
    console.log('Olá, Mundo!'); // Output: Olá, Mundo!
})();
// Essa função se auto-invoca
```

Exemplo de função que se auto-invoca (com parâmetros):

``` js
(function (x, y) {
    console.log(x * y); // Output: 50
})(5, 10);
// Essa função se auto-invoca
```

### Variável Local `arguments`

A variável local `arguments` possui todos os argumentos em forma de array, mas ainda assim, esta variável não é um array real. Os argumentos podem ser acessados por índice, e seu maior uso é para ter acesso ao número de argumentos passados para a função com a propriedade **`length`**.

``` js
function soma() {
    let soma = 0;
    for (let i = 0; i < arguments.length; i++) {
        soma += arguments[i];
    }
    return soma;
}

console.log(soma(2, 5)); // Output: 7
```

No exemplo acima, a função `soma()` não pede nenhum argumento, de qualquer modo, ela consegue somar argumentos passados por meio da variável local `arguments`, que é usada tanto como condição para o `for`, quanto para ter acesso aos valores passados como argumentos para a soma.

### *Arrow Functions*

As funções de seta são funções escritas de maneira mais curta e simples, onde a palavra `function` pode ser omitida. Caso a função possua apenas uma declaração, as chaves e a palavra `return` também podem ser omitidos.

Exemplo:

``` js
const soma = (x, y) => x + y;
```

A função acima é uma maneira simplificada da seguinte função:

``` js
const soma = function (x, y) { return x + y };
```

Exemplo de função de seta com mais de uma declaração:

``` js
const maiorQueDez = (x) => {
    if (x > 10) {
        return `${x} é MAIOR que 10`;
    } else if (x < 10) {
        return `${x} é MENOR que 10`;
    } else {
        return 'Valor é IGUAL a 10';
    }
};
```

Sobre as Arrow Functions:

* Elas não são içadas(hoisting)
* As chaves e a palavra-chave `return` só podem ser omitidos caso a função possua apenas uma declaração
* Elas não são ideais para métodos de objetos
* Elas mantém o valor do `this` do contexto em que foram definidas

### Retorno de Valores

A palavra-chave **`return`** retorna um valor e encerra a função.

``` js
function isPar(valor) {
    return valor % 2 === 0;
}

isPar(2); // -> true
isPar(5); // -> false
```

No exemplo acima, a função `isPar()` verifica se um valor é par, e se for, retorna `true`.

## Sets

São como arrays, porém um valor específico só pode ocorrer uma vez dentro do set.

É utilizado o construtor **`new Set()`** para criar um set.

``` js
const mySet = new Set();
```

É muito útil para remover itens duplicados em um array.

``` js
const myArray = [2, 3, 5, 3, 1];
const mySet = new Set(myArray);

console.log(mySet);
// Output: Set(4) { 2, 3, 5, 1 }
```

Existe apenas uma propriedade para sets, a propriedade **`size`**, que retorna o número de elementos dentro do set.

``` js
const mySet = new Set(['A', 'B', 'C', 'D', 'E']);
console.log(mySet.size); // Output: 5
```

### Métodos para Set

* **'`add()`'**: Adiciona um elemento ao fim do set.

    ``` js
    const mySet = new Set();
    mySet.add('A');
    mySet.add('B');
    mySet.add('C');
    mySet.add('D');
    mySet.add('E');

    console.log(mySet);
    // Output: Set(5) { 'A', 'B', 'C', 'D', 'E' }
    ```

* **'`delete()`'**: Exclui o elemento especificado. Caso o elemento exista dentro do set, ele irá retornar `true`, caso contrário, retornará `false`.

    ``` js
    const mySet = new Set([1, 2, 3, 4, 5]);

    let deletado =  mySet.delete(3);
    console.log(deletado); // Output: true
    ```

* **'`has()`'**: Retorna verdadeiro se o elemento especificado existir dentro do set.

    ``` js
    const mySet = new Set([1, 2, 3, 4, 5]);
    console.log(mySet.has(2)); // Output: true
    console.log(mySet.has(6)); // Output: false
    ```

* **'`forEach()`'**: Executa uma função para cada elemento dentro do set.

    ``` js
    const mySet = new Set([1, 2, 3, 4, 5]);
    mySet.forEach((elemento) => {
        console.log(elemento);
    })
    /* Output:
    1
    2
    3
    4
    5
    */
    ```

* **'`values()`'**: Retorna um objeto iterador para acessar os elementos.

    ``` js
    const mySet = new Set([1, 2, 3, 4, 5]);
    for (let elemento of mySet.values()) {
        console.log(elemento);
    }
    /*Output:
    1
    2
    3
    4
    5
    */
    ```

## Maps

Maps armazenam dados com pares chave-valor.

Um map é declarado a partir do construtor **`new Map()`**.

``` js
const myMap = newMap();
```

Exemplo de map:

``` js
const myMap = new Map([
    ['chave1', 'valor1'],
    ['chave2', 'valor2'],
    ['chave3', 'valor3']
]);
console.log(myMap);
/* Output:
Map(3) {
  'chave1' => 'valor1',
  'chave2' => 'valor2',
  'chave3' => 'valor3'
}
*/
```

Os maps preservam a ordem em que os pares chave-valor foram inseridos, logo, é possível iterar pelos elementos na ordem em que foram inseridos.

Assim como os sets, os maps possuem a propriedade **`size`**, que retorna o número de elementos no map.

``` js
const myMap = new Map([
    ['chave1', 'valor1'],
    ['chave2', 'valor2'],
    ['chave3', 'valor3']
]);
console.log(myMap.size); // Output: 3
```

### Métodos para Maps

* **'`set()`'**: Adiciona novos elementos ou substitui valores de elementos já existentes.

    ``` js
    const materiais = new Map();

    materiais.set('lápis', 2);
    materiais.set('caneta', 1);
    materiais.set('borracha', 1);
    materiais.set('apontador', 1);

    console.log(materiais);
    /* Output:
    Map(4) {
    'lápis' => 2,
    'caneta' => 1,
    'borracha' => 1,
    'apontador' => 1
    }
    */
    ```

    Substituição de valor:

    ``` js
    const numeros = new Map([
    ['numero1', 0],
    ['numero2', 1]
    ]);

    numeros.set('numero1', 1);
    numeros.set('numero2', 2);

    console.log(numeros);
    // Output: Map(2) { 'numero1' => 1, 'numero2' => 2 }
    ```

* **'`get()`'**: Retorna o valor da chave especificada.

    ``` js
    const myMap = new Map([
        ['primeiro', 1],
        ['segundo', 2],
        ['terceiro', 3]
    ]);

    console.log(myMap.get('primeiro'));   // Output: 1
    console.log(myMap.get('segundo'));    // Output: 2
    console.log(myMap.get('terceiro'));   // Output: 3
    ```

* **'`delete()`'**: Exclui um elemento do map.

    ``` js
    const myMap = new Map([
        ['primeiro', 1],
        ['segundo', 2],
        ['terceiro', 3]
    ]);
    myMap.delete('primeiro');

    console.log(myMap);
    // Output: Map(2) { 'segundo' => 2, 'terceiro' => 3 }
    ```

* **'`has()`'**: Retorna verdadeiro caso a chave especificada exista dentro do map.

    ``` js
    const myMap = new Map([
        ['primeiro', 1],
        ['segundo', 2],
        ['terceiro', 3]
    ]);

    console.log(myMap.has('segundo'));  // Output: true
    console.log(myMap.has('quarto'));   // Output: false
    ```

* **'`forEach()`'**: Chama uma função para cada elemento dentro do map.

    ``` js
    const myMap = new Map([
        ['primeiro', 1],
        ['segundo', 2],
        ['terceiro', 3]
    ]);

    myMap.forEach((v, k) => {
        console.log(`${k}: ${v}`);
    })
    /* Output:
    primeiro: 1
    segundo: 2
    terceiro: 3
    */
    ```

* **'`entries()`'**: Retorna um objeto iterável com as chaves e os valores do map.

    ``` js
    const myMap = new Map([
        ['primeiro', 1],
        ['segundo', 2],
        ['terceiro', 3]
    ]);
    for (let x of myMap.entries()) {
        console.log(x);
    }

    /* Output:
    [ 'primeiro', 1 ]
    [ 'segundo', 2 ]
    [ 'terceiro', 3 ]
    */
    ```

### Diferenças Entre Maps e Objetos

* Maps são iteráveis, objetos não.
* Maps podem receber qualquer tipo de dado como chave, objetos não.
* Objetos possuem valores padrões para chaves, maps não.
* Maps possuem chaves ordenadas por inserção, objetos não.
