# PHP

O PHP(um acrônimo para "PHP: Hypertext Preprocessor") é uma linguagem de programação open source mais utilizada para executar scripts no lado do servidor, podendo ser embutida dentro do HTML.

Arquivos PHP possuem a extensão "`.php`".

## Delimitações de Código PHP em HTML

São 5, porém as 2 últimas não funcionam mais.

1. **Super Tag PHP**: Todo o código PHP fica dentro da super tag **`<?php  ?>`**.

1. **Short Open Tag**: Todo o código PHP fica dentro da tag **`<?  ?>`**.

1. **Short Tag PHP**: Apenas quando o script tiver uma linha de código, e essa linha seja um `print` ou `echo`. É a seguinte tag: **`<?= "Olá, Mundo!" ?>`**.

1. **ASP Tag**: Todo o código PHP fica dentro da tag **`<%  %>`**. Não funciana mais hoje em dia.

1. **Tag `<script>`**: Bem parecido com a delimitação de código JavaScript em HTML, **`<script language="php"</script>`**. Hoje em dia não é mais utilizada esta delimitação. Não funciona a partir das novas versões.

> Nota: Caso um arquivo PHP só contenha código PHP, é recomendável omitir a tag de fechamento do PHP.

## Sintaxe PHP

As declarações em PHP terminam com **`;`**.

``` php
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Teste</title>
</head>
<body>
    <h1>Primeira página em PHP</h1>
    <?php
    $txt = 'Olá, Mundo!';
    print $txt;
    ?>
</body>
</html>
```

As palavras-chaves existentes em PHP e as definidas pelo usuário são case-sensitive.

## Comentários

Os comentários de uma linha em PHP são escritos com **'`//`'** ou **'`#`'**, já os comentários de múltiplas linhas ficam entre **'`/*  */`'**.

``` php
// Comentário de 1 linha

# Comentário de uma linha

/* Comentário de múltiplas linhas */
```

Claro que os comentário de uma única linha também podem ser feitos com '`/**/`'.

## Impressão de Valores

Em PHP, as declarações **`echo`** e **`print`** imprimem um valor na tela.

``` php
<?php
$msg = 'Olá, Mundo!';
echo $msg; # Output: "Olá, Mundo!"
```

``` php
<?php
$msg = 'Olá, Mundo!';
print $msg # Output: "Olá, Mundo!"
```

Uma diferença entre estas duas declarações é que `echo` não retorna valores, enquanto `print` retorna 1.

Ambas as funções `echo` e `print` podem ser usadas para criar elementos HTML, como títulos, parágrafos, etc.

``` php
<?php
$title = 'Título';
echo '<h1>' . $title . '</h1>'; # Cria um título
```

## Variáveis e Constantes

### Variáveis

Em PHP, as variáveis possuem um **`$`** antes do nome.

``` php
<?php
$str = 'Olá, Mundo!';
$int = 5;
$float = 7.21;
$bool = true;
```

As variáveis em PHP não precisam ser declaradas explicitamente, na verdade, elas são declaradas automaticante ao atribuir algum valor a elas.

#### Regras Para Variáveis

* Uma variável sempre inicia com `$`.
* O nome da variável deve se iniciar com uma letra ou `_`.
* O nome da variável não pode se iniciar com um número.
* O nome da variável pode conter alpha-numéricos, letras maiúsculas e minúsculas, números e underline(`_`).

#### Escopo de Variáveis

Em PHP existem 3 escopos de variáveis:

* local
* global
* static

##### Variáveis Globais e Locais

Uma variável declarada fora de uma função é possui o escopo global, já uma variável declarada dentro de uma função possui o escopo local.

###### Palavra-chave '`global`'

A palavra-chave **`global`** permite uma função acessar variáveis globais.

``` php
<?php
$num1 = 22;
$num2 = 13;

function printMsg() {
    global $num1, $num2;
    echo $num1 + $num2;
}

printMsg(); # Output: 35
```

Todos as variáveis globais são armazenadas em um array chamado **`$GLOBALS`**. Os índices deste array são os nomes das variáveis globais. Este array pode ser acessado dentro de funções e usado para atualizar as variáveis globais diretamente.

Sendo assim, o mesmo exemplo anterior poderia ser:

``` php
<?php
$num1 = 22;
$num2 = 13;

function soma() {
    echo $GLOBALS['num1'] + $GLOBALS['num2'];
}

soma(); # Output: 35
```

##### Variáveis Estáticas

Estas variáveis são mantidas até mesmo no fim da execução de uma função. Estas variáveis precisam ser declaradas com a palavra-chave `static` antes do nome da variável.

``` php
<?php
function funcao() {
    static $num = 0;
    echo $num;
    $num++;
}

funcao(); # 0
funcao(); # 1
funcao(); # 2
```

Como visto no exemplo acima, o valor da variável `$num` tinha o incremento de 1 a cada execução da função.

### Constantes

São como variáveis, porém não podem ser redefinidas com outros valores.

Você pode definir uma constante usando a função **`define()`** ou a palavra-chave **`const`**.

A sintaxe para `define()` é a seguinte:

``` php
define("IDENTIFICADOR", valor);
```

A sintaxe para `const` é a seguinte:

``` php
const IDENTIFICADOR = valor;
```

1. Identificador: É o nome da constante.
1. Valor: É o valor da constante.

``` php
<?php
define("MENSAGEM", 'Olá, Mundo!');

# Ou

const MENSAGEM = 'Olá, Mundo!';
```

Não esqueça que se houver alguma tentativa de se mudar o valor de uma constante, ocorrerá um erro.

As constantes definidas fora de classes e função são de escopo global por padrão.

## Tipos de Dados

### String

Podem ser escritas com aspas simples ou duplas.

``` php
<?php
$a = 'Olá, Mundo!';
$b = "Olá, Mundo!";
```

#### Funções de String

* **'`mb_strlen()`'**: Retorna o número de caracteres da string.

    ```php
    <?php
    $str = 'Olá, Mundo!';
    echo mb_strlen($str); # Output: 11
    ```

* **'`str_word_count()`'**: Retorna o número de palavras da string.

    ``` php
    <?php
    $str = 'Olá, Mundo!';
    echo str_word_count($str); # Output: 2
    ```

