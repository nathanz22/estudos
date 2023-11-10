# C

## Comentários

Em C, comentários de uma linha são criados com **`//`**. Comentário de múltiplas linha são criados com **`/*`** e **`*/`**.

Exemplo:

``` c
// Isso é um comentário!

/*
Isso também é um comentário
*/
```

## Sintaxe

Exemplo:

``` c
#include <stdio.h>

int main() {
    printf("Olá, Mundo!\n"); // Imprime "Olá, Mundo!"
    return 0; // Encerra a função `main`
}
```

Em C, todas as declarações são terminadas com ponto e vírgula.

## Variáveis

Variáveis em C são armazenadas já com o tipo de valor predefinido.

* **'`int`'**: Armazena números inteiros.
* **'`float`'**: Armazena números reais (de ponto flutuante).
* **'`char`'**: Armazena caracteres únicos. Eles ficam entre aspas simples.

A sintaxe é a seguinte:

``` c
tipo nomeVariavel = valor;
```

Exemplo:

``` c
int num1 = 2;
float num2 = 5.3;
char caractere = 'b';
```

É possível também criar uma variável e atribuir o valor só depois.

``` c
#include <stdio.h>

int main() {
    int myNum;
    myNum = 5;
    printf("%d\n", myNum); // Output: 5

    return 0;
}
```

## Constantes

São declaradas com a palavra-chave **`const`**.

Sintaxe:

``` c
const tipo NOMECONSTANTE = valor;
```

Exemplo:

``` c
#include <stdio.h>

int main() {
    const int VALOR = 5;
    valor = 2; // Ocorrerá um erro

    return 0;
}
```

Constantes devem ter seus valores atribuídos assim que declaradas.

> Identificadores de constantes normalmente são escritos em letras maiúsculas.

## Output

Para saída de valores em C, é usada a função **`printf()`**.

``` c
#include <stdio.h>

int main() {
    printf("Olá, Mundo!\n");
    return 0;
}
```

No fim do texto, é quebrada a linha caso haja `\n`.

### Output de Variáveis

Para mostrar variáveis, antes é necessário dizer o formato especificador da variável.

* Para inteiros: `"%d"` ou "`%i`.
* Para floats: `"%f"`.
* Para caracteres: `"%c"`.

``` c
#include <stdio.h>

int main() {
    int num1 = 2;
    float num2 = 5.3;
    char caractere = 'b';

    printf("%d\n", num1);       // Output: 2
    printf("%f\n", num2);       // Output: 5.300000
    printf("%c\n", caractere);  // Output: b

    return 0;
}
```

Para imprimir as variáveis junto a um texto, separe-os com vírgula.

``` c
#include <stdio.h>

int main() {
    int num = 5;
    char letra = 'e';

    printf("Número %d", num); // Output: Número 5

    return 0;
}
```

Para mostrar mais de uma variável:

``` c
#include <stdio.h>

int main() {
    int num1 = 5;
    int num2 = 2;
    int soma = num1 + num2;
    printf("A soma entre %d e %d é %d", num1, num2, soma);
    // Output: A soma entre 5 e 2 é 7

    return 0;
}
```

Para mostrar a soma como no exemplo acima, poderia ser feito o seguinte:

``` c
#include <stdio.h>

int main() {
    int num1 = 5;
    int num2 = 2;
    printf("A soma entre %d e %d é %d", num1, num2, num1 + num2);
    // Output: A soma entre 5 e 2 é 7

    return 0;
}
```

Números de ponto flutuante quando imprimidos são maiores do que quando definidos na variável.

``` c
#include <stdio.h>

int main() {
    float num = 5.12;
    printf("%f\n", num); // Output: 5.120000

    return 0;
}
```

São mostrados 6 casas decimais, porém, é possível mostrar um número de casas específico com `.` e o número de casas decimais.

``` c
#include <stdio.h>

int main() {
    float num = 5.128034;
    printf("%.2f\n", num); // Output: 5.13
    printf("%.3f\n", num); // Output: 5.128
    printf("%.4f\n", num); // Output: 5.1280

    return 0;
}

```

## Conversão de Tipos

Dividir valores como 5 e 2, gera o resultado 2, pois faz a divisão inteira já que estão sendo calculados dois valores inteiros. Porém, se especificado `(float)` antes do valor atribuído à variável ou se um dos operandos forem de ponto flutuante, será feita a divisão comum.

``` c
#include <stdio.h>

int main() {
    float num = (float) 5 / 2;
    printf("%.1f", num); // Output: 2.5

    return 0;
}
```

Ou:

``` c
#include <stdio.h>

int main() {
    printf("%d\n", 5 / 2);      // Output: 2
    printf("%.1f\n", 5 / 2.0);  // Output: 2.5

    return 0;
}
```

## Booleanos

Para usar valores booleanos (true e false), é necessário importar **`stdbool.h`**.

``` c
#include <stdbool.h>
```

Se importado, é possível declarar variáveis com a palavra-chave **`bool`**, que recebe `true` ou `false` como valor.

``` c
#include <stdio.h>
#include <stdbool.h>

int main() {
    bool v = true;
    bool f = false;

    printf("%d\n", v); // Output: 1
    printf("%d\n", f); // Output: 0

    return 0;
}
```

Como visto no exemplo acima, `true` equivale a 1 e `false` equivale a 0. Além disso, como é sempre retornado 1 ou 0, deve ser usado o formatador de números inteiro: `%d`.

## Operadores

Em C, os operadores são separados em cinco grupos:

* Operadores Aritméticos
* Operadores de Atribuição
* Operadores de Comparação
* Operadores Lógicos
* Operadores Bitwise

### Operadores Aritméticos

São:

* **'`+`'**: Adição.

    ``` c
    #include <stdio.h>

    int main() {
        printf("%d", 5 + 2);
        // Output: 7

        return 0;
    }
    ```

* **'`-`'**: Subtração.

    ``` c
    #include <stdio.h>

    int main() {
        printf("%d", 5 - 2);
        // Output: 3

        return 0;
    }
    ```

* **'`*`'**: Multiplicação.

    ``` c
    #include <stdio.h>

    int main() {
        printf("%d", 5 * 2);
        // Output: 10

        return 0;
    }
    ```

* **'`/`'**: Divisão.

    ``` c
    #include <stdio.h>

    int main() {
        printf("%d", 20 / 2);
        // Output: 10

        return 0;
    }
    ```

* **'`%`'**: Módulo (resto da divisão).

    ``` c
    #include <stdio.h>

    int main() {
        printf("%d", 5 % 2);
        // Output: 1

        return 0;
    }
    ```

* **'`++`'**: Incremento.

    ``` c
    #include <stdio.h>

    int main() {
        int num = 5;
        printf("%d", ++num);
        // Output: 6

        return 0;
    }
    ```

* **'`--`'**: Decremento.

    ``` c
    #include <stdio.h>

    int main() {
        int num = 5;
        printf("%d", --num);
        // Output: 4

        return 0;
    }
    ```

### Operadores de Atribuição

* **'`=`'**: Adiciona um valor à variável.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;

        return 0;
    }
    ```

* **'`+=`'**: Soma um valor à variável.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x += 5;
        printf("%d", x); // Output: 15

        return 0;
    }
    ```

* **'`-=`'**: Subtrai um valor da variável.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x -= 5;
        printf("%d", x); // Output: 5

        return 0;
    }
    ```

* **'`*=`'**: Multiplica o valor da variável por um valor.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x *= 2;
        printf("%d", x); // Output: 20

        return 0;
    }
    ```

* **'`/=`'**: Divide o valor da variável por um valor.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x /= 2;
        printf("%d", x); // Output: 5

        return 0;
    }
    ```

* **'`%=`'**: Variável se torna o módulo de seu valor pelo valor especificado.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x %= 3;
        printf("%d", x); // Output: 1

        return 0;
    }
    ```

* **'`&=`'**: Atribui à variável o resultado da comparação bitwise AND.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x &= 9;
        printf("%d", x); // Output: 8

        return 0;
    }
    ```

* **'`|=`'**: Atribui à variável o resuldado da comparação bitwise OR.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x |= 9;
        printf("%d", x); // Output: 11

        return 0;
    }
    ```

* **'`^=`'**: Atribui à variável o resuldado da comparação bitwise XOR.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x ^= 9;
        printf("%d", x); // Output: 3

        return 0;
    }
    ```

* **'`>>=`'**: Atribui à variável o resuldado do deslocamento à direita.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x >>= 2;
        printf("%d", x); // Output: 2

        return 0;
    }
    ```