* **'`strpos()`'**: Procura por um texto dentro da string e retorna o índice de sua primeira letra.

    ``` php
    <?php
    $str = 'Olá, Mundo!';
    echo strpos($str, 'Mundo!'); # Output: 6
    ```

* **'`strrev()`'**: Inverte a posição das palavras da string.

    ``` php
    <?php
    $str = 'Olá, Mundo!';
    echo strrev($str); # Output: "!odnuM ,álO"
    ```

* **'`str_replace()`'**: Substitui uma substring dentro da string por outra.

    ``` php
    <?php
    $str = 'Adeus, Mundo!';
    echo str_replace('Adeus', 'Olá', $str);
    # Output: "Olá, Mundo!"
    ```

    Devem ser passados 3 argumentos:

    1. Substring que vai ser substituída.
    1. Substring que vai substituir.
    1. A string em que vai ocorrer essa substituição.

* **'`mb_str_split()`'**: Transforma a string em um array.

    ``` php
    <?php
    $str = 'Olá Mundo';
    print_r(mb_str_split($str, 1));
    # Output: Array ( [0] => O [1] => l [2] => á [3] => [4] => M [5] => u [6] => n [7] => d [8] => o )
    ```

### Tipos Numéricos

A função **`is_numeric()`** retorna `true` se o valor for um número ou uma string numérica, ou `false` em caso contrário.

``` php
<?php
var_dump(is_numeric(22));               # true
var_dump(is_numeric(5.3));              # true
var_dump(is_numeric('Olá, Mundo!'));    # false
var_dump(is_numeric('13'));             # true
```

#### Integer

Em PHP, são todos os números não decimais entre -2,147,483,648 e 2,147,483,647.

``` php
<?php
$int = 5123;
```

##### Funções de Integer

* **'`is_int()`', '`is_integer()`', '`is_long()`'**: Retorna `true` se o valor passado for inteiro, ou `falso`, em caso contrário.

    ``` php
    <?php
    var_dump(is_int(5));        # true
    var_dump(is_integer(2.7));  # false
    var_dump(is_long('3'));     # false
    ```

##### Conversão Para Integer

As funções `(int)`, `(integer)` e `intval()` são usadas para converter algum valor para inteiro.

``` php
<?php
$n = 7.3;
var_dump((int)$n);  # 7
```

#### Float

São os números que possuem casas decimais.

``` php
<?php
$num = 22.13
```

##### Funções de Float

* **'`is_float()`', '`is_double()`'**: Retorna `true` se o valor passado for float, ou `false`, em caso contrário.

    ``` php
    <?php
    var_dump(is_float(1.3));    # true
    var_dump(is_double(2));     # false
    ```

* **'`round()`'**: Retorna o número inteiro mais próximo do valor digitado.

    ``` php
    <?php
    echo round(5.2); # 5
    echo round(1.8); # 2
    echo round(3.5); # 4
    ```

### Boolean

São os valores **`true`**(verdadeiro) e **`false`**(falso).

``` php
<?php
$v = true
$f = false
```

### Array

Um array armazena múltiplos valores em uma única variável.

``` php
<?php
$my_array = array(5, 'Olá', 3.2, true)
```

### Object

Um objeto é uma instância de uma classe.

``` php
<?php
class Pessoa {
    public $nome;
    public function __construct($nome) {
        $this->nome = $nome;
    }

    public function apresentacao() {
        return 'Olá, meu nome é ' . $this->nome . '!';
    }
}

$pessoa1 = new Pessoa('João');
echo $pessoa1 -> apresentacao();
# Output: "Olá, meu nome é João!"
```

Neste exemplo, a variável `$pessoa1` é do tipo objeto.

### Null

É um valor nulo. Variáveis com o valor `null` são variáveis sem valor.

``` php
<?php
$var = null;
```

O valor `null` é considerado não verdadeiro em expressões, assim como `false`.

### Resource

O tipo de dado `resource` é usado para representar um recurso externo ou manipulador de recursos, como conexões de banco de dados, fluxos de arquivo ou ponteiros para recursos externos.

## Números

### Número Infinito

Um número que é maior que `PHP_FLOAT_MAX` é considerado infinito.

As funções **`is_finite()`** e **`is_infinite()`** verificam se um valor é ou não infinito.

### NaN

"NaN" é um acrônimo para "Not a Number", que significa que não é um número.

A função **`is_nan()`** veririca se um valor é ou não `NaN`.

`NaN` é retornado em casos de cálculo inválido.

### Funções Numéricas

* **'`pi()`'**: Retorna o valor de PI.

    ``` php
    <?php
    echo pi(); # 3.1415926535898
    ```

    Esta função funciona da mesma forma que a constante **`M_PI`**, que possui o valor de pi.

* **'`abs()`'**: Retorna o valor absoluto de um número.

    ``` php
    <?php
    echo abs(-21.31); # 21.31
    ```

* **'`sqrt()`'**: Retorna a raíz quadrada de um número.

    ``` php
    <?php
    echo sqrt(25); # 5
    ```

* **'`rand()`'**: Retorna um número aleatório.

    ``` php
    <?php
    echo rand(0, 10);
    # Retorna um número aleatório entre 0 e 10
    ```

    Se não for passado os valores mínimo e máximo, retorna um número aleatório de qualquer maneira, porém sem limites de mínimo e máximo.

* **'`base_convert()`'**: Converte um valor de uma base para outra (ex.: base 10 para base 8).

    ``` php
    <?php
    $num = 22;
    echo base_convert($num, 10, 2);     # Para binário
    echo '<br>';
    echo base_convert($num, 10, 8);     # Para Octal
    echo '<br>';
    echo base_convert($num, 10, 16);    # Para Hexadecimal
    ```

    Devem ser passados 3 argumentos:

    1. Valor a ser convertido
    1. Base do valor que vai ser convertido
    1. Base para conversão

* **'`floor()`'**: Arredonda um valor para baixo.

    ``` php
    <?php
    echo floor(32.7); # 32
    echo '<br>';
    echo floor(23.2); # 23
    echo '<br>';
    echo floor(55.5); # 55
    ```