* **'`<<=`'**: Atribui à variável o resuldado do deslocamento à esquerda.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 10;
        x <<= 2;
        printf("%d", x); // Output: 40

        return 0;
    }
    ```

### Operadores de Comparação

* **'`==`'**: Igual.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x == y);
        // Output: 0

        return 0;
    }
    ```

* **'`!=`'**: Diferente.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x != y);
        // Output: 1

        return 0;
    }
    ```

* **'`>`'**: Maior.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x > y);
        // Output: 1

        return 0;
    }
    ```

* **'`<`'**: Menor.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x < y);
        // Output: 0

        return 0;
    }
    ```

* **'`>=`'**: Maior ou igual.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x >= y);
        // Output: 1

        return 0;
    }
    ```

* **'`<=`'**: Menor ou igual.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 5;
        int y = 2;
        printf("%d", x <= y);
        // Output: 0

        return 0;
    }
    ```

### Operadores Lógicos

* **'`&&`'**: And. Verdadeiro se ambos os valores forem verdadeiro.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 1;
        int y = 1;
        printf("%d", x && y);
        // Output: 1

        return 0;
    }
    ```

* **'`||`'**: Or. Verdadeiro se pelo menos um dos valores for verdadeiro.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 0;
        int y = 1;
        printf("%d", x || y);
        // Output: 1

        return 0;
    }
    ```

* **'`!`'**: Not. Interve os valores, se verdadeiro, se torna falso, se falso, se torna verdadeiro.

    ``` c
    #include <stdio.h>

    int main() {
        int x = 0;
        int y = 0;
        printf("%d", !x && !y);
        // Output: 1

        return 0;
    }
    ```

### Operador `sizeof`

Retorna o tamanho que uma variável ou tipo de dado ocupa na memória (em bytes).

``` c
#include <stdio.h>

int main() {
    int myInt;
    float myFloat;
    double myDouble;
    char myChar;

    printf("%lu\n", sizeof(myInt));     // Output: 4
    printf("%lu\n", sizeof(myFloat));   // Output: 4
    printf("%lu\n", sizeof(myDouble));  // Output: 8
    printf("%lu\n", sizeof(myChar));    // Output: 1

    return 0;
}
```

> É utilizado `%lu` ao invés de `%d` para mostrar os valores. O motivo é que os valores são do tipo `size_t`, que requer `%lu` para ser mostrado.

## Estruturas Condicionais

São `if`, `else` e `else if`.

A sintaxe é a seguinte:

``` c
if (condicao1) {
    // Código a ser executado se `condicao1` for verdadeira
} else if (condicao2) {
    // Código a ser executado se `condicao2` for verdadeira
} else {
    // Se `if` ou `else if` não for verdadeiro, é executado este bloco
}
```

Será executado o primeiro bloco cuja a condição seja verdadeira, logo, será executado apenas um bloco.

Exemplo:

``` c
#include <stdio.h>

int main() {
    int x = 5;
    if (x > 5) {
        printf("%d é MAIOR que 5", x);
    } else if (x < 5) {
        printf("%d é MENOR que 5", x);
    } else {
        printf("Valor é IGUAL a 5");
    }
    // Output: Valor é IGUAL a 5

    return 0;
}
```

Os blocos `else if` e `else` são opcionais, porém não podem existir sem a declaração `if`.

### Operadores Ternários

São **`?`** e **`:`**, e são usados para expressões condicionais.

Sintaxe:

``` c
condicao ? se_verdadeiro : se_falso;
```

Exemplo:

``` c
#include <stdio.h>

int main() {
    int x = 5;
    x == 5 ? printf("SIM!") : printf("NÃO!");
    // Output: SIM!

    return 0;
}
```

No exemplo acima, é impresso "SIM!" porque a variável `x` é igual a 5.

### Estrutura `switch`

Em casos de múltiplos valores à uma única variável ou expressão, a estrutura **`switch`** é muito útil.

Sintaxe:

``` c
switch (expressao) {
    case valor1:
        // Executa se `expressao` for igual a `valor1`
        break;
    case valor2:
        // Executa se `expressao` for igual a `valor2`
        break;
    case valor3:
        // Executa se `expressao` for igual a `valor3`
        break;
    default:
        // Executa se `expressao` não corresponder a nenhum `case`
}
```

Exemplo:

``` c
#include <stdio.h>

int main() {
    int x = 5;
    switch (x) {
        case 1:
            printf("Opção 1");
            break;
        case 2:
            printf("Opção 2");
            break;
        case 3:
            printf("Opção 3");
            break;
        default:
            printf("%d não é uma opção válida!", x);
    }
    // Output: 5 não é uma opção válida!

    return 0;
}
```

A palavra-chave **`break`** é usada para sair da estrutura `switch` e, se omitda, será executado o próximo bloco `case`.

Exemplo:

``` c
#include <stdio.h>

int main() {
    int x = 1;
    switch (x) {
        case 1:
            printf("Opção 1\n");
        case 2:
            printf("Opção 2\n");
        case 3:
            printf("Opção 3\n");
        default:
            printf("%d não é uma opção válida!\n", x);
    }
    /* Output:
    Opção 1
    Opção 2
    Opção 3
    1 não é uma opção válida!
    */

    return 0;
}
```

## Estruturas de Repetição

### Loop `for`

Executa um bloco um número específico de vezes.

Sintaxe:

``` c
for (inicializacao; condicao; atualizacao) {
    // Bloco a ser repetido
}
```

* **'`inicializacao`'**: É executado uma vez no início do loop, geralmente para inicializar a variável de controle do loop.

* **'`condicao`'**: É a condição que é verificada antes de cada iteração do loop. O loop executa apenas se a condição for verdadeira, se não, o loop é encerrado.

* **'`atualizacao`'**: É executado ao início de toda iteração, geralmente para atualizar a variável de controle do loop.

Exemplo:

``` c
#include <stdio.h>

int main() {
    for (int x = 0; x <= 5; x++) {
        printf("%d\n", x);
    }
    /* Output:
    0
    1
    2
    3
    4
    5
    */

    return 0;
}
```

Exemplo que imprime todos os números pares de 0 a 10:

``` c
#include <stdio.h>

int main() {
    for (int x = 0; x <= 10; x += 2) {
        printf("%d\n", x);
    }
    /* Output:
    0
    2
    4
    6
    8
    10
    */

    return 0;
}
```

### Loop `while`

Executa um bloco de código até que sua condição se torne falsa.

Sintaxe:

``` c
while (condicao) {
        // Bloco a ser repetido
    }
```

Exemplo:

``` c
#include <stdio.h>

int main() {
    int x = 0;
    while (x < 5) {
        x++;
        printf("%d\n", x);
    }
    /* Output
    1
    2
    3
    4
    5
    */

    return 0;
}
```

### Loop `do...while`

É uma variante do loop `while` e funciona da mesma maneira, porém, o bloco é executado pelo menos uma vez.

``` c
do {
    // Bloco a ser repetido (executa pelo menos uma vez)
} while (condicao);
```

Exemplo:

``` c
#include <stdio.h>
#include <stdbool.h>

int main() {
    int x = false;
    do {
        printf("Olá, Mundo!");
    } while (x);
    // Output: Olá, Mundo!

    return 0;
}
```

Basicamente, é executado o bloco de código uma vez, e ao fim da execução é levado em conta a condição.

### Controle de Fluxo

As declarações `break` e `continue` são usadas para controlar o fluxo em loops.

* **'`break`'**: Encerra o loop.
* **'`continue`'**: Pula para a próxima iteração.

Exemplo com `break`

``` c
#include <stdio.h>
#include <stdbool.h>

int main() {
    int x = 0;
    while (true) {
        printf("%d\n", x);
        x++;
        if (x > 5) { break; }
    }
    /* Output:
    0
    1
    2
    3
    4
    5
    */

    return 0;
}
```

No exemplo acima, `while` é um loop infinito, podendo ser encerrado apenas com a declaração `break`.

Exemplo com `continue`

``` c
#include <stdio.h>
#include <stdbool.h>

int main() {
    for (int x = 0; x <= 10; x++) {
        if (x % 2 != 0) { continue; }
        printf("%d\n", x);
    }
    /* Output:
    0
    2
    4
    6
    8
    10
    */

    return 0;
}
```

No exemplo acima, a iteração será pulada toda vez que a variável de controle for ímpar.