* **'`ceil()`'**: Arredonda um valor para cima.

    ``` php
    <?php
    echo ceil(32.7); # 33
    echo '<br>';
    echo ceil(23.2); # 24
    echo '<br>';
    echo ceil(55.5); # 56
    ```

* **'`round()`'**: Arredonda um valor.

    ``` php
    <?php
    echo round(32.7); # 33
    echo '<br>';
    echo round(23.2); # 23
    echo '<br>';
    echo round(55.5); # 56
    ```

* **'`intdiv()`'**: Faz a divisão inteira de um valor.

    ``` php
    <?php
    echo intdiv(5, 2); # 2
    ```

* **'`hypot()`'**: Mostra o valor da hipotenusa a partir do valor de dois catetos.

    ``` php
    <?php
    echo hypot(2, 3); # 3.605551275464
    ```

* **'`sin()`', '`cos()`', '`tan()`'**: Retornam os valores de seno, cosseno e tangente, respectivamente, a partir de um valor em radianos.

    ``` php
    <?php
    echo sin(30); # -0.98803162409286
    echo '<br>';
    echo cos(30); # 0.15425144988758
    echo '<br>';
    echo tan(30); # -6.4053311966463
    ```

* **'`min()`', '`max()`'**: Mostram os valores mínimo e máximo de uma sequência.

    ``` php
    <?php
    $sequencia = array(3, 2, 0, 5, 6, 9, 1, 8, 4, 7);
    echo min($sequencia); # 0
    echo '<br>';
    echo max($sequencia); # 9
    ```

## Operadores

### Operadores Aritméticos

* **'`+`'**: Adição

    ``` php
    <?php
    echo 5 + 2; # 7
    ```

* **'`-`'**: Subtração

    ``` php
    <?php
    echo 10 - 2; # 8
    ```

* **'`*`'**: Multiplicação

    ``` php
    <?php
    echo 7 * 3; # 21
    ```

* **'`/`'**: Divisão

    ``` php
    <?php
    echo 10 / 2; # 5
    ```

* **'`%`'**: Módulo (resto da divisão)

    ``` php
    <?php
    echo 7 % 2; # 1
    ```

* **'`**`'**: Exponenciação

    ``` php
    <?php
    echo 5 ** 2; # 25
    ```

### Operadores de Incremento e Decremento

* **'`++$x`'**: Pré-incremento.

    Adiciona mais um ao valor da variável antes de executar uma ação.

    ``` php
    <?php
    $v = 10;
    echo ++$v; # 11
    ```

* **'`$x++`'**: Pós-incremento.

    Adiciona mais um ao valor da variável depois de executar uma ação.

    ``` php
    <?php
    $v = 10;
    echo $v++; # 10
    # `$v` passa a ser 11 após a impressão
    ```

* **'`--$x`'**: Pré-decremento.

    Retira um do valor da variável antes de executar uma ação.

    ``` php
    <?php
    $v = 10;
    echo --$v; # 9
    ```

* **'`$x--`'**: Pós-decremento.

    Retira um valor da variável depois de executar uma ação.

    ``` php
    <?php
    $v = 10;
    echo $v--; # 9
    # `$v` passa a ser 9 após a impressão
    ```

### Operadores de Comparação

* **'`==`'**: Retorna `true` se os valores forem iguais.

    ``` php
    <?php
    var_dump(5 == 5);       # true
    var_dump(2 == 3);       # false
    var_dump(1 == '1');     # true
    ```

* **'`===`'**: Retorna `true` se os valores forem idênticos.

    ``` php
    <?php
    var_dump(5 === 5);       # true
    var_dump(2 === 3);       # false
    var_dump(1 === '1');     # true
    ```

* **'`!=`', '`<>`'**: Retorna `true` se os valores forem diferentes.

    ``` php
    <?php
    var_dump(3 != 5);   # true
    var_dump(6 != 6);   # false
    var_dump(2 != '2'); # false
    ```

* **'`!==`'**: Retorna `true` se os valores não forem idênticos.

    ``` php
    <?php
    var_dump(3 !== 5);   # true
    var_dump(6 !== 6);   # false
    var_dump(2 !== '2'); # true
    ```

* **'`>`'**: Retorna `true` se o valor da esquerda for maior que o da direita.

    ``` php
    <?php
    var_dump(5 > 2);    # true
    var_dump(3 > 7);    # false
    var_dump(-3 > 3);   # false
    ```

* **'`<`'**: Retorna `true` se o valor da esquerda for menor que o da direita.

    ``` php
    <?php
    var_dump(2 < 3);    # true
    var_dump(5 < 2);    # false
    var_dump(1 < -1);   # false
    ```

* **'`>=`'**: Retorna `true` se o valor da esquerda for maior ou igual o valor da direita.

    ``` php
    <?php
    var_dump(5 >= 3);    # true
    var_dump(2 >= 2);    # true
    var_dump(-1 >= 4);   # false
    ```

* **'`<=`'**: Retorna `true` se o valor da esquerda for menor ou igual o valor da direita.

    ``` php
    <?php
    var_dump(2 <= 4);    # true
    var_dump(3 <= 1);    # false
    var_dump(1 <= -3);   # false
    ```

* **'`<=>`'**: Retorna 1 se o valor da esquerda for maior que o da direita, retorna 0 se os valores forem iguais, ou retorna -1 se o valor da direita for maior que o da esquerda.

    ``` php
    <?php
    var_dump(2 <=> 1);  #  1
    var_dump(5 <=> 5);  #  0
    var_dump(3 <=> 7);  # -1
    ```

### Operadores Lógicos

* **'`and`', '`&&`'**: Verdadeiro se ambos forem verdadeiros.

    ``` php
    <?php
    var_dump(true && true);     # true
    var_dump(true && false);    # false
    var_dump(false && true);    # false
    var_dump(false && false);   # false

    # Ou

    var_dump(true and true);    # true
    var_dump(true and false);   # false
    var_dump(false and true);   # false
    var_dump(false and false);  # false
    ```

* **'`or`', '`||`'**: Verdadeiro pelo menos um for verdadeiro.

    ``` php
    <?php
    var_dump(true || true);     # true
    var_dump(true || false);    # true
    var_dump(false || true);    # true
    var_dump(false || false);   # false

    # Ou

    var_dump(true or true);    # true
    var_dump(true or false);   # true
    var_dump(false or true);   # true
    var_dump(false or false);  # false
    ```

* **'`xor`'**: Verdadeiro se pelo menos um for verdadeiro, mas não ambos.

    ``` php
    <?php
    var_dump(true xor true);     # false
    var_dump(true xor false);    # true
    var_dump(false xor true);    # true
    var_dump(false xor false);   # false
    ```

* **'`!`'**: Se verdadeiro, se torna falso, e se falso, se torna verdadeiro.

    ``` php
    <?php
    var_dump(true && !true);     # false
    var_dump(true || !false);    # true
    var_dump(!false xor true);   # false
    ```

## Estruturas Condicionais

### Declaração '`if`'

Executa um bloco se sua condição for verdadeira.

Sintaxe:

``` php
<?php
if (condicao) {
    # bloco de código;
}
```

Exemplo:

``` php
<?php
$num = 10;
if ($num > 5) {
    echo "O número $num é MAIOR que 5";
}
```

A declaração `if` inicia uma estrutura condicional, onde só pode haver um `if`, vários `elseif`, e um `else`.

### Declaração '`elseif`'

Esta estrutura é um outro `if` dentro de uma estrutura condicional. É usado quando apenas o `if` não abrange todas as possibilidades.

Exemplo:

``` php
<?php
$num = 3;
if ($num > 5) {
    echo "O número $num é MAIOR que 5";
} elseif ($num < 5) {
    echo "O número $num é MENOR que 5";
}
```

Em uma estrutura condicional, podem há limites quanto à quantidade de `elseif`s.

### Declaração '`else`'

Executa um bloco caso as outras declarações (`if` e `elseif`) não testem verdadeiro.

Exemplo:

``` php
<?php
$num = 5;
if ($num > 5) {
    echo "O número $num é MAIOR que 5";
} elseif ($num < 5) {
    echo "O número $num é MENOR que 5";
} else {
    echo "O número $num é IGUAL a 5";
}
```

Um outro exemplo:

``` php
<?php
$num = 5;
if ($num > 5) {
    echo "O número $num é MAIOR que 5";
} else {
    echo "O número $num é MENOR ou IGUAL a 5";
}
```

### Condição Ternária

Os operadores **`?:`** conduzem uma condição ternária.

Sintaxe:

``` php
<?php
condicao ? "executa quando true" : "executa quando false"
```

Caso os códigos a serem executados possuam a mesma função em comum, como mostrar uma mensagem, a função deve ser especificado antes da condição:

``` php
<?php
acao condicao ? "executa quando true" : "executa quando false"
```

Exemplo:

``` php
<?php
$num = 10;
echo $num == 10 ? "Valor é IGUAL a 10" : "Valor é DIFERENTE de 10"
# Mostrará: "Valor é IGUAL a 10"
```

### Operador de Coalescência Nula

Representada por **`??`**, atribui um valor a uma variável caso a mesma não tenha sido definida ou seja nula.

``` php
<?php
$msg = $msg ?? "Olá, Mundo!";
```

No exemplo acima, a variável `$msg` irá receber o valor `"Olá, Mundo!"` apenas se ela já não tenha sido definida ou seja nula.

### Declaração '`switch`'

Ao passar uma variável ou expressão, executa o bloco cujo o valor seja igual ao valor da variável ou expressão passada.

Sintaxe:

``` php
<?php
switch (expressao) {
    case valor1:
        # Código a ser executado
        break;
    case valor2:
        # Código a ser executado
        break;
    case valor3:
        # Código a ser executado
        break;
    default:
        # Código a ser executado caso nenhum `case` seja correspondido.
}
```

Exemplo:

``` php
<?php
$num = 2;
switch ($num) {
    case 1:
        echo "Número 1";
        break;
    case 2:
        echo "Número 2";
        break;
    case 3:
        echo "Número 3";
        break;
    default:
        echo "Número passado é diferente de 1, 2 e 3";
}

# Será executado o segundo `case`
```

O bloco **`default`** será executado caso nenhum `case` tenha sido correspondido.

A declaração **`break`** sai do `switch` ao fim do bloco, sem ele, seriam testados os outros `case`s, e mesmo que eles testem falso, será executado o próximo bloco mesmo assim.

## Arrays

Em PHP, os arrays são declarados a utilizando a função **`array()`** ou utilizando colchetes **`[]`**.

Sintaxe:

``` php
<?php
$my_array = array('Item 1', 'Item 2', 'Item 3');

# Ou

$my_array = ['Item 1', 'Item 2', 'Item 3'];
```

### Tipos de Arrays

Em PHP, existem 3 tipos de array: Array Indexado, Array Assossiativo e Array Multidimensional.

#### Array Indexado

Um array indexado permite o acesso ao seus elementos por meio de índices:

``` php
<?php
$my_array = array('Item 1', 'Item 2', 'Item 3');
echo $my_array[0]; # Item 1
echo $my_array[1]; # Item 2
echo $my_array[2]; # Item 3
```

#### Array Assossiativo

Um array assossiativo possui chaves que se referem a um valor.

``` php
<?php
$my_array = [
  'Chave 1'=>'Item 1',
  'Chave 2'=>'Item 2',
  'Chave 3'=>'Item 3'
];

echo $my_array['Chave 1']; # Item 1
echo $my_array['Chave 2']; # Item 2
echo $my_array['Chave 3']; # Item 3
```

#### Array Multidimensional

Um array multidimensional é um array que possui outros arrays dentro de si, ou seja, é um array de arrays.

``` php
<?php
$my_array = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

echo $my_array[0][0]; # 1
echo $my_array[0][1]; # 2
echo $my_array[0][2]; # 3
echo $my_array[1][0]; # 4
echo $my_array[1][1]; # 5
echo $my_array[1][2]; # 6
echo $my_array[2][0]; # 7
echo $my_array[2][1]; # 8
echo $my_array[2][2]; # 9
```

### Funções de Array

* **'`count()`'**: Retorna o número de elementos do array.

    ``` php
    <?php
    $my_array = ['Item 1', 'Item 2', 'Item 3'];
    echo count($my_array); # Output: 3
    ```

* **'`sort()`'**: Organiza o array em ordem crescente.

    ``` php
    <?php
    $my_array = [2, 3, 1, 5, 4];
    sort($my_array);
    var_dump($my_array);
    # Será: [1, 2, 3, 4, 5]
    ```

* **'`rsort()`'**: Organiza o array em ordem decrescente.

    ``` php
    <?php
    $my_array = [2, 3, 1, 5, 4];
    rsort($my_array);
    var_dump($my_array);
    # Será: [5, 4, 3, 2, 1]
    ```

* **'`asort()`'**: Organiza o array assossiativo em ordem crescente a partir dos seus valores.

    ``` php
    <?php
    $my_array = [
    'Chave 2'=>'Item 2',
    'Chave 3'=>'Item 3',
    'Chave 1'=>'Item 1'
    ];
    asort($my_array);
    var_dump($my_array);
    # Mostra o array organizado
    ```

* **'`arsort()`'**: Organiza o array assossiativo em ordem decrescente a partir dos seus valores.

    ``` php
    <?php
    $my_array = [
    'Chave 2'=>'Item 2',
    'Chave 3'=>'Item 3',
    'Chave 1'=>'Item 1'
    ];
    arsort($my_array);
    var_dump($my_array);
    # Mostra o array organizado (decrescente)
    ```

* **'`ksort()`'**: Organiza o array assossiativo em ordem crescente a partir das suas chaves.

    ``` php
    <?php
    $my_array = [
    'Chave 2'=>'Item 2',
    'Chave 3'=>'Item 3',
    'Chave 1'=>'Item 1'
    ];
    ksort($my_array);
    var_dump($my_array);
    # Mostra o array organizado
    ```

* **'`krsort()`'**: Organiza o array assossiativo em ordem decrescente a partir das suas chaves.

    ``` php
    <?php
    $my_array = [
    'Chave 2'=>'Item 2',
    'Chave 3'=>'Item 3',
    'Chave 1'=>'Item 1'
    ];
    krsort($my_array);
    var_dump($my_array);
    # Mostra o array organizado (decrescente)
    ```

## Loops

### '`for`'

Executa um bloco em um número específico de vezes. A sintaxe é a seguinte:

``` php
for (contador_inicial; teste; incremento) {
    # Bloco a ser executado
}
```

Exemplo:

``` php
<?php
for ($c = 0; $c <= 10; $c++) {
    echo "Número $c <br>";
}
# Imprime os números de 0 a 10
```

### '`while`'

Repete um bloco enquanto sua condição for verdadeira.

Sintaxe:

``` php
<?php
while (condicao) {
    # Bloco a ser executado
}
```

Exemplo:

``` php
<?php
$c = 10;
while ($c != 0) {
    echo "Número $c <br>";
    $c--;
}
# Imprime os números de 10 até 1
```

### '`do...while`'

Executa um bloco uma vez, e em seguida verifica uma condição, se for verdadeira, mantém o loop até que se torne falsa.

``` php
<?php
$c = 0;
do {
    echo "Número $c <br>";
    $c++;
} while ($c <= 10);
# Imprime os números de 0 a 10
```

A diferença do loop `do...while` para `while`, é que `do...while` sempre executa o bloco pelo menos uma vez.

``` php
<?php
$c = 0;
do {
    echo "Número $c <br>";
    $c++;
} while (false);
# Output: "Número 0"
```

### '`foreach`'

Percorre um array, capturando os pares chave-valor.

Exemplo:

``` php
<?php
$my_array = array(
    'Primeiro'=> 1,
    'Segundo'=> 2,
    'Terceiro'=> 3
);

foreach($my_array as $value) {
    echo "Número $value <br>";
}
# Imprime os valores do array
```

Para capturar também as chaves:

``` php
<?php
$my_array = array(
    'Primeiro'=> 1,
    'Segundo'=> 2,
    'Terceiro'=> 3
);

foreach($my_array as $key => $value) {
    echo "$key: $value <br>";
}
# Imprime os valores junto às chaves
```

### Declarações `break` e `continue`

#### '`break`'

A declaração `break` interrompe um loop no mesmo momento.

``` php
<?php
$c = 0;
while (true) {
    $c++;
    echo "Número $c <br>";
    if ($c == 10) { break; }
}
# Imprime os números de 1 a 10
```

#### '`continue`'

A declaração `continue` pula para a próxima repetição, ignorando se houver mais códigos abaixo.

``` php
<?php
for ($c = 0; $c <= 10; $c++) {
    if ($c % 2 != 0) { continue; }
    echo "Número $c <br>";
}
# Imprime os números pares entre 0 e 10
```

## Funções

A declaração **`function`** define uma função. A sintaxe é a seguinte:

``` php
<?php
function nomeFuncao(param1, param2, ..., param9) {
    # Declaração
}
```

Exemplo:

``` php
<?php
function saudacao() {
    echo "Olá, Mundo! <br>";
}

saudacao(); # Chama a função
```

As funções normalmente são escritas com a primeira palavra em minúscula e as demais capitalizadas (`nomeFuncao()`, `somaValores()`).

### Parâmetros e Argumentos

Os parâmetros são os dados que uma função deve receber.

Os argumentos são relativos aos parâmetros, e são passados ao chamar a função.

Exemplo:

``` php
<?php
function corFavorita($cor) {
    echo "Minha cor favorita é $cor!";
}

CorFavorita('vermelho');
# "Minha cor favorita é vermelho!
CorFavorita('verde');
# "Minha cor favorita é verde!
CorFavorita('azul');
# "Minha cor favorita é azul!
```

Os parâmetros, às vezes, podem receber um valor inválido, por esse motivo, é importante especificar o tipo de valor que o parâmetro espera receber.

Exemplo:

``` php
<?php
function soma(int $num1, int $num2) {
    echo "A soma entre $num1 e $num2 é " . $num1 + $num2;
}
```

#### Valor Padrão Para Argumento

Você pode definir um valor padrão para um argumento atribuindo ao argumento o seu valor padrão.

Exemplo:

``` php
<?php
function saudacao($pessoa = 'Mundo') {
    echo "Olá, $pessoa!";
}

saudacao('Lucas');
# "Olá, Lucas!"

saudacao();
# "Olá, Mundo!"
```

#### Argumento Por Referência

Para que o valor de um argumento seja imutável durante a execução da função, você pode adicionar **`&`** ao início do nome do argumento.

``` php
<?php
function addDez(&$num) {
  $num += 10;
}

$n = 2;
addDez($n);
echo $n;
```

### Retorno

A declaração **`return`** faz o retorno de algum valor.

Exemplo:

``` php
<?php
function soma(int $num1, int $num2) {
    return $num1 + $num2;
}

$s = soma(13, 22);
echo "Soma: $s"
```

Neste exemplo, a função `Soma()` retornou a soma de 13 e 22 à variável `$s`.

#### Tipo de Retorno

Você pode definir o tipo de dado que a função retorna, para isso:

``` php
<?php
function soma(int $num1, int $num2) : int {
    return $num1 + $num2;
}

$s = soma(13, 22);
echo "Soma: $s"
```

## Expressões Regulares

Uma expressão regular, ou RegExp, é uma sequência de caracteres que forma um padrão de pesquisa.

``` php
<?php
$exp = "/mundo/i";
$msg = 'Olá, Mundo!';
echo preg_match($exp, $msg); # 1
```

No exemploa acima, as barras são os delimitadores, que poderiam também ser outros caracteres, como `#`, `~`, entre outros.

O caractere `i` é um modificador, além dele há `m` e `u`.

### Funções de Expressões Regulares

* **'`preg_match()`'**: Retorna `1` se o padrão existir na string, ou `0`, em caso contrário

    ``` php
    <?php
    $exp = "#[0-9]{2}[/][0-9]{2}[/][0-9]{4}#i";
    echo preg_match($exp, '10/09/2023');    # 1
    echo preg_match($exp, '10/09/202');     # 0
    echo preg_match($exp, '10/9/2023');     # 0
    ```

* **'`preg_match_all()`'**: Retorna o número de vezes que o padrão foi encontrado dentro da string.

    ``` php
    <?php
    $exp = "/[a][0-9][a-z][a-z]/i";
    $str = 'a321 a3b1 akc2 a2bc a5sb a7s8 a0ll';
    echo preg_match_all($exp, $str); # 3
    ```

* **'`preg_replace()`'**: Retorna uma nova string, onde os padrões encontrados são substituídos de acordo com o que foi especificado.

    ``` php
    <?php
    $exp = "/([0-9]{4})[-]([0-9]{2})[-]([0-9]{2})/i";
    $str = '2023-09-10';
    echo preg_replace($exp, "$3/$2/$1", $str); # 10/09/2023
    ```

### Modificadores

* **'`i`'**: Pesquisa sem diferenciar maiúsculas de minúsculas.
* **'`m`'**: Faz uma pesquisa em múltiplas linhas.
* **'`u`'**: Corresponde corretamente aos padrões codificados em UTF-8.

## Superglobais

São as variáveis que podem ser acessadas de qualquer lugar do programa.

São elas:

* $GLOBALS
* $_SERVER
* $_REQUEST
* $_GET
* $_POST
* $_FILES
* $_COOKIE
* $_ENV
* $_SESSION

### '`$GLOBALS`'

A superglobal `$GLOBALS` é um array assossiativo que armazena todas as variáveis globais.

``` php
<?php
$n1 = 5;
$n2 = 2;

function soma() {
    return $GLOBALS['n1'] + $GLOBALS['n2'];
}

$resultado = soma();
echo "A soma entre $n1 e $n2 é $resultado."
```

### '`$_SERVER`'

A variável superglobal `$_SERVER` guarda informações sobre o servidor. Alguns exemplo são:

``` php
<?php
echo $_SERVER['PHP_SELF'];
echo "<br>";
echo $_SERVER['SERVER_NAME'];
echo "<br>";
echo $_SERVER['HTTP_HOST'];
echo "<br>";
echo $_SERVER['HTTP_USER_AGENT'];
echo "<br>";
echo $_SERVER['SCRIPT_NAME'];
```

### '`$_REQUEST`'

A variável superglobal `$_REQUEST` é usada para coletar informações enviadas por formulários HTML.

### '`$_GET`'

A variável superglobal `$_GET` é usada para coletar informações enviadas de um formulario HTML com método `get`.

### '`$_POST`'

A variável superglobal `$_POST` é usada para coletar informações enviadas via formulário HTML com método `post`.

## Classes

São criadas a partir da palavra-chave **`class`**, que é seguida pelo nome da classe e chaves que engloba as declarações da classe dentro de si.

A sintaxe é a seguinte:

``` php
<?php
class NameClass {
    # Declarações
}
```

### Instanciação

A palavra-chave **`new`** cria uma instância de uma classe.

A sintaxe é a seguinte:

``` php
<?php
class TestClass {
    # Declaração
}

$obj = new TestClass;
```

#### '`instanceof`'

A palavra-chave `instanceof` é utilizada para verificar se um objeto pertence a uma classe específica.

``` php
<?php
class OlaMundo {
    function msg() {
        echo "Olá, Mundo!";
    }
}

$obj = new OlaMundo;
var_dump($obj instanceof OlaMundo); # true
```

No exemplo acima, é verificado se a variável `$obj` é um objeto da classe `OlaMundo`.

### Propriedades

Propriedades são variáveis que guardam dados de um objeto, o que significa que instâncias de uma mesma classe podem ter propriedades com valores diferentes.

``` php
<?php
class TestClass {
    public $prop1, $prop2;
}
```

#### Propriedades Estáticas

Podem ser acessados a partir do nome da classe, sem a necessidade de criação de uma instância. São criadas a partir da palavra-chave **`static`** e podem ser acessadas utilizando notação de classe (**`::`**).

Exemplo:

``` php
<?php
class Test {
    static $propriedade = 'Olá, Mundo!';
}

echo Test::$propriedade; # Imprime "Olá, Mundo!"
```

### Métodos

São escritos da mesma forma que funções.

``` php
<?php
class Soma {
    public $num1, $num2;

    function somar() {
        return $this->num1 + $this->num2;
    }
}

$obj = new Soma;
$obj->num1 = 5;
$obj->num2 = 2;

echo $obj->somar(); // 7
```

Neste exemplo, a classe `Soma` pussui o método `somar()`, que soma as propriedades `num1` e `num2`.

A variável **`$this`** se refere ao objeto atual, no caso, o objeto `$obj`.

#### Métodos Estáticos

A palavra-chave **`static`** define um método como estático, que significa que esse método pode ser acessado sem a criação de uma instância, sendo chamado a partir do nome da própria classe.

Exemplo:

``` php
<?php

class Calculadora {
    static function somar($num1, $num2) {
        return $num1 + $num2;
    }

    static function subtrair($num1, $num2) {
        return $num1 - $num2;
    }

    static function multiplicar($num1, $num2) {
        return $num1 * $num2;
    }

    static function dividir($num1, $num2) {
        return $num1 / $num2;
    }

}

echo Calculadora::somar(10, 2);         # 12
echo Calculadora::subtrair(10, 2);      # 8
echo Calculadora::multiplicar(10, 2);   # 20
echo Calculadora::dividir(10, 2);       # 5
```

### Método '`__construct()`'

O método **`__construct()`** é usado para iniciar as propriedades de um objeto assim que ele for criado. Ele é executado no momento em que um objeto da classe é criado.

``` php
class Pessoa {
    public $nome, $idade;

    public function __construct($nome, $idade) {
        $this->nome = $nome;
        $this->idade = $idade;
    }
}
```

Os argumentos do método `__construct()` devem ser passados ao criar o objeto.

### Método '`__destruct()`'

O método **`__destruct()`** é o oposto do método `__construct()`, pois é executado no fim da classe/script.

``` php
<?php
class OlaMundo {
    function __construct() {
        echo 'Olá, Mundo!';
    }

    function __destruct() {
        echo 'Tchau, Mundo!';
    }
}

$obj = new OlaMundo; # Output: Olá, Mundo!
unset($obj); # Output: Tchau, Mundo!
```

A função **`unset()`** remove a referência de uma variável, o que tornando-a inacessível e fazendo com que a memória seja liberada.

No exemplo acima, a variável `$obj` perde sua referência à classe, deixando de ser um objeto, e por isso o método `destruct()` é executado.

Como dito anteriormente, o método `destruct()` também é executado ao fim do script, então, mesmo que a função `unset()` não estivesse presente no código, o resultado seria o mesmo.

``` php
$pessoa1 = new Pessoa('Julia', 11);
```

### Getters e Setters

É possível ler ou alterar o valor de uma propriedade fora da classe, contanto que essa propriedade seja pública.

``` php
<?php
class Test {
    public $propriedade = 10;
}

$obj = new Test;
echo $obj->propriedade; # 10

$obj->propriedade = 'Olá, Mundo!';
echo $obj->propriedade; # Olá, Mundo!
```

Entretanto, caso essa propriedade seja privada ou protegida, não é possível ler ou alterar o valor dessa propriedade dessa forma. Para isso, existem os métodos especiais `__get()` e `__set()`;

``` php
<?php
class Test {
    private $propriedade = 10;

    function __get($nome_propriedade) {
        return $this->$nome_propriedade;
    }

    function __set($nome_propriedade, $novo_valor) {
        $this->propriedade = $novo_valor;
    }
}

$obj = new Test;
echo $obj->__get('propriedade'); # 10

$obj->__set('propriedade', 'Olá, Mundo!');
echo $obj->__get('propriedade'); # Olá, Mundo!
```

No exemplo acima, é importante lembrar que irá ocorrer um erro caso seja passado um nome inválido ao usar os métodos `__get` e `__set`. Por isso, você pode usar a função `property_exists()` para verificar se a propriedade existe ou não.

``` php
<?php
class Test {
    private $propriedade = 10;

    function __get($nome_propriedade) {
        if (property_exists($this, $nome_propriedade)) {
            return $this->$nome_propriedade;
        } else {
            return null;
        }
    }

    function __set($nome_propriedade, $novo_valor) {
        if (property_exists($this, $nome_propriedade)) {
            $this->$nome_propriedade = $novo_valor;
        }
    }
}

$obj = new Test;
echo $obj->__get('propriedade'); # 10

$obj->__set('propriedade', 'Olá, Mundo!');
echo $obj->__get('propriedade'); # Olá, Mundo!
```

### Encapsulamento

Encapsulamento é um conceito que controla o acesso às propriedades e métodos de uma classe.

Em PHP, pode ser:

* **'`public`'**: Acessível de qualquer lugar.
* **'`private`'**: Acessível somente de dentro da própria classe.
* **'`protected`'**: Acessível somante de dentro da própria classe e suas filhas (herança).

Caso não especificado o tipo de encapsulamento ao definir um método ou propriedade, será automaticamente público.

### Herança

A palavra-chave **`extends`** permite criar uma herança, fazendo com que uma classe possua todas as funcionalidades públicas e protegidas da classe pai.

``` php
<?php
class ClassePai {
    protected $msg = 'Olá, Mundo!';
}

class ClasseFilha extends ClassePai {
    function mostrar_mensagem() {
        echo $this->msg;
    }
}

$obj = new ClasseFilha;
$obj->mostrar_mensagem();
```

Neste exemplo, a `ClasseFilha` herda da `ClassePai`, tendo o acesso à propriedade `$msg` e possuindo um método que mostra o valor dessa propriedade. Ao fim, é criado uma instância da `ClasseFilha` que chama o método `mostrar_mensagem()` e mostra o valor da propriedade protegida.

A palavra-chave **`parent`** é usada para chamar métodos ou constantes da classe pai a partir da classe filha. Seguido da palavra-chave `parent`, vêm `::` e o nome do método ou constante.

``` php
<?php
class ClassePai {
    const PI = 3.1415926535898;

    function mensagem() {
        return 'Olá, Mundo!';
    }
}

class ClasseFilha extends ClassePai {
    function ola_mundo() {
        echo parent::mensagem();
    }

    function pi() {
        echo parent::PI;
    }
}

$obj = new ClasseFilha;
$obj->ola_mundo();
$obj->pi();
```

#### Construtor da Classe Pai

Para executar o método `__construct()` da classe pai, é necessário chamá-la na classe filha.

``` php
<?php
class ClassePai {
    function __construct() {
        echo 'Olá, Mundo!';
    }
}

class ClasseFilha extends ClassePai {
    function __construct() {
        parent::__construct();
    }
}

$obj = new ClasseFilha; # Imprime "Olá, Mundo!"
```

#### Substituição de Métodos

Caso exista métodos com o mesmo nome em ambas as classes, pai e filha, o método da classe filha irá substituir o da classe pai.

``` php
<?php
class ClassePai {
    function mensagem() {
        echo 'Olá, Mundo!';
    }
}

class ClasseFilha extends ClassePai {
    function mensagem() {
        echo 'Olá, PHP!';
    }
}

$obj = new ClasseFilha;
$obj->mensagem(); # Output: Olá, PHP!
```

#### Palavra-chave '`final`'

A palavra-chave **`final`** torna impossível substituir um método ou classe passado como herança.

``` php
<?php
class ClassePai {
    final function mensagem() {
        echo 'Olá, Mundo!';
    }
}

class ClasseFilha extends ClassePai {
    function mensagem() {
        echo 'Olá, PHP!';
    }
}

$obj = new ClasseFilha;
$obj->mensagem();

# Ocorre um erro
```

No código acima é lançado um erro, pois a `ClasseFilha` tenta substituir o método `mensagem()` da `ClassePai`, que não permite tal ação por conta da palavra-chave `final`.

A palavra-chave `final` também pode ser aplicado no início da declaração da classe, fazendo com que nenhum método na classe possa ser substituído em suas subclasses.

### Constantes em Classes

Em uma classe, você pode definir uma constante a partir da palavra-chave **`const`**. Essa constante pode ser acessada por meio da notação de classe (**`::`**).

``` php
<?php
class MinhaClasse {
    const MENSAGEM = 'Olá, Mundo!';
}

$obj = new MinhaClasse;
echo $obj::MENSAGEM; # Output: Olá, Mundo!
```

> **OBS.: Constantes são sempre públicas e estáticas.**

### Classes Abstratas

Uma classe abstrata é um modelo para outras classes, onde todo método abstrato definido dentro de uma classe abstrata deve ser definido também em classes que herdam esse modelo.

``` php
<?php
abstract class Celular {
    abstract function ligar_celular();
}

class Samsung extends Celular {
    function ligar_celular() {
        echo 'O seu Samsung está ligando!';
    }
}

class Motorola extends Celular {
    function ligar_celular() {
        echo 'O seu Motorola está ligando!';
    }
}

class Iphone extends Celular {
    function ligar_celular() {
        echo 'O seu Iphone está ligando!';
    }
}

$samsung = new Samsung;
$motorola = new Motorola;
$iphone = new Iphone;

echo $samsung->ligar_celular();
echo '<br>';
echo $motorola->ligar_celular();
echo '<br>';
echo $iphone->ligar_celular();
```

### Interfaces

**Interfaces** são bem parecidas com Classes Abstratas, porém, possuem algumas diferenças:

* Interfaces não podem ter propriedades
* Todos os métodos são abstratos
* Todos os métodos são públicos

### Traits

**Traits** permitem que uma classe utilize métodos sem criar uma herança com outra classe. Um treit é criado a partir da palavra-chave **`trait`**, e para usá-los em uma classe, se utiliza a palavra-chave **`use`**.

``` php
<?php
trait Mensagem1 {
    function msg1() {
        echo 'Olá, Mundo!';
    }

    function msg2() {
        echo 'Olá, PHP!';
    }
}

class Test {
    use Mensagem1;
}

$obj = new Test;
$obj->msg1(); # Olá, Mundo!
echo '<br>';
$obj->msg2(); # Olá, PHP!
```

É possível usar mais de um trait em uma mesma classe, o que seria uma "herança múltipla".

``` php
<?php
trait Mensagem1 {
    function msg1() {
        echo 'Olá, Mundo!';
    }
}

trait Mensagem2 {
    function msg2() {
        echo 'Olá, PHP!';
    }
}

class Test {
    use Mensagem1, Mensagem2;
}

$obj = new Test;
$obj->msg1(); # Olá, Mundo!
echo '<br>';
$obj->msg2(); # Olá, PHP!
```

### Namespaces

Namespaces podem armazenar dentro de si classes, funções, constantes, traits, interfaces e outros namespaces aninhados, tornando tudo mais organizado e evitando conflito entre nomes de elementos.

O exemplo a seguir contém dois arquivos PHP, um que possui dois namespaces com classes de mesmo nome, e o outro que possui o código principal.

``` php
<?php
# Arquivo que contém as classes
namespace NameSpace1;

class MinhaClasse {
    function msg() {
        echo 'Olá, Mundo!';
    }
}

namespace NameSpace2;

class MinhaClasse {
    function msg() {
        echo 'Olá, PHP!';
    }
}
```

Arquivo com código principal:

``` php
<?php
# Arquivo principal
require 'classes.php'; # Importa as classes do arquivo `classe.php`
use NameSpace1\MinhaClasse as MinhaClasse1;
use NameSpace2\MinhaClasse as MinhaClasse2;

$obj = new MinhaClasse1;
$obj->msg(); # Output: Olá, Mundo!

$obj = new MinhaClasse2;
$obj->msg(); # Output: Olá, PHP!
```

A palavra-chave **`as`** (*alias*) é usada principalmente para fornecer um nome alternativo para a classe ou namespace importado, facilitando o uso no código, assim como visto no exemplo acima.

#### Namespace Global

Quando não criado uma declaração explícita de namespace, o código estará dentro do namespace global.

``` php
<?php
# Namespace Global
class MinhaClasse {
    function ola_mundo() {
        echo 'Olá, Mundo!';
    }
}
```

#### Namespace Personalizado

É o namespace criado a partir da palavra-chave `namespace`.

``` php
<?php
namespace NameSpacePersonalizado {
    class MinhaClasse {
        function ola_mundo() {
            echo 'Olá, Mundo!';
        }
    }
}
```

#### Constante '`__NAMESPACE__`'

A constante `__NAMESPACE__` possui o valor igual ao nome do namespace atual.

``` php
<?php
namespace MeuNamespace;
class MinhaClasse {
    function info() {
        return __NAMESPACE__;
    }
}

$obj = new MinhaClasse;
echo $obj->info(); # Output: MeuNamespace

```
