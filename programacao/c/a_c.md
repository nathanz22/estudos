# C

## Comentários

Em C, comentários de uma linha são criados com **`//`**. Comentário de múltiplas linha são criados com **`/*`** e **`*/`**.

**Exemplo:**

``` c
// Isso é um comentário!

/*
Isso também é um comentário
*/
```

## Sintaxe

**Exemplo:**

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

**Exemplo:**

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

**Exemplo:**

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

### Caracteres de Escape

São sequências especiais de caracteres usadas para representar caracteres especiais não imprimíveis ou realizar ações específicas na saída.

Os principais caracteres de escape são:

* **'`\n`'**: Quebra de linha.

    ``` c
    #include <stdio.h>

    int main() {
        printf("Hello,\nWorld!");
        /* Output:
        Hello,
        World!
        */

        return 0;
    }
    ```

* **'`\t`'**: Tabulação horizontal.

    ``` c
    #include <stdio.h>

    int main() {
        printf("Hello,\tWorld!");
        // Output: Hello,  World!

        return 0;
    }
    ```

* **'`\'`'**: Aspas simples.

    ``` c
    #include <stdio.h>

    int main() {
        printf("\'Hello, World!\'");
        // Output: 'Hello, World!'

        return 0;
    }
    ```

* **'`\"`'**: Aspas duplas.

    ``` c
    #include <stdio.h>

    int main() {
        printf("\"Hello, World!\"");
        // Output: "Hello, World!"

        return 0;
    }
    ```

* **'`\\`'**: Barra invertida.

    ``` c
    #include <stdio.h>

    int main() {
        printf("\\Hello, World!\\");
        // Output: \Hello, World!\

        return 0;
    }
    ```

Além desses caracteres de escape, há também outros menos comuns:

* **'`\a`'**: Alarme (geralmente resulta em um sinal sonoro).
* **'`\b`'**: Retrocesso (move o cursor de volta um caractere).
* **'`\r`'**: Retorno de carro (move o cursor para o início da linha).
* **'`\f`'**: Alimentação de formulário (avança para a próxima página em algumas saídas de texto).
* **'`\v`'**: Tabulação vertical (avanço vertical do cursor).

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

Imprimindo uma variável junto a um texto:

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

## Tipos Primitivos

Em C, os principais tipos primitivos são:

* Inteiros (`int`)
* Ponto Flutuante (`float`)
* Caracteres (`char`)
* Sem valor (`void`)

### Inteiros

São representados pela palavra **`int`**. Existem vários tipos de dados inteiros. São eles:

#### `int`

É o tipo de dado inteiro padrão. Em muitos sistemas, o tipo **`int`** ocupa 4 bytes na memória (32 bits).

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    // Declaração de inteiros
    int myInt1 = 2;
    int myInt2 = -3;
    int myInt3 = 0;

    // Imprime os valores
    printf("Inteiro 1: %d\n", myInt1); // Output: Inteiro 1: 2
    printf("Inteiro 2: %d\n", myInt2); // Output: Inteiro 2: -3
    printf("Inteiro 3: %d\n", myInt3); // Output: Inteiro 3: 0

    return 0;
}
```

> Para impressão, é usado o formato **`%d`**.

#### `short int`

Representa números inteiros curtos. Eles ocupam menos espaço na memória e são declarados a partir da palavra-chave **`short`**.

Os valores máximo e mínimo que um inteiro curto pode ter é:

**Valor mínimo: -32768**
**Valor máximo: 32767**

``` c
#include <stdio.h>

int main() {
    // Declaração de inteiros curtos
    short int num1 = 21873;
    short int num2 = -1093;
    short int num3 = 5;

    // Imprime os valores
    printf("Inteiro curto 1: %d\n", num1); // Output: Inteiro curto 1: 21873
    printf("Inteiro curto 2: %d\n", num2); // Output: Inteiro curto 2: -1093
    printf("Inteiro curto 3: %d\n", num3); // Output: Inteiro curto 3: 5

    return 0;
}
```

> Para impressão, é usado o formato **`%d`**.

#### `long int`

Representa números inteiros longos. Usar **`long`** como qualificador aumenta o intervalo de valores que uma variável pode armazenar em comparação com um `int` padrão.

``` c
#include <stdio.h>

int main() {
    // Declaração de um inteiro longo
    long int num = 1234567890;

    // Imprime o valor
    printf("Inteiro longo: %ld\n", num); // Output: Inteiro longo: 1234567890

    return 0;
}
```

Geralmente, um `long int` ocupa mais espaço na memória do que `int`, normalmente 4 bytes a mais.

Usar o sufixo `L` ou `l` indica explicitamente que se trata de um `long int`.

``` c
long int num = 1234567890l;
```

> Para impressão, é usado o formato **`%ld`**.

#### `long long int`

Representa um inteiro de tamanho maior que o `int` padrão. O tamanho exato de `long long int` pode variar entre os compiladores, mas é garantido ser pelo menos tão grande quanto um `long int`.

``` c
#include <stdio.h>

int main() {
    // Declaração de um `long long int`
    long long int num = 987654321012345678;

    // Imprime o valor
    printf("Inteiro longo: %lld\n", num); // Output: Inteiro longo longo: 987654321012345678

    return 0;
}
```

> Para impressão, é usado o formato **`lld`**.

Usar o sufixo `LL` ou `ll` ao fim de um número torna explícito de que se trata de um `long long int` literal.

``` c
long long int num = 987654321012345678ll;
```

#### `signed int`

Por padrão, os inteiros em C são `signed`, o que significa que eles podem armazenar tanto valores positivos quanto negativos.

``` c
signed int num1 = 5;
signed int num2 = -5;
signed int num3 = 0;
```

O código acima é o mesmo que:

``` c
int num1 = 5;
int num2 = -5;
int num3 = 0;
```

O termo "signed" indica que o tipo de dado inclui um bit de sinal, que é usado para representar o sinal do número (positivo ou negativo).

#### `unsigned int`

Representam números inteiros sem sinal, ou seja, números que não podem ser negativos.

``` c
#include <stdio.h>

int main() {
    // Declaração de inteiros curtos
    unsigned int num = 21;

    // Imprime o valor
    printf("Inteiro sem sinal: %u\n", num); // Output: Inteiro sem sinal: 21

    return 0;
}
```

Valores inteiros sem sinal podem armazenar um número maior que inteiros com sinal, pois o espaço dos valores negativos são convertidos em mais espaços para mais positivos.

A quantidade de memória ocupada por um `unsigned int` varia, mas geralmente é de 4 bytes em sistemas 32 bits e 4 ou 8 bytes em sistemas de 64 bits.

> Para impressão de inteiros sem sinal, é usado o formato **`%u`**.

#### Largura de Campo e Precisão

Pode-se definir a largura de campo e precisão da seguinte maneira:

``` c
#include <stdio.h>

int main() {
    int num = 25;
    printf("Valor: %5d\n", num); // Output: Valor:    25

    return 0;
}
```

#### Limites dos Inteiros

Para saber o limite dos inteiros, você pode usar constantes da biblioteca padrão **`limits.h`**.

``` c
#include <stdio.h>
#include <limits.h>

int main() {
    printf("%d\n", INT_MAX);
    printf("%ld\n", LONG_MAX);
    printf("%lld\n", LLONG_MAX);

    return 0;
}
```

### Números de Ponto Flutuante

Em C, números de ponto flutuante podem são representados pelos tipos **`float`** e **`double`**.

**Exemplo com `float`:**

``` c
#include <stdio.h>

int main() {
    // Declara variáveis de ponto flutuante
    float numReal1 = 5.2;
    float numReal2 = -231.5;
    float numReal3 = 99.6;

    // Imprime as variáveis
    printf("%f\n", numReal1); // Output: 5.200000
    printf("%f\n", numReal2); // Output: -231.500000
    printf("%f\n", numReal3); // Output: 99.599998

    return 0;
}
```

**Exemplo com `double`:**

``` c
#include <stdio.h>

int main() {
    // Declara variáveis de ponto flutuante
    double numReal1 = 5.2;
    double numReal2 = -231.5;
    double numReal3 = 99.6;

    // Imprime as variáveis
    printf("%f\n", numReal1); // Output: 5.200000
    printf("%f\n", numReal2); // Output: -231.500000
    printf("%f\n", numReal3); // Output: 99.599998

    return 0;
}
```

Como pode ver nos exemplos acima, ao imprimir números reais são mostrados 6 casas decimais. Para ambos os tipos (`float` e `double`) é possível formatar a quantidade de casas decimais ao imprimir o valor.

``` c
#include <stdio.h>

int main() {
    float num = 10.5;

    printf("%.1f\n", num); // Output: 10.5
    printf("%.2f\n", num); // Output: 10.50
    printf("%.3f\n", num); // Output: 10.500

    return 0;
}
```

> Para ambos os tipos, é usado o formato **`%f`** para impressão.

#### `float` vs. `double`

A diferença entre `float` e `double` está na precisão, onde `float` possui uma precisão finita, o que significa que em algumas situações pode haver perda de precisão ao lidar com números muito pequenos ou muito grandes, ou ao realizar operações aritméticas complexas.

O tipo `double` é mais preciso, e geralmente ocupa 8 bytes na memória (64 bits), comparado com os 4 bytes (32 bits) do tipo `float`. Essa maior quantidade de bytes permite que o tipo `double` represente uma gama maior de valores e forneça maior precisão em comparação com o tipo `float`.

#### `long double`

É basicamente o tipo `double`, porém com ainda mais precisão.

``` c
long double pi = 3.14159265358979323846;
```

Geralmente um `long double` ocupa mais bytes na memória do que um `double` (por exemplo, 10 ou 12 bytes), permitindo representar valores com uma precisão ainda maior.

O tipo `long double` é dispensável, a menos que a situação requeira precisão extra crítica, como em cálculos científicos ou matemáticos muito sensível à precisão.

##### Impressão de `long double`

Para imprimir um `long double`, é usado o formatador **`%Lf`**.

``` c
#include <stdio.h>

int main() {
    // Declara um `long double`
    long double pi = 3.14159265358979323846;

    // Imprime o `long double`
    printf("%Lf\n", pi);    // Output: 3.141593
    printf("%.1Lf\n", pi);  // Output: 3.1
    printf("%.2Lf\n", pi);  // Output: 3.14

    return 0;
}
```

Como pode ver no exemplo acima, ao imprimir os valores podem ser formatados para mostrar uma quantidade específica de casas decimais.

#### Formatação de Floats

**Pode-se formatar a quantidade de casas decimais:**

``` c
#include <stdio.h>

int main() {
    float myFloat = 22.513;

    printf("Valor: %.1f\n", myFloat); // Output: 22.5

    return 0;
}
```

**Pode-se definir a largura de campo:**

``` c
#include <stdio.h>

int main() {
    float myFloat = 22.513;

    printf("Valor: %10.2f\n", myFloat); // Output: Valor:      22.51

    return 0;
}
```

**Pode-se formatar com notação científica:**

``` c
#include <stdio.h>

int main() {
    float myFloat = 22.513;

    printf("Valor: %e\n", myFloat); // Output: Valor: 2.251300e+001

    return 0;
}
```

#### Comparação

Comparar diretamente valores de ponto flutuante pode levar a resultados inesperados.

``` c
#include <stdio.h>

int main() {
    float x = 0.1;
    float y = 0.2;
    float z = x + y;

    if (z == 0.3) {
        printf("Igual!\n");
    } else {
        printf("Diferente\n");
    }

    return 0;
}
```

Neste exemplo, devido a erros de arredondamento, `z` pode não ser exatamente igual a `0.3`.

Para resolver isso, é comum usar uma tolerância (margem de erro) ao realizar comparações entre números de ponto flutuante.

``` c
#include <stdio.h>
#include <math.h>

int main() {
    float x = 0.1;
    float y = 0.2;
    float z = x + y;
    float tolerancia = 0.000001;

    if (fabs(z - 0.3) < tolerancia) {
        printf("Aproximadamente igual!\n");
    } else {
        printf("Diferente\n");
    }

    return 0;
}
```

Aqui, `fabs()` é a função da biblioteca padrão **`math.h`** que retorna o valor absoluto.

#### `NaN` e `Inf`

Floats podem representar valores especiais, como `NaN` (Not a Number) e `Inf` (Infinity), e a comparação com esses valores também deve ser tratada com cuidado.

Para lidar com isso, pode-se usar as funções **`isnan()`** e **`isinf()`**, ambas da biblioteca padrão **`math.h`**.

### Caracteres

O tipo **`char`** representa um caractere único.

``` c
char x = 'A';
```

> Ao denotar um único caractere, devem ser usadas aspas simples.

Cada variável do tipo `char` ocupa 1 byte na memória, e pode armazenar um único valor alfanumérico. Os caracteres podem ser letras, números, pontuações ou símbolos especiais.

**Para imprimir caracteres, é usado o formato `%c`:**

``` c
#include <stdio.h>

int main() {
    char x = 'A';
    printf("%c\n", x); // Output: A

    return 0;
}
```

Além de armazenar caracteres, as variáveis do tipo `char` podem ser usadas para representar números inteiros pequenos. Isso ocorre porque em C, os caracteres são representados internamente como valores inteiros correspondentes aos códigos ASCII dos caracteres.

**Exemplo:**

``` c
char x = 65; // Representa 'A'
char y = 66; // Representa 'B'
```

**Então, é possível imprimir os valores correspondentes aos caracteres utilizando o formato `%d`:**

``` c
#include <stdio.h>

int main() {
    char x = 'A';
    printf("%d\n", x); // Output: 65

    return 0;
}
```

### Tipo `void`

Representa a ausência de tipo ou valor, frequentemente usado como um tipo de retorno de funções, como um tipo de ponteiro e como um argumento de função para indicar que a função não recebe argumentos.

### Conversão de Tipos

Converter um tipo de dado para um outro tipo é chamado de **"cast"**. Pode ser feito usando parênteses com um tipo de dado, seguido pelo dado que será convertido.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    float myFloat = 2.23;
    printf("Número: %d", (int)myFloat);
    // Output: Número 2

    return 0;
}
```

Dividir o valor 5 por 2 gera o resultado 2, pois faz a divisão inteira já que estão sendo calculados dois valores inteiros. Porém, se feito o cast para `(float)` ou se um dos operandos forem de ponto flutuante, será feita a divisão comum.

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

#### Tipo `size_t`

O tipo **`size_t`** é usado para representar o tamanho de objetos em bytes.

É um tipo inteiro sem sinal, o que significa que só aceita valores não negativos.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    // Variável que armazena o número de bytes de um inteiro
    size_t tamanhoInt = sizeof(int);

    // Imprime o tamanho em bytes de um inteiro
    printf("%lu", tamanhoInt); // Output: 4

    return 0;
}
```

## Fluxos Padrão

Existem três fluxos padrão:

* **`stdin`**: Entrada padrão.
* **'`stdout`'**: Saída padrão.
* **'`stderr`'**: Saída de erro padrão.

### `stdin`

É o fluxo de entrada padrão, normalmente está associado ao teclado. Funções como `scanf()` e `getchar()` são usadas para ler dados de `stdin`.

``` c
int main() {
    int num;
    scanf("%d", &num);

    return 0;
}
```

### `stdout`

É o fluxo de saída padrão associado ao console ou terminal. Funções como `printf()` e `putchar()` são usadas para imprimir dados em `stdout`.

``` c
#include <stdio.h>

int main() {
    int num = 5;
    printf("Número: %d\n", num);
    // Output: Número: 5

    return 0;
}
```

### `stderr`

É o fluxo de saída de erro padrão associado ao console ou terminal. Frequentemente usado pela função `fprintf()`.

``` c
#include <stdio.h>

int main() {
    fprintf(stderr, "Erro: Teste de erro.\n");
    // Output: Erro: Teste de erro.

    return 0;
}
```

### Redirecionamento de Fluxos

É possível redirecionar os fluxos padrão para apontar para arquivos em vez do console.

``` c
#include <stdio.h>

int main() {
    freopen("text.txt", "a", stdout);
    printf("Hello, World!\n");

    return 0;
}
```

No exemplo acima, o arquivo `text.txt` será:

``` txt
Hello, World!
```

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

**Exemplo:**

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

**Sintaxe:**

``` c
condicao ? se_verdadeiro : se_falso;
```

**Exemplo:**

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

**Sintaxe:**

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

**Exemplo:**

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

**Exemplo:**

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

## Entrada do Usuário

A função **`scanf()`** permite uma entrada do usuário com um tipo de valor específico.

``` c
#include <stdio.h>

int main() {
    int userValue;
    printf("Digite um valor: ");
    scanf("%d", &userValue);

    printf("O valor digitado foi %d", userValue);

    return 0;
}
```

> No exemplo acima, `&userValue` armazena o endereço de memória da variável.

### Validação de Valores

Para validar e prosseguir somente quando o usuário digitar um valor válido, por exemplo, apenas quando o usuário digitar um número inteiro, podemos usar uma condição.

``` c
#include <stdio.h>

int main() {
    int userInt;

    printf("Digite um número inteiro: ");
    if (scanf("%d", &userInt)) {
        printf("Valor digitado foi %d.", userInt);
    } else {
        printf("Valor inválido.");
    }

    return 0;
}
```

Assim, podemos usar um loop para que o programa continue apenas quando o usuário passar um valor válido:

``` c
#include <stdio.h>
#include <stdbool.h>

// Função que limpa o buffer do teclado
void limparBuffer() {
    int c;
    while (c = getchar() != '\n' && c != EOF);
}

int main() {
    int userInt;
    while (true) {
        printf("Digite um número inteiro: "); // Pede um número inteiro ao usuário
        if (scanf("%d", &userInt)) { // `scanf()` retorna verdadeiro se o valor for válido
            // Caso o valor seja válido
            printf("Valor digitado foi %d.", userInt);
            limparBuffer(); // Limpa o buffer do teclado
            break;
        } else {
            // Caso valor seja inválido
            printf("Valor inválido.\n");
        }
        limparBuffer(); // Limpa o buffer do teclado
    }

    return 0;
}
```

### Múltiplas Entradas

É possível obter múltiplos valores com uma única declaração da função `scanf()`.

``` c
#include <stdio.h>

int main() {
    int userInt;
    char userStr[10];

    printf("Digite um inteiro e uma string: ");
    scanf("%d %s", &userInt, userStr);

    printf("O valor digitado foi %d\n", userInt);
    printf("%s\n", userStr);

    return 0;
}
```

> No caso de strings, não é necessário usar `&` antes do identificador da variável.

### Função `fgets()`

Uma string retornada de `scanf()` é terminada no primeiro espaço em branco, ou seja, não é possível receber mais de uma palavra utilizando esta função.

``` c
#include <stdio.h>

int main() {
    char userStr[30];

    printf("Digite uma string: ");
    scanf("%s", userStr);

    printf("String: %s", userStr);

    /*
    Input:      Eu amo C
    Output:     String: Eu
    */

    return 0;
}
```

Para obter strings de mais de uma palavra, pode ser utilizada a função **`fgets()`**, que lê uma linha de texto.

Essa função recebe três argumentos:

1. Variável que vai receber o input.
1. Tamanho da variável que vai receber o input (`sizeof(var_name)`).
1. Palavra `stdin`.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    char userStr[30];

    printf("Digite uma string: ");
    fgets(userStr, sizeof(userStr), stdin);

    printf("String: %s", userStr);

    /*
    Input:      Eu amo C
    Output:     String: Eu amo C
    */

    return 0;
}
```

### Segurança de Entrada

Ao declarar uma variável de string, é obrigatório definir a quantidade de caracteres que a variável vai ocupar, porém, ao receber uma string do usuário com a função `scanf()` é importante também especificar o limite de caracteres.

``` c
#include <stdio.h>

int main() {
    char userStr[10];

    printf("Digite algo: ");
    scanf("%9s", userStr);

    printf("%s", userStr);
    /*
    Input:      HelloWorld!
    Output:     HelloWorl
    */

    return 0;
}
```

> É uma boa prática indicar o número de caracteres da variável menos 1 para garantir que haja o caractere nulo (`\0`) ao fim da string.

A importância de especificar o tamanho máximo de caracteres que a string pode conter se deve a prevenção de estouro de buffer.

Para a função `fgets()`, também é necessário especificar o tamanho máximo do buffer para garantir que não haja estouro. O tamanho do buffer deve ser o segundo argumento passado para `fgets()` (`sizeof(var_str)`).

#### Limpeza do Buffer

A limpeza de buffer ajuda a evitar caracteres indesejados, especialmente após a leitura de dados usando funções como `scanf()`.

Ao ler uma entrada do usuário usando `scanf()`, é possível que caracteres indesejados, como quebra de linhas e espaços em branco, permaneçam no buffer de entrada. Para lidar com isso, é comum usar um loop para consumir esses caracteres até encontrar um caractere de nova linha (`\n`) ou final do arquivo (`EOF`).

``` c
// Função que limpa o buffer do teclado
void limparBuffer() {
    int c;
    while (c = getchar() != '\n' && c != EOF);
}
```

#### Entrada de Números com `fgets()`

A função `fgets()` recebe uma string do usuário, porém, é muito útil para verificar se uma entrada é ou não um número inteiro antes de continuar a execução do programa. Para isso, é necessário converter o valor de entrada para um número inteiro com a função **`sscanf()`**, que recebe os seguintes argumentos:

1. String de entrada.
1. Formato de entrada.
1. String de armazenamento.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    char userInput[20];
    int userInt;

    // Input de um número inteiro
    printf("Digite um inteiro: ");
    fgets(userInput, sizeof(userInt), stdin);

    // Converte a string para um inteiro
    if (sscanf(userInput, "%d", &userInt) == 1) {
        printf("Valor digitado: %d\n", userInt);
    } else {
        printf("Valor digitado é inválido!");
    }

    return 0;
}
```

No exemplo acima, é mostrada uma mensagem com o valor digitado apenas se o mesmo for um número inteiro.

## Estruturas de Repetição

### Loop `for`

Executa um bloco um número específico de vezes.

**Sintaxe:**

``` c
for (inicializacao; condicao; atualizacao) {
    // Bloco a ser repetido
}
```

* **'`inicializacao`'**: É executado uma vez no início do loop, geralmente para inicializar a variável de controle do loop.

* **'`condicao`'**: É a condição que é verificada antes de cada iteração do loop. O loop executa apenas se a condição for verdadeira, se não, o loop é encerrado.

* **'`atualizacao`'**: É executado ao início de toda iteração, geralmente para atualizar a variável de controle do loop.

**Exemplo:**

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

**Sintaxe:**

``` c
while (condicao) {
        // Bloco a ser repetido
    }
```

**Exemplo:**

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

**Exemplo:**

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

## Arrays

Arrays são usados para armazenar vários valores em uma única variável.

Arrays são declarados em variáveis `int` com `[]` ao fim do identificador, os valores são escritos entre chaves e separados por vírgula.

**Sintaxe:**

``` c
int myArray[] = {valor1, valor2, valor3};
```

**Exemplo:**

``` c
int myArray[] = {2, 4, 6, 8, 10};
```

Outra maneira de criar arrays, é especificando o número de elementos entre os colchetes e só depois atribuir os valores.

``` c
#include <stdio.h>

int main() {
    int myArray[5];
    myArray[0] = 1;
    myArray[1] = 2;
    myArray[2] = 3;
    myArray[3] = 4;
    myArray[4] = 5;

    printf("{");
    for (int x = 0; x <= 4; x++) {
        printf("%d", myArray[x]);
        if (x == 4) { break; }
        printf(", ");
    }
    printf("}\n");
    // Output: {1, 2, 3, 4, 5}

    return 0;
}

```

Dessa maneira não é possível alterar o tamanho do array posteriormente.

### Acesso aos Elementos do Array

Os elementos de um array podem ser acessador por meio de  notação de colchete.

``` c
#include <stdio.h>

int main() {
    int myArray[] = {1, 2, 3, 4, 5};

    for (int x = 0; x <= 4; x++) {
        printf("%d\n", myArray[x]);
    }
    /* Output:
    1
    2
    3
    4
    5
    */

    return 0;
}
```

### Alterar Valores

Para alterar um valor de um elemento do array, deve ser especificado o array com o índice do elemento a ser alterado.

``` c
int myArray[] = {1, 2, 3, 4, 5};
myArray[2] = 10;
// `myArray` será: {1, 2, 10, 4, 5}
```

### Array Multidimensional

Um array multidimensional é um array composto de outros arrays.

A sintaxe é a seguinte:

``` c
int myArray[linhas][colunas] = { {array1}, {array2} };
```

Exemplo de array 3x3:

``` c
int myArray[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };
```

Para acessar os elementos, é necessário especificar o índice do array, e o índice do elemento desse array.

``` c
#include <stdio.h>

int main() {
    int myArray[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };
    printf("%d\n", myArray[0][0]); // Output: 1
    printf("%d\n", myArray[0][1]); // Output: 2
    printf("%d\n", myArray[0][2]); // Output: 3
    printf("%d\n", myArray[1][0]); // Output: 4
    printf("%d\n", myArray[1][1]); // Output: 5
    printf("%d\n", myArray[1][2]); // Output: 6
    printf("%d\n", myArray[2][0]); // Output: 7
    printf("%d\n", myArray[2][1]); // Output: 8
    printf("%d\n", myArray[2][2]); // Output: 9
}
```

Uma outra forma de mostrar os valores:

``` c
#include <stdio.h>

int main() {
    int myArray[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };

    int x, y;
    for (x = 0; x < 3; x++) {
        for (y = 0; y < 3; y++) {
            printf("%d\n", myArray[x][y]);
        }
    }
    /* Output:
    1
    2
    3
    4
    5
    6
    7
    8
    9
    */

    return 0;
}
```

## Strings

Para serem armazenadas em variáveis, essas variáveis devem ser `char`, e ao fim do identificador deve conter colchetes.

**Exemplo:**

``` c
char myString[] = "Olá, Mundo!";
```

Para mostrar variáveis que armazenam uma string, deve ser usado o formato **`%s`**.

``` c
#include <stdio.h>

int main() {
    char myStr[] = "Olá, Mundo!";
    printf("%s", myStr);
    // Output: Olá, Mundo!

    return 0;
}
```

### Strings são Arrays

Em C, não existe o tipo de dado String. Strings em C são arrays, e por isso a maneira de declará-las como variáveis é a mesma (só que sem chaves e vários valores).

Como strings são arrays, é possível usar notação de colchetes para obter seus caracteres por índice.

``` c
#include <stdio.h>

int main() {
    char myStr[] = "Minha String";
    printf("%c", myStr[6]);
    // Output: S

    return 0;
}
```

> Use `%c` para mostrar apenas um caractere.

Uma outra meneira de criar uma string é definir cada caractere como um elemento de um array.

``` c
#include <stdio.h>

int main() {
    char myStr[] = {'M', 'i', 'n', 'h', 'a', ' ', 'S', 't', 'r', 'i', 'n', 'g', '\0'};
    printf("%s", myStr);
    // Output: Minha String

    return 0;
}
```

> Para mostrar uma string é usado o formato **`%s`**.

Ao fim, deve haver o elemento `\0` para determinar o fim da string.

### Largura da String

Com o operador `sizeof` é possível obter a largura de uma string.

``` c
#include <stdio.h>

int main() {
    char myStr[] = "Oi";
    printf("%d", sizeof(myStr));
    // Output: 3

    return 0;
}
```

No exemplo acima, a string tem 3 de largura porque é contado `\0` que indica o fim da string.

Então o correto seria:

``` c
#include <stdio.h>

int main() {
    char myStr[] = "Oi";
    printf("%d", sizeof(myStr) - 1);
    // Output: 2

    return 0;
}
```

Existe uma maneira ainda mais fácil, que é utilizando a função **`strlen()`**, mas primeiro, é necessário importar **`<string.h>`**.

``` c
#include <stdio.h>
#include <string.h>

int main() {
    char myStr[] = "Oi";
    printf("%d", strlen(myStr));
    // Output: 2

    return 0;
}
```

### Substituição de Caracteres

Para substituir um caractere específico em uma string, você deve especificar a string, o índice entre colchetes e atribuir um novo caractere.

``` c
#include <stdio.h>

int main() {
    char myStr[] = "Minha String";
    myStr[0] = 'W';
    printf("%s", myStr);
    // Output: Winha String

    return 0;
}
```

O caractere que vai substituir deve estar entre aspas simples.

Desse modo, é possível substituir caracteres procurando-os dentro da string, podendo assim, substituir caracteres mesmo sem saber seus índices.

``` c
#include <stdio.h>
#include <string.h>

void replace(char *str, char old, char new);

int main() {
    char myStr[15] = "Hello, World!";
    strReplace(myStr, 'W', 'M');
    printf("%s", myStr); // Output: Hello, Morld!
}

void strReplace(char *str, char old, char new) {
    for (int i = 0; i < strlen(str); i++) {
        if (str[i] == old) {
            str[i] = new;
        }
    }
}
```

### Strings Para Maiúsculo ou Minúsculo

As funções **`toupper()`** e **`tolower()`** são da biblioteca padrão **`ctype.h`**, e elas convertem um caractere para maiúsculo ou minúsculo, respectivamente.

**Exemplo com `toupper()`:**

``` c
#include <stdio.h>
#include <ctype.h>

int main() {
    char myChar = 'a';
    myChar = toupper(myChar);
    printf("%c", myChar); // Output: A
}
```

**Exemplo com `tolower()`:**

``` c
#include <stdio.h>
#include <ctype.h>

int main() {
    char myChar = 'A';
    myChar = tolower(myChar);
    printf("%c", myChar); // Output: a
}
```

Para **converter uma string inteira**, é necessário criar um loop que percorre toda a string, e assim, converter caractere por caractere.

``` c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void converterParaMinusculo(char str[]) {
    for (int i = 0; i < strlen(str); i++) {
        str[i] = tolower((unsigned char)str[i]);
    }
}

int main() {
    char myStr[15] = "Hello, World!";
    converterParaMinusculo(myStr);
    printf("%s", myStr); // Output: hello, world!
}
```

No exemplo acima:

1. A função `converterParaMinusculo()` recebe uma string que será convertida em letras minúsculas.

1. Há um loop `for` que percorre a string passada.

1. Dentro do loop, é atribuído os caracteres minúsculos à string (substituindo a string original).

1. `(unsigned char)` é útil para que a função `tolower()` funcione corretamente.

Se o objetivo for converter a string para maiúculo, é só substituir a função `tolower()` por `toupper()`.

### Inverter String

Há várias formas de inverter a posição dos caracteres de uma string. É possível, por exemplo, usar um loop para inverter a posição de cada caractere de uma string, considerando uma cópia da string original.

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

void inverterString(char str[]) {
    // Comprimento da string
    size_t larguraStr = strlen(str);

    // Cópia da string
    char strCopy[larguraStr + 1];
    strcpy(strCopy, str);

    // Inverte a posição dos caracteres
    int j = larguraStr - 1;
    for (int i = 0; i < larguraStr; i++) {
        str[i] = strCopy[j];
        j--;
    }
}

int main() {
    // String que será invertida
    char myStr[] = "Hello, World!";

    // Inverte a string
    inverterString(myStr);

    // Imprime a string invertida
    printf("%s", myStr);

    return 0;
}
```

No exemplo acima:

* A função que inverte a string cria uma cópia da string para usá-la como referência.

* Possui um loop que inverte a posição dos caracteres, usando como referência a cópia da string.

* Uma observação é que essa função **modifica a string original**.

### Remover Espaços no Início e Fim de uma String

Para remover espaços desnecessário no início e no fim de uma string, podemos fazer o seguinte:

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Função que remove os espaços em branco no início e fim da string
void removerEspacos(char *str) {
    int inicio = 0;
    int fim = strlen(str) - 1;

    // Conta os espaços em branco do início
    while (isspace((unsigned char)str[inicio])) {
        inicio++;
    }

    // Conta os espaços em branco do fim
    while (fim > inicio && isspace((unsigned char)str[fim])) {
        fim--;
    }

    // Copia a string sem espaços para a string original
    int i, j = 0;
    for (i = inicio; i <= fim; i++) {
        str[j++] = str[i];
    }

    // Adiciona o caracter nulo no final da string
    str[j] = '\0';
}

int main() {
    char str[] = "   Hello, World!   ";
    printf("String original: \"%s\"\n", str);

    removerEspacos(str);
    printf("Nova string: \"%s\"\n", str);

    return 0;
}
```

**Análise do Exemplo:**

1. Importação das bibliotecas.

    ``` c
    #include <stdio.h>
    #include <string.h>
    #include <ctype.h>
    ```

    * **'`stdio.h`'**: Para usar `printf()`.
    * **'`string.h`'**: Para usar `strlen()`.
    * **'`ctype.h`'**: Para usar `isspace()`, que é uma função que retorna verdadeiro quando seu argumento é um espaço em branco.

1. Declaração de função.

    ``` c
    void removerEspacos(char *str)
    ```

    Aqui, é declarada uma função que altera uma string existente, excluindo os espaços em branco no início e no fim da string.

    Recebe como argumento um ponteiro para uma string.

1. Declaração de variáveis para início e fim.

    ``` c
    int inicio = 0;
    int fim = strlen(str) - 1;
    ```

    Aqui, são declaradas as variáveis `inicio` e `fim`, que representam os índices inicial e final da string após a remoção dos espaços em branco.

1. Verificar espaços no início.

    ``` c
    while (isspace((unsigned char)str[inicio])) {
        inicio++;
    }
    ```

    Aqui, há um loop que verifica se o caractere inicial da string é um espaço em branco, e se for, incrementa sobre a variável `inicio`, continuando a verificar até o caractere não ser um espaço em branco.

    O cast para `unsigned char` dentro da função `isspace()` é uma prática comum e é feito para garantir que o argumento fornecido seja um valor dentro do intervalo representável pela tabela ASCII, sem o risco de comportamento indefinido.

1. Verifica espaços no fim.

    ``` c
    while (fim > inicio && isspace((unsigned char)str[fim])) {
        fim--;
    }
    ```

    É usado um loop `while` para verificar duas coisas: se a variável `fim` é maior `inicio`, e se o caractere que corresponde ao fim é um espaço em branco. Se ambas as condições forem verdadeiras, será decrementado da variável `fim` até que o último caractere não seja um espaço em branco.

1. Remove os espaços em branco do início e fim da string.

    ``` c
    int i, j = 0;
    for (i = inicio; i <= fim; i++) {
        str[j++] = str[i];
    }
    ```

    Aqui, há um loop `for` que move os caracteres para a esquerda usando as variáveis `inicio` e `fim`. Basicamente, o loop passa por toda a string, com exceção dos caracteres em branco no início e fim da string.

1. Caractere nulo.

    ``` c
    str[j] = '\0';
    ```

    Por fim, a string é encerrada com o caractere nulo.

### Remover Quebras de Linha em Strings

Para remover quebras de linhas em strings, é necessário procurar e remover o caractere `\n` dentro da string.

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

void removerQuebraDeLinha(char *str) {
    // Comprimento da string
    int comprimento = strlen(str);

    // Procura e exclui quebras de linha na string
    int i, j;
    for (i = j = 0; i < comprimento; i++) {
        if (str[i] != '\n') {
            str[j++] = str[i];
        }
    }

    // Adiciona o caractere nulo para indicar o final da nova string
    str[j] = '\0';
}

int main() {
    char str[] = "Hello,\n World!";
    printf("String original: %s\n", str);

    removerQuebraDeLinha(str);
    printf("Nova string: %s\n", str);

    return 0;
}
```

### Funções de String

Para usar as funções de string, deve primeiro ser importado **`<string.h>`**.

* **'`strlen()`'**: Retorna a largura da string.

    ``` c
    #include <stdio.h>
    #include <string.h>

    int main() {
        char str[] = "Oi!";
        printf("%d", strlen(str));
        // Output: 3

        return 0;
    }
    ```

* **'`strnlen()`'**: Como a função `strlen()`, porém aceitando um argumento opcional que especifica o número máximo de caracteres a serem verificados.

    ``` c

    ```

* **'`strcat()`'**:

* **'`strncat`'**:

* **'`strcpy()`'**: Cria uma cópia da string.

    Recebe dois argumentos:

    1. Destino: Variável de string que vai receber a string. Deve ser declarada com uma largura.
    1. Origem: String que vai ser copiada.

    Se a string de destino já possuir um valor, ela terá seu valor sobrescrito.

    ``` c
    #include <stdio.h>
    #include <string.h>

    int main() {
        char str[] = "Oi!";
        char copia_str[4];
        strcpy(copia_str, str);

        printf("%s", copia_str);
        // Output: Oi!

        return 0;
    }
    ```

* **'`strncpy()`'**:

* **'`strcmp()`'**:

* **'`strncmp()`'**:

* **'`strchr()`'**:

* **'`strstr()`'**:

* **'`sprintf()`'**: Formata e armazena uma sequência de caracteres em uma string.

    Seus argumentos são:

    1. Variável string que receberá a sequência.
    1. Sequência.
    1. Formatadores de valores.

    ``` c
    #include <stdio.h>

    int main() {
        char str[20];
        int num = 13;

        sprintf(str, "Número: %d", num);

        printf("%s", str);
        // Output: Número: 13

        return 0;
    }
    ```

* **'`sscanf()`'**:

* **'`strtok()`'**:

* **'`strtok_r()`'**:

* **'`strspn()`'**:

* **'`strcspn()`'**:

* **'`strpbrk()`'**:

* **'`memset()`'**:

* **'`memcpy()`'**:

* **'`memmove()`'**:

* **'`memcmp()`'**:

* **'`strerror()`'**:

* **'`strerror_r()`'**:

* **'`strcoll()`'**:

* **'`strxfrm()`'**:

* **'`strdup()`'**:

### Alinhamento de Texto

#### Alinhar à Direta

Para alinhar um texto à direita, você pode especificar um valor junto ao formato.

``` c
#include <stdio.h>

int main() {
    char str[] = "Hello, World!";
    printf("\"%25s\"", str);
    // Output: "            Hello, World!"

    return 0;
}
```

#### Alinhar à Esquerda

Para alinhar um texto à esquerda, você pode especificar um valor negativo junto ao formato.

``` c
#include <stdio.h>

int main() {
    char str[] = "Hello, World!";
    printf("\"%-25s\"", str);
    // Output: "Hello, World!            "

    return 0;
}
```

#### Alinhar à Esquerda ou Direita Com Caracteres

Para que ao invés de espaços em branco hajam algum caractere específico, você pode usar um loop.

``` c
#include <stdio.h>
#include <string.h>

void alinharEsquerda(char texto[], int larguraTotal, char caractere) {
    // Espaços a serem preenchidos
    int espacos = larguraTotal - strlen(texto);

    // Imprime o texto
    printf("%s", texto);

    // Preenche os espaços com o caractere
    for (int i = 0; i < espacos; i++) {
        printf("%c", caractere);
    }

    // Quebra de linha
    printf("\n");
}

void alinharDireita(char texto[], int larguraTotal, char caractere) {
    // Espaços a serem preenchidos
    int espacos = larguraTotal - strlen(texto);

    // Preenche os espaços com o caractere
    for (int i = 0; i < espacos; i++) {
        printf("%c", caractere);
    }

    // Imprime o texto
    printf("%s", texto);

    // Quebra de linha
    printf("\n");
}

int main() {
    // Texto que será alinhado
    char str[] = "Hello, World!";

    // Largura total
    int larguraTotal = 20;

    // Caractere que preencherá os espaços
    char caractere = '*';

    // Texto alinhado à esquerda
    alinharEsquerda(str, larguraTotal, caractere);  // Output: Hello, World!*******

    // Texto alinhado à direita
    alinharDireita(str, larguraTotal, caractere);   // Output: *******Hello, World!

    return 0;
}
```

#### Centralizar Texto

Para centralizar um texto, é preciso fazer o seguinte cálculo:

1. Definir o texto que será centralizado.

    Valos considerar a string "`Hello, World!`".

    ``` c
    char texto[] = "Hello, World!";
    ```

1. Definir a largura do espaço total que será ocupado.

    A largura total será 25, logo, o texto deve ficar centralizado em 25 caracteres.

    ``` c
    int larguraTotal = 25;
    ```

1. Calcular o espaço à esquerda do texto.

    Será o seguinte:

    ``` c
    int espacoEsquerda = (larguraTotal - strlen(texto)) / 2;
    ```

    * É usada a função `strlen()` para obter a largura do texto.

    * A largura total é subtraída pela largura do texto. É feito para calcular o espaço disponível para espaços em branco.

    * É feita a divisão por 2 para distribuir igualmente o espaço à esquerda e à direita do texto.

1. Calcular o espaço à direita do texto.

    Será o seguinte:

    ``` c
    int espacoDireita = larguraTotal - strlen(texto) - espacoEsquerda;
    ```

    * A subtração entre a largura total e a largura do texto é feita para calcular o espaço disponível após o texto.

    * A subtração entre o resultado da subtração anterior e o espaço à esquerda é feita para distribuir os espaços restantes após os espaços à esquerda do texto.

1. Imprimir o texto centralizado.

    Será o seguinte:

    ``` c
    printf("%*s%s%*s" espacoEsquerda, "", texto, espacoDireita, "");
    ```

    * O formato `%*s` é usado para imprimir uma string com uma largura dinâmica. Quando usado antes de `""`, adiciona os espaços em branco à esquerda e à direita do texto.

    * O formato `%s` é usado para imprimir o texto, e por isso está entre os outros formatos.

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

int main() {
    // Texto que será centralizado
    char texto[] = "Hello, World!";

    // Largura total
    int larguraTotal = 25;

    // Espaços à esquerda do texto
    int espacoEsquerda = (larguraTotal - strlen(texto)) / 2;

    // Espaços à direita do texto
    int espacoDireita = larguraTotal - strlen(texto) - espacoEsquerda;

    // Imprime o texto centralizado
    printf("%*s%s%*s", espacoEsquerda, "", texto, espacoDireita, "");

    // Output: "      Hello, World!      "

    return 0;
}
```

Para facilitar o uso, pode-se criar uma função:

``` c
#include <stdio.h>
#include <string.h>

void centralizarTexto(char texto[], int larguraTotal) {
    // Comprimento do texto
    int comprimentoTexto = strlen(texto);

    // Espaços à esquerda do texto
    int espacoEsquerda = (larguraTotal - comprimentoTexto) / 2;

    // Espaços à direta do texto
    int espacoDireita = larguraTotal - comprimentoTexto - espacoEsquerda;

    // Imprime a string formatada
    printf("%*s%s%*s", espacoEsquerda, "", texto, espacoDireita, "");
}

int main() {
    // Texto que será centralizado
    char texto[] = "Hello, World!";

    // Largura total
    int larguraTotal = 25;

    // Imprime o texto formatado
    centralizarTexto(texto, larguraTotal);

    // Output: "      Hello, World!      "

    return 0;
}
```

##### Centralizar Entre Caracteres

Se você deseja centralizar um texto entre algum caractere específico, você pode usar um loop para imprimir o caracter para preencher os espaços que o texto não ocupa.

``` c
#include <stdio.h>
#include <string.h>

void centralizarEntreCaractere(char texto[], int larguraTotal, char caractere) {
    // Comprimento do texto
    int comprimentoTexto = strlen(texto);

    // Espaços à esquerda do texto
    int espacoEsquerda = (larguraTotal - comprimentoTexto) / 2;

    // Espaços à direta do texto
    int espacoDireita = larguraTotal - comprimentoTexto - espacoEsquerda;

    // Imprime o caractere preenchendo os espaços à esquerda
    for (int i = 0; i < espacoEsquerda; i++) {
        printf("%c", caractere);
    }

    // Imprime o texto
    printf("%s", texto);

    // Imprime o caractere preenchendo os espaços à direita
    for (int i = 0; i < espacoDireita; i++) {
        printf("%c", caractere);
    }
}

int main() {
    // Texto que será centralizado
    char texto[] = "Hello, World!";

    // Largura total
    int larguraTotal = 25;

    // Caractere que preencherá os espaços
    char caractere = '-';

    // Imprime o texto formatado
    centralizarEntreCaractere(texto, larguraTotal, caractere);

    // Output: ------Hello, World!------

    return 0;
}
```

E se desejar centralizar um texto entre **múltiplos caracteres**, você pode usar um loop da seguinte forma:

``` c
#include <stdio.h>
#include <string.h>

void centralizarEntreCaractere(char texto[], int larguraTotal, char caracteres[]) {
    // Comprimento do texto
    int comprimentoTexto = strlen(texto);

    // Comprimento dos caracteres que preencherão os espaços
    int comprimentoCaracteres = strlen(caracteres);

    // Espaços à esquerda do texto
    int espacoEsquerda = ((larguraTotal - comprimentoTexto) / 2);

    // Espaços à direta do texto
    int espacoDireita = larguraTotal - comprimentoTexto - espacoEsquerda;

    // Caractere atual
    int charAtual;

    // Imprime o caractere preenchendo os espaços à esquerda
    charAtual = 0;
    for (int i = 0; i < espacoEsquerda; i++) {
        if (charAtual == comprimentoCaracteres) {
            charAtual = 0;
        }
        printf("%c", caracteres[charAtual]);
        charAtual++;
    }

    // Imprime o texto
    printf("%s", texto);

    // Imprime o caractere preenchendo os espaços à direita
    charAtual = 0;
    for (int i = 0; i < espacoDireita; i++) {
        if (charAtual == comprimentoCaracteres) {
            charAtual = 0;
        }
        printf("%c", caracteres[charAtual]);
        charAtual++;
    }
}

int main() {
    // Texto que será centralizado
    char texto[] = "Hello, World!";

    // Largura total
    int larguraTotal = 25;

    // Caractere que preencherá os espaços
    char caractere[] = "=-";

    // Imprime o texto formatado
    centralizarEntreCaractere(texto, larguraTotal, caractere);

    // Output: =-=-=-Hello, World!=-=-=-

    return 0;
}
```

## Funções

São blocos de códigos reutilizáveis que podem receber dados.

**Sintaxe:**

``` c
void myFunction() {
    // Código a ser executado
}
```

`void` significa que a função não retorna nenhum valor.

**Exemplo:**

``` c
#include <stdio.h>

// Função que imprime "Olá, Mundo!"
void myFunction() {
    printf("Olá, Mundo!");
}

int main() {
    // Chama a função
    myFunction(); // Output: Olá, Mundo!

    return 0;
}
```

Perceba que a função não está dentro da função `main()`.

Como visto no exemplo acima, escrever o nome da função com parênteses no fim chama a função.

### Retorno de Valores

Ao declarar uma função, o tipo de dado que vem antes do nome é o tipo de dado que a função retorna.

``` c
#include <stdio.h>

// Função que retorna o resultado de 2 + 2
int doisMaisDois() {
    return 2 + 2;
}

int main() {
    int valor = doisMaisDois();
    printf("%d", valor); // Output: 4

    return 0;
}
```

Funções do tipo `void` não retornam valores, como visto anteriormente.

### Parâmetros

São usados para receber dados quando a função é chamada.

**Sintaxe:**

``` c
tipoDeRetorno myFunction(tipo param1, tipo param2, tipo param3) {
    // Código da função
}
```

**Exemplo:**

``` c
#include <stdio.h>

// Função que retorna a soma de dois valores
int soma(int valor1, int valor2) {
    return (valor1 + valor2);
}

int main() {
    printf("%d\n", soma(2, 3)); // Output: 5
    printf("%d\n", soma(5, 2)); // Output: 7
    printf("%d\n", soma(1, 0)); // Output: 1

    return 0;
}
```

### Escopo de Variáveis

Existem dois tipos principais de escopo: escopo global e escopo local.

#### Escopo Global

Variáveis declaradas fora de qualquer função têm escopo global. Essas variáveis podem ser acessadas por qualquer parte do programa, incluindo dentro de funções.

**Exemplo:**

``` c
#include <stdio.h>

int num = 25; // Variável global

int main() {
    printf("Número: %d\n", num); // Output: Número: 25

    return 0;
}
```

Funções podem acessar diretamente variáveis globais, sem a necessidade de parâmetros.

``` c
#include <stdio.h>

int num = 25; // Variável global

void printValue() {
    printf("Número: %d\n", num);
}

int main() {
    printValue(); // Output: Número 25

    return 0;
}
```

#### Escopo Local

Variáveis declaradas dentro de uma função têm escopo local. Elas só podem ser acessadas dentro dessa função.

**Exemplo:**

``` c
#include <stdio.h>

void myFunction() {
    int x = 2;
    int y = 5;
    printf("A soma entre %d e %d é %d\n", x, y, x + y);
}

int main() {
    myFunction(); // Output: A soma entre 2 e 5 é 7

    return 0;
}
```

#### Escopo de Bloco

Declarar variáveis dentro de um bloco como `if`, faz com que essas variávels só possam ser acessados dentro desse bloco.

**Exemplo incorreto:**

``` c
#include <stdio.h>

int main() {
    int x = 5;
    if (x == 5) {
        int y = 10;
    } else {
        int y = 15;
    }

    printf("Valor de y: %d\n", y); // Isso não funciona!

    return 0;
}
```

#### Prioridade de Variáveis

Variáveis locais têm prioridade sobre variáveis globais, ou seja, caso haja duas variáveis com o mesmo nome, será considerada a que tem escopo local.

### Funções Aninhadas

Também chamadas de funções internas, são funções declaradas dentro de outra função.

A função interna terá acesso a todas as variáveis e parâmetros da função externa (também chamada de função pai).

É útil quando o propósito da função é servir exclusivamente dentro de outra e não precisa ser utilizada em outros contextos.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdbool.h>

void soma(int num1, int num2, bool multi) {
    void multiplicar() {
        printf("%d x %d = %d\n", num1, num2, num1 * num2);
    }

    // Imprime a soma dos valores
    printf("%d + %d = %d\n", num1, num2, num1 + num2);

    // Multiplica os valores se necessário
    if (multi) {
        multiplicar();
    }

}

int main() {
    // Variáveis que serão somadas
    int x = 5;
    int y = 2;
    bool multiplicar = true;

    // Mostra a soma e multiplicação dos valores
    soma(x, y, multiplicar);

    /* Output:
    5 + 2 = 7
    5 x 2 = 10
    */

    return 0;
}
```

> **Observação:** Funções aninhadas podem não ser suportadas por todos os compiladores, sendo comum a prática de manter as funções separadas.

### Funções Variádicas

São funções que aceitam um número variável de argumentos. São implementadas usando a biblioteca padrão **`stdarg.h`**.

A função `printf()` é o exemplo mais comum de função variádica, pois a mesma recebe um argumento obrigatório e os demais variam de acordo com a quantidade de formatos.

Em `stdarg.h`, são definidas quatro macros:

* **`va_list`**: Armazena informações sobre os argumentos variádicos.

* **`va_start`**: Inicializa a lista de argumentos variádicos. Deve ser chamada antes de acessar os argumentos.

* **`va_arg`**: Retorna o primeiro argumento na lista, com base no tipo especificado.

* **`va_end`**: Finaliza o uso da lista de argumentos variádicos.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdarg.h>

int calcularSoma(int num, ...) {
    va_list args;
    va_start(args, num);

    int soma = 0;

    for (int i = 0; i < num; i++) {
        soma += va_arg(args, int);
    }

    va_end(args);

    return soma;
}

int main() {
    int soma = calcularSoma(5, 1, 2, 3, 4, 5);
    printf("Soma: %d\n", soma); // Output: Soma: 15
}
```

**Análise do Exemplo:**

1. Importação de bibliotecas:

    ``` c
    #include <stdio.h>
    #include <stdarg.h>
    ```

    Aqui, são importadas as bibliotecas `stdio.h`, para a função `printf()`, e `stdarg.h`, para trabalhar com funções variádicas.

1. Declaração da função `calcularSoma()`

    ``` c
    int calcularSoma(int num, ...)
    ```

    Essa função retorna a soma de vários números inteiros. O primeiro argumento deve ser a quantidade de argumentos que serão passados a seguir.

1. Acesso aos argumentos

    ``` c
    va_list args;
    va_start(args, num);
    ```

    Primeiro, é criado uma variável do tipo `va_list` chamada `args`. Após isso, essa variável é inicializada como uma lista que armazena os argumentos passados (com exceção do primeiro, que representa a quantidade de argumentos).

1. Cálculo da soma

    ``` c
    int soma = 0;
    for (int i = 0; i < num; i++) {
        soma += va_arg(args, int);
    }
    ```

    Aqui, há uma variável `soma`, que tem como função armazenar a soma dos argumentos passados.

    Após isso, há um loop que acessa os argumentos e calcula a soma entre eles.

    A função `va_arg()` é usada para acessar cada argumento na lista com base no tipo de valor do argumento a ser acessado.

1. Finalizar o uso da lista de argumentos

    ``` c
    va_end(args);
    ```

    A função `va_end()` é usada para finalizar o uso da lista de argumentos variádicos. Isso garante a liberação de quaisquer recursos associados à lista.

1. Retorno da soma

    ``` c
    return soma;
    ```

    Aqui, é retornado a soma de todos os argumentos variádicos passados.

1. Exemplo de uso no `main()`

    ``` c
    int main() {
        int soma = calcularSoma(5, 1, 2, 3, 4, 5);
        printf("Soma: %d\n", soma); // Output: Soma: 15
    }
    ```

    Aqui é mostrado uma exemplo de uso da função `calcularSoma()`.

## Math

Para usar funções matemáticas, é necessário incluir `math.h`.

``` c
#include <math.h>
```

Algumas funções pertencem a biblioteca `stdlib.h`.

``` c
#include <stdlib.h>
```

### Funções Matemáticas

* **'`sqrt()`'**: Retorna a raíz quadrada de um número.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f", sqrt(25)); // Output: 5.000000
        return 0;
    }
    ```

* **'`cbrt()`'**: Retorna a raíz cúbica de um número.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", cbrt(10)); // Output: 2.154435
        printf("%f\n", cbrt(60)); // Output: 3.914868
        printf("%f\n", cbrt(21)); // Output: 2.758924

        return 0;
    }
    ```

* **'`round()`'**: Arredonda um número e retorna o resultado.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", round(1.2)); // Output: 1.000000
        printf("%f\n", round(5.8)); // Output: 6.000000
        printf("%f\n", round(3.3)); // Output: 3.000000

        return 0;
    }
    ```

* **'`ceil()`'**: Arredonda um número para cima e retorna o resultado.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", ceil(1.2)); // Output: 2.000000
        printf("%f\n", ceil(5.8)); // Output: 6.000000
        printf("%f\n", ceil(3.3)); // Output: 4.000000

        return 0;
    }
    ```

* **'`floor()`'**: Arredonda um número para baixo e retorna o resultado.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", floor(1.2)); // Output: 1.000000
        printf("%f\n", floor(5.8)); // Output: 5.000000
        printf("%f\n", floor(3.3)); // Output: 3.000000

        return 0;
    }
    ```

* **'`pow()`'** Eleva um número a outro e retorna o resultado.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", pow(5, 2)); // Output: 25.000000
        printf("%f\n", pow(3, 3)); // Output: 27.000000
        printf("%f\n", pow(4, 0)); // Output: 1.000000

        return 0;
    }
    ```

* **'`abs()`'**: Retorna o valor absoluto de um número.

    ``` c
    #include <stdio.h>
    #include <stdlib.h>

    int main() {
        printf("%d\n", abs(-5));    // Output: 5
        printf("%d\n", abs(2));     // Output: 2
        printf("%d\n", abs(7));     // Output: 7

        return 0;
    }
    ```

* **'`labs()`'**: Retorna o valor absoluto de um número `long`.

    ``` c
    #include <stdio.h>
    #include <stdlib.h>

    int main() {
        printf("%ld\n", labs(123456789L));     // Output: 123456789
        printf("%ld\n", labs(-123456789L));    // Output: 123456789

        return 0;
    }
    ```

* **'`llabs()`'**: Retorna o valor absoluto de um número `long long`.

    ``` c
    #include <stdio.h>
    #include <stdlib.h>

    int main() {
        printf("%lld\n", llabs(123456789123456789LL));
        // Output: 123456789123456789
        printf("%lld\n", llabs(-123456789123456789L));
        // Output: 123456789123456789

        return 0;
    }
    ```

* **'`sin()`'**: Retorna o seno de um valor em radianos.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", sin(30.0 * M_PI / 180.0)); // Output: 0.500000
        printf("%f\n", sin(45.0 * M_PI / 180.0)); // Output: 0.707107
        printf("%f\n", sin(60.0 * M_PI / 180.0)); // Output: 0.866025

        return 0;
    }
    ```

* **'`cos()`'**: Retorna o cosseno de um valor em radianos.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", cos(30.0 * M_PI / 180.0)); // Output: 0.866025
        printf("%f\n", cos(45.0 * M_PI / 180.0)); // Output: 0.707107
        printf("%f\n", cos(60.0 * M_PI / 180.0)); // Output: 0.500000

        return 0;
    }
    ```

* **'`tan()`'**: Retorna a tangente de um valor em radianos.

    ``` c
    #include <stdio.h>
    #include <math.h>

    int main() {
        printf("%f\n", tan(30.0 * M_PI / 180.0)); // Output: 0.577350
        printf("%f\n", tan(45.0 * M_PI / 180.0)); // Output: 1.000000
        printf("%f\n", tan(60.0 * M_PI / 180.0)); // Output: 1.732051

        return 0;
    }
    ```

## Memória

O gerenciamento de memória é fundamental para garantir que o programa seja eficiente, seguro e livre de vazamentos de memória.

### Endereço de Memória

Um **endereço de memória** é a localização de uma variável na memória do computador. Toda variável ocupa um espaço na memória, e esse espaço é identificado por um endereço.

Cada endereço é um número hexadecimal que representa a localização de uma variável específica na RAM.

Com o operador `&` é possível obter o endereço de memória de uma variável.

Para imprimir esses endereços, é usado o formato **`%p`**.

``` c
#include <stdio.h>

int main() {
    int x = 1;
    printf("Endereço: %p\n", (void*)&x);
    // Output: 0061FF1C

    return 0;
}
```

O uso do cast `(void*)` é importante para evitar avisos do compilador.

### Ponteiros

Ponteiros são variáveis que armazenam o endereço de memória de uma outra variável.

São declarados como variáveis, porém os nomes dessas variáveis se iniciam com `*` e seus valores são variáveis que se iniciam com `&` (referencia o endereço de memória da variável).

Para declarar um ponteiro:

``` c
int *ponteiro;
int* ponteiro;
int * ponteiro;

// Todos funcionam da mesmo forma
```

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    int x = 5;

    // Declaração de ponteiro
    int *ponteiro_x;

    // Atribuição de endereço de memória para o ponteiro
    ponteiro_x = &x;

    // Imprime o ponteiro (endereço de memória de x)
    printf("%p", (void*)ponteiro_x); // Output: 0061FF18

    return 0;
}
```

Sobre o exemplo acima, temos alguns detalhes importantes:

* Ponteiros são declarados mais comumente com `*` antes do nome da variável.

* Ao atribuir um endereço a um ponteiro, não deve ser usado `*` ao início do identificador (a menos que a atribuição seja feita no momento da declaração).

* Os valores de ponteiros são endereços de memória, por isso ao atribuir esses endereços é especificada a variável com `&` no início para referenciar o endereço de memória dessa variável.

* Ao imprimir endereços de variáveis deve ser usado o formatador de tipo **`%p`**.

* No exemplo, `(void*)` é um cast para que não sejam mostrados avisos do compilador.

* É uma boa prática definir o tipo do ponteiro igual ao tipo da variável cujo endereço de memória é guardado por esse ponteiro. Ou seja, se uma variável é do tipo `int`, é interessante que seu ponteiro seja também do tipo `int`.

#### Desreferência

Usar `*` antes do identificador de um ponteiro sem ser para declará-lo irá referenciar o valor que o endereço de memória desse ponteiro guarda.

``` c
#include <stdio.h>

int main() {
    int x = 5;
    int *ponteiro_x = &x;

    printf("%d", *ponteiro_x); // Output: 5

    return 0;
}
```

#### Ponteiros e Arrays

É possível acessar os endereços de memória dos elementos de um array.

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};

    int x;
    for (x = 0; x < 4; x++) {
        printf("%p\n", &myArray[x]);
    }
    /* Output:
    0061FF0C
    0061FF10
    0061FF14
    0061FF18
    */

    return 0;
}
```

Perceba que cada elemento do array possui 4 bytes a mais que o elemento anterior. Acontece porque inteiros ocupam 4 bytes na memória.

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};

    printf("%lu", sizeof(myArray));
    // Output: 16

    return 0;
}
```

O nome do array é um ponteiro para o primeiro elemento do array.

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};

    printf("%p\n", myArray);
    // Output: 0061FF10

    printf("%p", &myArray[0]);
    // Output: 0061FF10

    return 0;
}
```

Então é possível usar `*` antes do nome do array para fazer desreferência ao primeiro elemento do array, mostrando assim seu valor ao invés de endereço de memória.

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};

    printf("%d", *myArray);
    // Output: 2

    return 0;
}
```

Dessa maneira, `*(myArray + 1)` acessa o segundo elemento do array, `*(myArray + 2)` acessa o terceiro, e assim por diante.

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};

    printf("%d\n", *myArray);
    printf("%d\n", *(myArray + 1));
    printf("%d\n", *(myArray + 2));
    printf("%d\n", *(myArray + 3));
    /* Output:
    2
    4
    6
    8
    */

    return 0;
}
```

O mesmo exemplo acima, poderia ser:

``` c
#include <stdio.h>

int main() {
    int myArray[4] = {2, 4, 6, 8};
    int *arrayPointer = myArray;
    int x;
    for (x = 0; x < 4; x++) {
        printf("%d\n", *(arrayPointer + x));
    }
    /* Output:
    2
    4
    6
    8
    */

    return 0;
}
```

Perceba que não é necessário usar `&` antes do identificador da variável que armazena o array, pois como dito anteriormente, o nome do array é um ponteiro para o primeiro elemento do array.

#### Ponteiros Nulos

É um ponteiro que não aponta para nenhum endereço de memória válido.

São importantes pelos seguintes motivos:

* **Inicialização**: Ao declarar um ponteiro, é uma boa prática iniciá-lo como nulo caso não possua um endereço de memória para ele inicialmente.

    ``` c
    int *ponteiro = NULL;
    ```

* **Testes de Nulidade**: Possibilita testar se um ponteiro está apontando para algum endereço válido antes de tentar acessar ou modificar o valor para o qual ele aponta.

    ``` c
    if (ponteiro != NULL) {
        // Ponteiro possui algum endereço
    } else {
        // Ponteiro nulo
    }
    ```

* **Evita Ponteiros Selvagens**: Ponteiros selvagens são ponteiros que apontam para locais na memória desconhecidos ou inválidos, e ponteiros nulos evitariam esse comportamento de ponteiros.

#### Ponteiros e Strings

Ponteiros são frequentemente usados para manipular strings de forma eficiente.

O nome de um array de caracteres (string) é um ponteiro para o primeiro elemento do array, ou seja, para o primeiro caractere da string. Por isso, não é necessário atribuir `&` ao início do nome do array a um ponteiro.

``` c
char str[] = "Olá, Mundo!";
char *ptr = str; // Ponteiro para o primeiro caractere de `str`
```

Então, incrementar 1 ao ponteiro fará com que o ponteiro avance para o próximo elemento da string.

``` c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Olá";
    char *ptr = str;

    // Imprimindo os caracteres da string
    for (int i = 0; i < strlen(ptr); i++) {
        printf("%c\n", *(ptr + i));
    }
    /* Output:
    O
    l
    á
    */

    return 0;
}
```

#### Ponteiros para Funções

Permitem armazenar e manipular endereços de funções. É útil quando necessário passar funções como argumentos para outras funções ou retornar funções de outras funções.

**Sintaxe:**

``` c
tipo_de_retorno (*nome_ponteiro)(tipo_param1, tipo_param2, ...);
```

**Exemplo:**

``` c
#include <stdio.h>

int soma(int x, int y) {
    return x + y;
}

int (*ponteiroFuncao)(int, int) = soma;

int main() {
    int resultado = ponteiroFuncao(2, 5);
    printf("Resultado: %d\n", resultado);
    // Output: Resultado: 7

    return 0;
}
```

No exemplo acima, é atribuido ao ponteiro o endereço da função `soma()` (não é necessário usar `&`). No `main()` é imprimido o valor que a função retorna.

##### Funções como Argumentos

É possível passar ponteiros de funções como argumentos de outra função.

``` c
#include <stdio.h>

int soma(int x, int y) {
    return x + y;
}

int (*ponteiroFuncao)(int, int) = soma;

void mostrarResultado(int (*funcao)(int, int), int x, int y) {
    int resultado = funcao(x, y);
    printf("Resultado: %d\n", resultado);
}

int main() {
    mostrarResultado(soma, 5, 2);
    // Output: Resultado: 7

    return 0;
}
```

No exemplo acima, a função `mostrarResultado()` imprime uma string com o retorno da função `soma()`. Note os argumentos do ponteiro da função não são passados junto à ela, mas sim a seguir como outros argumentos.

##### Funções como Retorno

``` c
#include <stdio.h>

// Soma dois valores
int soma(int x, int y) {
    return x + y;
}

// Subtrai um valor pelo outro
int subtracao(int x, int y) {
    return x - y;
}

// Multiplica dois valores
int mult(int x, int y) {
    return x * y;
}

// Divide um valor pelo outro
int divisao(int x, int y) {
    return x / y;
}

// Ponteiro de função
int (*selecionarFuncao(const char op))(int, int) {
    switch (op) {
        case '+':
            return soma;
            break;
        case '-':
            return subtracao;
            break;
        case '*':
            return mult;
            break;
        case '/':
            return divisao;
            break;
        default:
            return NULL;
    }
}

int main() {
    // Definição de operador
    char operador = '*';

    // Ponteiro para a função
    int (*funcao)(int, int) = selecionarFuncao(operador);

    // Imprime o resultado
    if (funcao != NULL) {
        int resultado = funcao(5, 2);
        printf("Resultado: %d\n", resultado);
        // Output: Resultado: 7
    } else {
        printf("Operador inválido.\n");
    }

    return 0;
}
```

### Alocação de Memória

Alocar memória é reservar uma região específica da memória do computador para armazenar dados.

Existem duas principais maneiras de alocar memória:

* Alocação na Pilha (Stack Allocation)
* Alocação no Heap (Heap Allocation)

#### Stack Allocation

Se refere à alocação de memória para variáveis locais em uma função, que são armazenadas na pilha de execução do programa.

A pilha é uma região de memória usada para armazenar informações temporárias durante a execução de uma função.

Quando uma função é chamada, um bloco de memória é reservado na pilha para suas variáveis locais e outros dados relacionados à execução da função.

A alocação de pilha é rápida e automática, sendo mais eficiente que a alocação dinâmica de memória.

A desalocação da memória alocada na pilha ocorre automaticamente quando a função que a alocou é concluída.

**Exemplo:**

``` c
void myFunction() {
    int x;          // Variável local alocada na pilha
    char y[15];     // Array local alocado na pilha
}
```

No exemplo acima, as variáveis `x` e `y` são alocadas na pilha quando a função `myFunction()` é chamada. Ao fim da execução dessa função, a memória alocada para essas variáveis é automaticamente liberada.

#### Heap Allocation

"Heap" é uma área de memória usada para armazenar dados dinâmicos durante a execução de um programa.

A alocação de memória heap permite a manipulação flexível da memória durante a execução do programa.

Para alocar memória na heap, é utilizada **`malloc`**. E para liberar a memória, é usada a função **`free()`**. Ambas as funções são da biblioteca padrão **`stdlib.h`**.

##### Funções `malloc()` e `free()`

É usada para alocar dinamicamente uma quantidade específica de memória na heap durante a execução do programa.

Para usá-la, é necessário incluir **`stdlib.h`**.

A sintaxe é a seguinte:

``` c
void* malloc(size_t tamanho);
```

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Tamanho em bytes para alocação
    size_t tamanho = 10;

    // Alocação de memória
    int* ponteiro = (int*)malloc(tamanho * sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

O uso do operador `sizeof` é importante, pois o mesmo retorna a quantidade necessária de bytes para cada tipo de dado.

A função `malloc()` retorna `void`, por isso no exemplo acima há um cast para converter explicitamente o ponteiro para `int*`.

Sempre que a alocação falhar, o ponteiro será `NULL`.

É importante liberar a memória quando a mesma não for mais necessária. Para isso, é usada a função `free()`, como visto acima no exemplo.

##### Função `realloc()`

É usada para realocar dinamicamente a memória que antes foi alocada. Essa função permite ajustar o tamanho da memória alocada, podendo expandi-la ou reduzi-la.

Para usá-la também é necessário a inclusão da biblioteca **`stdlib.h`**.

A sintaxe é a seguinte:

``` c
void* realloc(void* ponteiro, size_t tamanho);
```

* `ponteiro` se refere ao ponteiro da memória previamente alocada.

* `tamanho` se refere ao novo tamanho em bytes que se deseja alocar.

É retornado um ponteiro para a nova área de memória alocada, ou `NULL` se a alocação não for bem-sucedida, e se assim for, a memória original permanece inalterada.

> Passar `NULL` como ponteiro fará `realloc()` agir como `malloc()`.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Alocação de memória
    int* ponteiro = (int*)malloc(10 * sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Modificando a memória alterada
    int* novo_ponteiro = (int*)realloc(ponteiro, 5 * sizeof(int));

    // Verificando se a realocação foi bem-sucedida
    if (novo_ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Atualizando o ponteiro
    ponteiro = novo_ponteiro;

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

##### Função `calloc()`

É usada para alocar dinamicamente um bloco de memória para um número específico de elementos, inicializando todos os bits de memória alocada para zero.

Assim como as outras funções mencionadas, deve ser incluída a biblioteca **`stdlib.h`**.

A sintaxe é a seguinte:

``` c
void* calloc(size_t num_elementos, size_t tam_elemento);
```

* `num_elementos` se refere ao número de elementos que serão alocados.
* `tam_elementos` se refere, em bytes, o tamanho de cada elemento.

A quantidade de memória alocada por `calloc()` é equivalente a `num_elementos * tam_elemento` e retorna um ponteiro para o início dessa região de memória. Se a alocação falhar, é retornado `NULL`.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Alocação de memória para um array de 3 inteiros
    int* ponteiro = (int*)calloc(3, sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Uso da memória alocada
    for (int i = 0; i < 3; i++) {
        printf("%d\n", ponteiro[i]);
    }
    /* Output:
    0
    0
    0
    */

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

##### Boas Práticas ao Alocar Memória

* Evitar o uso de memória não inicializada.
* Verificar se a alocação de memória foi bem-sucedida.
* Liberar memória quando a mesma não for mais necessária.
* Inicie a memória com `calloc()` se desejar que cada byte seja zero.
* Atribuir NULL ao ponteiro para evitar referências a memória não alocada.

##### Inicialização da Memória

Ao alocar memória dinamicamente, a memória não é automaticamente inicializada. Ela contém o que é geralmente chamado de "lixo de memória" (*garbage value*), que são valores indeterminados que podem ser qualquer coisa.

Inicializar a memória significa definir explicitamente algum valor inicial a ela.

``` c
#include <stdlib.h>

int main() {
    // Alocação de memória
    int* ponteiro = (int*)malloc(5 * sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Definindo todos os elementos da memória para zero
    for (int i = 0; i < 5; i++) {
        ponteiro[i] = 0;
    }

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

Ou, você pode  usar a função **`memset()`** da biblioteca padrão `string.h`.

``` c
#include <stdlib.h>
#include <string.h>

int main() {
    // Alocação de memória
    int* ponteiro = (int*)malloc(5 * sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Definindo todos os elementos da memória para zero
    memset(ponteiro, 0, 5 * sizeof(int));

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

##### Alocação de Strings

É especialmente útil em funções que retornam strings, pois strings não podem ser retornadas diretamente.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char *helloWorld() {
    // Aloca memória para a string
    char *str = (char*)malloc(strlen("Hello, World!") + 1);

    // Verifica se a alocação foi bem-sucedida
    if (str == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Copia conteúdo para a string
    strcpy(str, "Hello, World!");

    // Retorna a string
    return str;
}

int main() {
    // Chama a função para obter a string
    char *mensagem = helloWorld();

    // Imprime a string
    printf("%s\n", mensagem); // Output: Hello, World!

    // Libera a memória alocada para a string
    free(mensagem);
}
```

**Analisando o código acima:**

1. Foi declarada uma função que tem como objetivo retornar a string `"Hello, World!"` (na verdade o ponteiro para essa string).

1. Nessa função, foi alocado dinamicamente um espaço na memória para a string `"Hello, World!"` com a função `malloc()`, que recebeu como argumento a largura da string + 1. Não foi necessário o uso do operador `sizeof` porque por padrão todo tipo `char` é igual a 1 byte. A soma de mais 1 ao fim, é para o caractere nulo.

1. É verificado se a alocação foi bem-sucedida.

1. Com a função `strcpy()`, é feita a cópia da string `"Hello, World!"` para o ponteiro da string que será retornada.

1. É retornada a string.

1. Na função principal é chamada a função definida anteriormente para obter a string `"Hello, World!"`, para então imprimí-la na tela.

1. Por fim, é liberada a memória alocada para a string para evitar vazamentos de memória.

##### Alocação de Estruturas

<!-- Não demore a escrever, por favor :) -->

##### Alocação de Matrizes Dinâmicas

Uma matriz dinâmica é um array de arrays que contém linhas e colunas, e seus valores são definidos ao decorrer do programa, o que significa que em diferentes execuções essa matriz pode possuir diferentes tamanhos.

Para alocar dinamicamente uma matriz dinâmica, é necessário seguir alguns passos.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

// Aloca dinamicamente as linhas e as colunas de uma matriz
int **linhasColunasMatriz(int linhas, int colunas) {
    // Aloca dinamicamente as linhas da matriz
    int **matriz = (int**)calloc(linhas, sizeof(int*));

    // Verifica se a alocação das linhas foi bem-sucedida
    if (matriz == NULL) {
        fprintf(stderr, "ERRO | Falha ao alocar as linhas.\n");

        // Libera a memória antes encerrar
        for (int x = linhas - 1; x >= 0; x--) {
            free(matriz[x]);
        }
        free(matriz);

        // Encerra o programa
        exit(EXIT_FAILURE);
    }

    // Aloca dinamicamente as colunas da matriz
    for (int j = 0; j < linhas; j++) {
        matriz[j] = (int*)calloc(colunas, sizeof(int*));

        // Verifica se a alocação das colunas foi bem-sucedida
        if (matriz[j] == NULL) {
            fprintf(stderr, "ERRO | Falha ao alocar as colunas.\n");

            // Libera a memória antes de encerrar
            for (int x = linhas - 1; x >= 0; x--) {
                free(matriz[x]);
            }
            free(matriz);

            // Encerra o programa
            exit(EXIT_FAILURE);
        }
    }

    // Retorna a matriz
    return matriz;
}
```

**Analisando o código acima:**

1. Primeiramente, foi criada a função `linhasColunasMatriz()` que aloca dinamicamente uma matriz dinâmica. Essa função têm `linhas` e `colunas` como parâmetros, o que significa que em diferentes execuções a matriz poderá ter diferentes tamanhos.

1. Dentro da função `linhasColunasMatriz()`, é feita a alocação de uma matriz de tamanho personalizado utilizando a função `calloc()`.

1. O ponteiro `**matriz` é um ponteiro para ponteiros, o que significa que seus valores também são ponteiros, e por isso há `**`.

1. Em caso de erro na alocação das linhas da matriz, é feita a liberação da mesma. Primeiro são liberadas linha por linha, e em seguida a matriz inteira. Basicamente, a liberação deve ser feita em ordem inversa de alocação.

1. Em seguida, é feita a alocação das colunas da matriz utilizando um loop `for`, que aloca dinamicamente cada coluna da matriz. Perceba que essa alocação é feita dentro do ponteiro da matriz, ou seja, é um ponteiro do array que também é um ponteiro.

1. Novamente é feita a liberação de memória em caso de erro ao alocar a memória. É feita da mesma maneira que para as linhas.

1. Ao final, é retornado a matriz, que é um ponteiro para ponteiros. Os ponteiros internos representam as colunas, e o ponteiro externo representa as linhas.

###### Atribuindo Valores à Matriz

Utilizando o mesmo código anterior, podemos atribuir os valores a uma matriz com um loop `for` que percorrerá sobre as linhas, e um loop `for` interno que percorrerá sobre as colunas.

``` c
// Recebe um valor inteiro do usuário
int inputValor(char msg[]) {
    int userInt;
    while (true) {
        // Imprime a mensagem de input
        printf("%s", msg);

        // Captura a entrada do usuário
        if (scanf("%d", &userInt)) {
            return userInt;
        } else {
            fprintf(stderr, "ERRO | Valor digitado deve ser um número inteiro.\n");
        }

        // Limpa o buffer do teclado
        int c;
        while (c = getchar() != '\n' && c != EOF);
    }
}

// Atribui os valores à matriz
void definirValores(int **matriz, int linhas, int colunas) {
    int userNum;
    char msg[50];
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            sprintf(msg, "Valor %dx%d: ", i + 1, j + 1);
            userNum = inputValor(msg);
            matriz[i][j] = userNum;
        }
    }
}
```

**Analise do código acima:**

1. Há a função `inputValor()`, que possui o objetivo de capturar a entrada de um número inteiro do usuário.

1. A função `definirValores()` tem o objetivo de definir valores inteiros a cada posição na matriz. Ela recebe como argumentos a matriz que será preenchida, e a quantidade de linhas e colunas da matriz.

1. Dentro da função `definirValores()` há dois loops `for`, um percorre sobre as linhas e o outro sobre as colunas. Dentro do loop mais interno são feitas as atribuições dos valores que o usuário digitar utilizando os índices das respectivas posições da matriz.

**Exemplo de uso:**

``` c
// Crie uma matriz bidimensional dinamicamente. Permita que o usuário especifique o número de linhas e colunas. Preencha a matriz com dados e exiba-a.

#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

// Limpa o buffer do teclado
void limparBuffer() {
    int c;
    while (c = getchar() != '\n' && c != EOF);
}

// Pede quantidade de linhas/colunas ao usuário
int inputIJ(char msg[]) {
    int userInt;
    while (true) {
        // Imprime a mensagem de input
        printf("%s", msg);

        // Captura entrada do usuário
        if (scanf("%d", &userInt) && userInt > 0 && userInt <= 5) { // Caso o valor passado seja um inteiro
            return userInt;
        } else { // Caso o valor passado seja inválido
            fprintf(stderr, "ERRO | Valor digitado deve ser um número inteiro maior que 0 e menor ou igual a 5.\n");
        }

        // Limpa o buffer do teclado
        limparBuffer();
    }
}

// Recebe um valor inteiro do usuário
int inputValor(char msg[]) {
    int userInt;
    while (true) {
        // Imprime a mensagem de input
        printf("%s", msg);

        // Captura a entrada do usuário
        if (scanf("%d", &userInt)) {
            return userInt;
        } else {
            fprintf(stderr, "ERRO | Valor digitado deve ser um número inteiro.\n");
        }

        // Limpa o buffer do teclado
        limparBuffer();
    }
}

// Libera a memória da matriz
void liberarMemoria(int **matriz, int linhas) {
    for (int x = linhas - 1; x >= 0; x--) {
        free(matriz[x]);
    }
    free(matriz);
}

// Aloca dinamicamente as linhas e as colunas de uma matriz
int **linhasColunasMatriz(int linhas, int colunas) {
    // Aloca dinamicamente as linhas da matriz
    int **matriz = (int**)calloc(linhas, sizeof(int*));

    // Verifica se a alocação das linhas foi bem-sucedida
    if (matriz == NULL) {
        fprintf(stderr, "ERRO | Falha ao alocar as linhas.\n");

        // Libera a memória antes encerrar
        liberarMemoria(matriz, linhas);

        // Encerra o programa
        exit(EXIT_FAILURE);
    }

    // Aloca dinamicamente as colunas da matriz
    for (int j = 0; j < linhas; j++) {
        matriz[j] = (int*)calloc(colunas, sizeof(int*));

        // Verifica se a alocação das colunas foi bem-sucedida
        if (matriz[j] == NULL) {
            fprintf(stderr, "ERRO | Falha ao alocar as colunas.\n");

            // Libera a memória antes de encerrar
            liberarMemoria(matriz, linhas);

            // Encerra o programa
            exit(EXIT_FAILURE);
        }
    }

    // Retorna a matriz
    return matriz;
}

// Atribui os valores à matriz
void definirValores(int **matriz, int linhas, int colunas) {
    int userNum;
    char msg[50];
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            sprintf(msg, "Valor %dx%d: ", i + 1, j + 1);
            userNum = inputValor(msg);
            matriz[i][j] = userNum;
        }
    }
}

// Imprime a matriz
void mostrarMatriz(int **matriz, int linhas, int colunas) {
    for (int i = 0; i < linhas; i++) {
        printf("|\t");
        for (int j = 0; j < colunas; j++) {
            printf("%d\t", matriz[i][j]);
            if (j == colunas - 1) {
                printf("|\n");
            }
        }
    }
}

int main() {
    // Input de linhas e colunas da matriz
    int linhas = inputIJ("Digite o número de linhas da matriz: ");
    int colunas = inputIJ("Digite o número de colunas da matriz: ");

    // Aloca dinamicamente a matriz
    int **matriz = linhasColunasMatriz(linhas, colunas);

    // Atribui os valores à matriz
    definirValores(matriz, linhas, colunas);

    // Imprime a matriz
    mostrarMatriz(matriz, linhas, colunas);

    // Libera a memória
    liberarMemoria(matriz, linhas);

    return 0;
}
```

O código acima possui algumas funções adicionais, como `mostrarMatriz()` e `liberarMemoria()`, ambas com nomes auto-explicativos.

> **NOTA:** Ao terminar de usar a matriz, lembre-se de liberar a memória da mesma maneira vista no código acima.

### Vazamento de Memória

Vazamento de memória, ou "memory leaks", é um problema em programas onde a aplicação falha em liberar corretamente a memória que não está mais em uso, o que gera aumento no consumo de memória ao longo do tempo, levando a problemas de desempenho e, eventualmente, a falhas no sistema.

Em C, vazamentos de memória são comuns devido à natureza manual do gerenciamento de memória.

## Classes de Armazenamento

Refere-se a características associadas às variáveis em termos de alocação de memória e escopo. Existem quatro classes de armazenamento principais:

* Automática
* Estática
* Externa
* Registradora

### Automática (auto)

Variáveis automáticas são aquelas cuja vida útil está limitada ao escopo em que são declaradas. Essas variáveis são destruídas assim que o bloco no qual elas foram declaradas for concluído.

Essas variáveis são armazenadas na pilha de execução do programa.

A única coisa necessário para que uma variável seja automática, é que ela seja declarada dentro de um bloco.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    int x = 5; // Variável automática

    return 0;
}

```

### Estática (static)

São declaradas usando a palavra-chave **`static`**, e podem ser usadas em dois contextos principais: dentro de uma função e fora de qualquer função (escopo global).

#### Variáveis Estáticas em Funções

Dentro de uma função, uma variável estática mantém seu valor entre chamadas da função. Isso significa que a variável não é destruída ao fim da função, para que assim, na próxima chamada da função, ela possuir ainda o mesmo valor.

**Exemplo:**

``` c
#include <stdio.h>

void myFunction() {
    static int contador = 0;
    contador++;
    printf("Contador: %d\n", contador);
}

int main() {
    myFunction(); // Output: Contador: 1
    myFunction(); // Output: Contador: 2
    myFunction(); // Output: Contador: 3

    return 0;
}
```

> **OBS.:** É uma boa prática inicializar variáveis estáticas ao declará-las. Em funções, a inicialização ocorre apenas na primeira chamada da função e persiste nas chamadas subsequentes.

#### Variáveis Estáticas No Escopo Global

Equivalem a variáveis comuns, podendo ser acessadas em qualquer lugar dentro do arquivo em que foram declaradas.

**Exemplo:**

``` c
#include <stdio.h>

static int contador = 0;

void add() {
    contador++;
    printf("Contador: %d\n", contador);
}

int main() {
    add(); // Output: Contador: 1
    add(); // Output: Contador: 2
    add(); // Output: Contador: 3

    return 0;
}
```

**Seria o mesmo que:**

``` c
#include <stdio.h>

int contador = 0;

void add() {
    contador++;
    printf("Contador: %d\n", contador);
}

int main() {
    add(); // Output: Contador: 1
    add(); // Output: Contador: 2
    add(); // Output: Contador: 3

    return 0;
}
```

### Externa (extern)

Variáveis externas são usadas para compartilhar variáveis entre diferentes arquivos de código-fonte. Elas permitem que uma variável declarada em um arquivo seja acessada em outros arquivos.

São declaradas a partir da palavra-chave **`extern`**.

**Exemplo:**

``` c
// arquivo1.c
#include <stdio.h>

int x = 20;
```

``` c
// arquivo2.c
#include <stdio.h>

extern int x;

int main() {
    printf("Variável externa: %d\n", x);
    // Output: Variável externa: 20

    return 0;
}
```

Em resumo, a palavra-chave `extern` diz ao compilador que a variável existe em algum lugar, mas não necessariamente no mesmo arquivo. Assim, quando dois ou mais arquivos são compilados ao mesmo tempo, as variáveis `extern` são usadas para acessar as variáveis com o mesmo nome declaradas em outros arquivos.

### Registradora (register)

Ao declarar uma variável com **`register`**, sugere-se ao compilador que a aloque em um registrador na CPU, se possível.

Essa sugestão pode resultar em um desempenho aprimorado, no entanto, os compiladores modernos geralmente ignoram essa recomendação, pois são altamente eficientes em determinar quais variáveis devem ser armazenadas em registradores.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    register int x; // Sugestão para alocar x em um registrador

    return 0;
}
```

Devido à eficiência dos compiladores modernos na otimização de código, o uso de `register` perdeu sua relevância e pode ser considerado obsoleto na maioria dos casos.

## Estruturas

Estruturas possibilitam agrupar diversas variáveis relacionadas em um único lugar.

Estruturas permitem diferentes tipos de valores, ao contrário de arrays.

Uma estrutura pode ser criada com a palavra-chave **`struct`**, e as variáveis que compõem estruturas são chamadas de **membros**.

**Exemplo:**

``` c
struct MyStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};
```

> Estruturas devem ser finalizadas com ponto e vírgula.

Para acessar uma estrutura, é necessário criar uma variável para ela.

``` c
#include <stdio.h>

struct MyStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};

int main() {
    struct MyStructure structure1;
    return 0;
}
```

E para acessar os membros dessa estrutura, é usado a sintaxe de ponto '`.`'.

``` c
#include <stdio.h>

// Cria a estrutura `MyStructure`
struct MyStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct MyStructure structure1;

    // Atribuição de valores aos membros de `structure1`
    structure1.num1 = 13;
    structure1.num2 = 2.2;
    structure1.letter = 'C';

    // Impressão de valores
    printf("Inteiro: %d\n", structure1.num1);
    printf("Flutuante: %f\n", structure1.num2);
    printf("Letra: %c\n", structure1.letter);

    /* Output:
    Inteiro: 13
    Flutuante: 2.200000
    Letra: C
    */

    return 0;
}
```

### Arrays em Estruturas

É possível atribuir um array como membro de uma estrutura.

**Sintaxe:**

``` c
struct NomeEstrutura {
    tipoArray nomeArray[5];
};
```

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

// Estrutura
struct Numeros {
    int inteiros[5];
};

int main() {
    // Variável de estrutura
    size_t numeroDeElementos = 5;
    struct Numeros valores;

    // Definindo os elementos do array dentro da estrutura
    size_t i;
    for (i = 0; i < numeroDeElementos; i++) {
        valores.inteiros[i] = i + 1;
    }

    // Imprime o array
    printf("{ ");
    for (i = 0; i < numeroDeElementos; i++) {
        printf("%d", valores.inteiros[i]);
        if (i != numeroDeElementos - 1) {
            printf(", ");
        }
    }
    printf(" }\n");

    // Output: { 1, 2, 3, 4, 5 }

    return 0;
}
```

### Strings em Estruturas

Não é possível atribuir uma string a um membro da mesma maneira que outros tipos de dados. Então para isso, é necessário usar a função **`strcpy()`** da biblioteca padrão `string.h`.

``` c
#include <stdio.h>
#include <string.h>

// Cria a estrutura `MyStructure`
struct MyStructure {
    char myStr[20];
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct MyStructure structure1;

    // Atribuição de string ao membro `myStr`
    strcpy(structure1.myStr, "Hello, World!");

    // Imprime o membro `myStr`.
    printf("%s", structure1.myStr); // Output: Hello, World!

    return 0;
}
```

### Atribuição Múltipla

É possível atribuir valores aos membros em uma única linha utilizando chaves '`{}`' e separando os valores com vírgula.

``` c
#include <stdio.h>

// Cria a estrutura `MyStructure`
struct MyStructure {
    int myInt;
    float myFloat;
    char myStr[20];
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct MyStructure structure1 = { 13, 2.2, "Hello, World!" };

    // Impressão de valores.
    printf("%d\n", structure1.myInt);   // Output: 13
    printf("%f\n", structure1.myFloat); // Output: 2.200000
    printf("%s\n", structure1.myStr);   // Output: Hello, World!

    return 0;
}
```

> Atribuir valores aos membros desta maneira, torna desnecessário usar a função `strcpy()` para atribuir valores à membros strings.

#### Inicialização com Designadores

Os valores são atribuídos aos membros da estrutura no momento de declaração da variável da estrutura utilizando `{}` e `.`.

**Exemplo:**

``` c
#include <stdio.h>

// Estrutura
struct Estrutura {
    int x;
    int y;
};

int main() {
    struct Estrutura estrutura = { .y = 5, .x = 2 };

    return 0;
}
```

Dessa maneira, é possível definir os valores dos membros em uma ordem diferente das quais eles estão declarados.

### Tamanho de Estruturas

Com o operador `sizeof`, é possível ver a quantidade de bytes que uma estrutura ou instância de estrutura possui.

``` c
#include <stdio.h>

struct MyStructure {
    int myInt;
    char myLetter;
    char myStr[20];
};

int main() {
    size_t size = sizeof(struct MyStructure);
    printf("Tamaho da estrutura: %zu bytes\n", size);
    // Output: 28 bytes

    return 0;
}
```

### Estruturas Aninhadas

Aninhar estruturas permite criar tipos de dados mais complexos.

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

// Estrutura interna
struct Data {
    int dia;
    int mes;
    int ano;
};

// Estrutura externa
struct Pessoa {
    char nome[50];
    int idade;
    struct Data dataNascimento;
};

int main() {
    // Variável para `Pessoa`
    struct Pessoa pessoa1;

    // Atribuindo valores aos membros de `pessoa1`
    strcpy(pessoa1.nome, "Lucas");
    pessoa1.idade = 22;
    pessoa1.dataNascimento.dia = 6;
    pessoa1.dataNascimento.mes = 12;
    pessoa1.dataNascimento.ano = 2001;

    // Mostrando informações
    printf("Nome: %s\n", pessoa1.nome);
    printf("Idade: %d\n", pessoa1. idade);
    printf("Data de Nascimento: %d/%d/%d\n", pessoa1.dataNascimento.dia, pessoa1.dataNascimento.mes, pessoa1.dataNascimento.ano);

    /* Output:
    Nome: Lucas
    Idade: 22
    Data de Nascimento: 6/12/2001
    */

    return 0;
}
```

No exemplo acima, a estrutura `Pessoa` possui como membro a estrutura `Data`.

#### Atribuição de Estruturas Aninhadas

Para atribuir valores aos membros de estruturas aninhadas, pode-se usar **`{}`**. Seus membros podem ser definidos com ou sem designadores.

**Exemplo:**

``` c
#include <stdio.h>

// Estrutura
struct Estrutura {
    int x;
    int y;
};

// Estrutura Externa
struct EstruturaExterna {
    struct Estrutura primeiraEstrutura;
    struct Estrutura segundaEstrutura;
};

int main() {
    struct EstruturaExterna estrututura = {
        .primeiraEstrutura = { .x = 5, .y = 3 },
        .segundaEstrutura = { .x = 10, .y = 15 }
    };

    return 0;
}
```

### Estruturas Dentro de Arrays

É possível armazenar estruturas dentro de um array. Para isso, é necessário especificar o tipo do array como o mesmo da estrutura.

**Sintaxe:**

``` c
struct Estrutura arrayDeEstruturas[numeroDeEstruturas];
```

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

// Estrutura
struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    // Array de estruturas
    size_t numPessoas = 3; // Número de pessoas que o array armazenará
    struct Pessoa pessoas[numPessoas];

    // Definindo elementos do array
    strcpy(pessoas[0].nome, "Lucas");
    pessoas[0].idade = 23;

    strcpy(pessoas[1].nome, "Maria");
    pessoas[1].idade = 18;

    strcpy(pessoas[2].nome, "Luana");
    pessoas[2].idade = 31;

    // Imprime os valores
    size_t i;
    for (i = 0; i < numPessoas; i++) {
        printf("\nNome: %s\n", pessoas[i].nome);
        printf("Idade: %d\n", pessoas[i].idade);
    }

    /* Output:
    Nome: Lucas
    Idade: 23

    Nome: Maria
    Idade: 18

    Nome: Luana
    Idade: 31
    */

    return 0;
}
```

### Ponteiro para Estruturas

Permitem manipular dados de estruturas de forma dinâmica e eficiente.

**Sintaxe:**

``` c
struct Estrutura *ponteiroEstrutura;
```

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>

// Estrutura
struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    // Declaração de variável de estrutura e ponteiro
    struct Pessoa pessoa1;
    struct Pessoa *ptrPessoa;

    // Inicializando o ponteiro
    ptrPessoa = &pessoa1; // Ponteiro aponta para `pessoa1`

    // Acesso aos membros da estrutura pelo ponteiro
    strcpy(ptrPessoa->nome, "Lucas");
    ptrPessoa->idade = 23;

    // Imprime os dados
    printf("\nNome: %s\n", ptrPessoa->nome);
    printf("Idade: %d\n", ptrPessoa->idade);

    /* Output:
    Nome: Lucas
    Idade: 23
    */

    return 0;
}
```

Ao invés de notação de ponto, é utilizado **`->`** para acessar os membros de uma estrutura a partir de um ponteiro.

### Alocação Dinâmica de Estruturas

**Sintaxe:**

``` c
struct Estrutura *ptrEstrutura = (struct Estrutura*)malloc(sizeof(struct Estrutura));
```

**Exemplo:**

``` c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// Estrutura
struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    // Aloca dinamicamente um espaço para uma estrutura
    struct Pessoa *pessoa1 = (struct Pessoa*)malloc(sizeof(struct Pessoa));

    // Verifica se a alocação foi bem-sucedida
    if (pessoa1 == NULL) {
        fprintf(stderr, "Falha na alocação de memória.\n");
        exit(EXIT_FAILURE);
    }

    // Define os valores dos membros da estrutura
    strcpy(pessoa1->nome, "Lucas");
    pessoa1->idade = 23;

    // Imprime os valores dos membros da estrutura
    printf("Nome: %s\n", pessoa1->nome);
    printf("Idade: %d\n", pessoa1->idade);

    // Libera a memória alocada
    free(pessoa1);

    /* Output:
    Nome: Lucas
    Idade: 23
    */

    return 0;
}
```

### Estruturas e Funções

É possível passar estruturas como argumentos de funções.

**Exemplo:**

``` c
#include <stdio.h>

// Definição da estrutura (com alias)
struct MyStructure {
    int x;
    int y;
};

// Função que soma os membros da estrutura
void somaMembros(struct MyStructure s) {
    printf("A soma entre %d e %d é %d\n", s.x, s.y, s.x + s.y);
}

int main() {
    // Variável para a estrutura
    struct MyStructure structure1;

    // Define os valores da variável da estrutura
    structure1.x = 2;
    structure1.y = 5;

    // Imprime a estrutura
    somaMembros(structure1);
    // Output: A soma entre 2 e 5 é 7

    return 0;
}
```

Uma função que recebe uma estrutura como argumento pode acessar e manipular os valores dessa estrutura. No exemplo acima, a função `somaMembros()` imprime a soma entre os membros da estrutura.

#### Ponteiros para Funções como Membros

É possível ter ponteiros para funções como membros de estruturas. Isso pode ser útil em situações em que se deseja armazenar referências para diferentes funções em uma estrutura e, posteriormente, chamar essas funções dinamicamente.

**Exemplo:**

``` c
#include <stdio.h>

// Tipo de função que recebe dois inteiros e retorna um inteiro

typedef int (*Operacao)(int, int);

// Estrutura que contém um ponteiro para uma função
struct Calculadora {
    Operacao somar;
};

// Função de soma
int soma(int x, int y) {
    return x + y;
}

int main() {
    // Instância de estrutura
    struct Calculadora calc;

    // Inicializando ponteiro para a função
    calc.somar = soma;

    // Chamando o ponteiro para chamar a função
    int resultado = calc.somar(5, 2);

    // Imprime o resultado
    printf("Resultado: %d\n", resultado);
    // Output: Resultado: 7

    return 0;
}
```

No exemplo acima, a estrutura `Calculadora` contém um ponteiro para a função `somar`. Esse ponteiro é inicializado e em seguida, é possível usar esse ponteiro para chamar a função associada.

### Listas Encadeadas

São estruturas de dados no qual os elementos de dados, chamados de **nós**, estão ligados uns aos outros por meio de ponteiros.

Cada nó contém um dado e um ponteiro que aponta para o próximo nó na sequência. A última célula geralmente tem um ponteiro nulo para indicar o final da lista.

**Sintaxe:**

``` c
struct Node {
    int data;           // Dado armazenado pelo nó
    struct Node* next;  // Ponteiro para o próximo nó
}
```

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>

// Estrutura de nó
struct Node {
    int data;
    struct Node* next;
};

// Função que imprime os elementos da lista encadeada
void printList(struct Node* head) {
    while (head != NULL) {
        printf("Valor %d\n", head->data); // Imprime o dado do nó
        head = head->next; // Torna `head` o próximo nó
    }
}

int main() {
    // Criando três nós
    struct Node* first = malloc(sizeof(struct Node));
    struct Node* second = malloc(sizeof(struct Node));
    struct Node* third = malloc(sizeof(struct Node));

    // Atribuindo valores aos nós
    first->data = 1;
    first->next = second; // Faz com que o próximo nó seja `second`

    second->data = 2;
    second->next = third; // Faz com que o próximo nó seja `third`

    third->data = 3;
    third->next = NULL; // Último nó deve apontar para NULL

    // Imprime a lista encadeada
    printList(first);

    // Libera a memória alocada
    free(first);
    free(second);
    free(third);

    /* Output:
    Valor 1
    Valor 2
    Valor 3
    */

    return 0;
}
```

> **LEMBRE-SE.:** A memória dos nós deve ser liberada quando os mesmos não forem mais necessários.

#### Referência Circular

Se refere a uma situação onde os nós nunca chegam no fim, fazendo com que eles se referenciem infinitamente, podendo levar a problemas como vazamento de memória se não gerenciado adequedamente.

**Exemplo:**

``` c
#include <stdio.h>
#include <stdlib.h>

// Estrutura de nó
struct Node {
    int data;
    struct Node* next;
};

int main() {
    // Criando três nós
    struct Node* first = malloc(sizeof(struct Node));
    struct Node* second = malloc(sizeof(struct Node));
    struct Node* third = malloc(sizeof(struct Node));

    // Atribuindo valores aos nós
    first->data = 1;
    first->next = second;

    second->data = 2;
    second->next = third;

    third->data = 3;
    third->next = first; // O próximo será o primeiro novamente

    // Libera a memória alocada
    free(first);
    free(second);
    free(third);

    return 0;
}
```

No exemplo acima, não há fim na referência, é retornado ao início sempre que chega ao fim.

Para evitar problemas, é fundamental indicar `NULL` para a próxima referência de um nó considerado o último.

``` c
#include <stdio.h>
#include <stdlib.h>

// Estrutura de nó
struct Node {
    int data;
    struct Node* next;
};

int main() {
    // Criando três nós
    struct Node* first = malloc(sizeof(struct Node));
    struct Node* second = malloc(sizeof(struct Node));
    struct Node* third = malloc(sizeof(struct Node));

    // Atribuindo valores aos nós
    first->data = 1;
    first->next = second;

    second->data = 2;
    second->next = third;

    third->data = 3;
    third->next = NULL; // Último nó

    // Libera a memória alocada
    free(first);
    free(second);
    free(third);

    return 0;
}
```

### Membros Bitfields

Membros bitfields permitem especificar o número exato de bits que eles vão ocupar na memória.

Para definí-los, basta que ao fim da declaração do membro você especifique o número de bits após **`:`**;

**Exemplo:**

``` c
struct Flags {
    unsigned int flag1 : 1;
    unsigned int flag2 : 2;
    unsigned int flag3 : 3;
};
```

No exemplo acima, `flag1` ocupa 1 bit, `flag2` ocupa 2 bits e `flag3` ocupa 3 bits.

## Enums

Um **enum** é um tipo especial que representa um grupo de constantes.

Enums são criados a partir da palavra-chave `enum`, seguido do nome do enum. Cada item dentro do enum é chamado de **membro**, e esses membros são separados por vírgula.

**Exemplo:**

``` c
enum DiasDaSemana {
    DOMINGO,
    SEGUNDA,
    TERCA,
    QUARTA,
    QUINTA,
    SEXTA,
    SABADO
};
```

> Enums devem ser terminados com ponto e vírgula.

Para acessar um enum, é necessário criar uma variável para ele de maneira semelhante à estruturas.

``` c
#include <stdio.h>

enum DiasDaSemana {
    DOMINGO,
    SEGUNDA,
    TERCA,
    QUARTA,
    QUINTA,
    SEXTA,
    SABADO
};

int main() {
    enum DiasDaSemana myVar;

    return 0;
}
```

Deve ser atribuído um dos membros do enum para a variável:

``` c
#include <stdio.h>

enum DiasDaSemana {
    DOMINGO,
    SEGUNDA,
    TERCA,
    QUARTA,
    QUINTA,
    SEXTA,
    SABADO
};

int main() {
    enum DiasDaSemana myVar = DOMINGO;

    printf("%d", myVar); // Output: 0

    return 0;
}
```

No exemplo acima, a saído é `0` porque `DOMINGO` é o primeiro membro de `DiasDaSemana`, logo, `SEGUNDA` é `1`, `TERCA` é `2` e assim por diante.

Atribuir valores aos membros assim que criar o enum é possível:

``` c
#include <stdio.h>

enum DiasDaSemana {
    DOMINGO = 2,
    SEGUNDA = 4,
    TERCA = 6,
    QUARTA = 8,
    QUINTA = 10,
    SEXTA = 12,
    SABADO = 14
};

int main() {
    enum DiasDaSemana myVar = DOMINGO;

    printf("%d", myVar); // Output: 2

    return 0;
}
```

Alterar o valor apenas do primeiro, irá fazer com que os próximo se alterem automaticamente.

``` c
enum DiasDaSemana {
    DOMINGO = 1,
    SEGUNDA,    // será 2
    TERCA,      // será 3
    QUARTA,     // será 4
    QUINTA,     // será 5
    SEXTA,      // será 6
    SABADO      // será 7
};
```

## Palavra-chave `typedef`

A palavra-chave **`typedef`** é usada para criar um alias de um tipo de dado.

> Um alias é um nome altenativo para identificar ou se referir ao mesmo objeto de dados.

Frequentemente, são usados para criar nomes alternativos para tipos de dados existentes, o que torna o código mais legível e com mais abstração. Além disso, pode ser útil para manutenção futura caso haja necessidade de alterar vários dados do mesmo tipo.

**Sintaxe:**

``` c
typedef tipo_original novo_nome;
```

**Exemplo:**

``` c
#include <stdio.h>

// Alias para o tipo `int`
typedef int Inteiro;

int main() {
    // Declarando dois números inteiros
    Inteiro numero1 = 13;
    Inteiro numero2 = 22;

    // Imprimindo os valores
    printf("Número 1: %d\n", numero1); // Output: Número 13
    printf("Número 2: %d\n", numero2); // Output: Número 22

    return 0;
}
```

No exemploa acima, `Inteiro` é um alias para o tipo `int`.

### Estruturas e `typedef`

Frequentemente é utilizado `typedef` junto a estruturas para criar nomes mais legíveis e expressivos para tipos de dados complexos.

**Sintaxe:**

``` c
typedef struct {
    // membros da estrutura
    tipo1 nome1;
    tipo2 nome2;
    // ...
} NomeDaEstruturaAlias;
```

**Exemplo:**

``` c
#include <stdio.h>

// Definição da estrutura (com alias)
typedef struct {
    int x;
    int y;
} MyStructure;

int main() {
    // Variável para a estrutura
    MyStructure structure1;

    // Define os valores da variável da estrutura
    structure1.x = 2;
    structure1.y = 5;

    // Imprime a estrutura
    printf("A soma entre %d e %d é %d\n", structure1.x, structure1.y, structure1.x + structure1.y);
    // Output: A soma entre 2 e 5 é 7

    return 0;
}
```

No exemplo acima, `MyStructure` é um alias para a estrutura que possui os membros `x` e `y`. Perceba que ao declarar uma variável de estrutura, não é necessário indicar `struct` ao início.

## Uniões

Permitem armazenar vários dados de diferentes tipos em uma única estrutura, bem parecido com `struct`s, porém, cada membro de uma união tem seu próprio espaço. Em uma união, todos os membros compartilham o mesmo espaço de memória.

**Sintaxe:**

``` c
union NomeUniao {
    tipo membro1;
    tipo membro2;
    // ...
}
```

O tamanho de uma união é igual ao tamanho do maior membro presente nela.

**Exemplo:**

``` c
#include <stdio.h>

union MyUnion {
    int intNum;
    float floatNum;
    char caractere;
};

int main() {
    // Cria uma instância da união
    union MyUnion uniao;

    // Atribui e imprime os valores da união
    uniao.intNum = 5;
    printf("Inteiro: %d\n", uniao.intNum);
    // Inteiro: 5

    uniao.floatNum = 10.2;
    printf("Float: %.1f\n", uniao.floatNum);
    // Float: 10.2

    uniao.caractere = 'C';
    printf("Char: %c\n", uniao.caractere);
    // Char: C

    return 0;
}
```

Todos os membros compartilham o mesmo espaço de memória, e a alteração de um membro pode afetar o valor dos outros membros. Por isso, é preciso ter cuidado ao usar uniões para garantir que os valores sejam interpretados corretamente.

## Macros

Macros são pedaços de código que são substituídos pelo pré-processador antes da compilação.

São criados a partir da palavra-chave **`#define`**.

**Sintaxe Básica:**

``` c
#define NOME_MACRO valor
```

**Exemplo:**

``` c
#include <stdio.h>

#define PI 3.14159

int main() {
    printf("PI = %.2f\n", PI);
    // Output: PI = 3.14

    return 0;
}
```

No exemplo acima, a macro `PI` simboliza uma constante, e seria o mesmo que `const PI = 3.14159;`.

### Macros como Funções

Macros podem ser usadas para criar atalhos para blocos de código, funcionando como funções inline.

**Exemplo:**

``` c
#include <stdio.h>

#define SOMA(x, y) ((x) + (y))

int main() {
    int resultado = SOMA(5, 2);
    printf("Resultado: %d\n", resultado);
    // Output: Resultado: 7

    return 0;
}
```

No exemplo acima, a macro `SOMA` age como uma função que recebe dois argumentos e retorna a soma entre eles.

### Boas Práticas e Precauções para Macros

* Use parênteses em torno dos argumentos para evitar problemas com precedência de operadores.

* O uso excessivo de macros pode tornar o código menos legível.

* Macros não têm conhecimento de escopo. Eles são substituídos globalmente no arquivo.

* Macros não têm checagem de tipo, podendo a levar a erros difícieis de diagnosticar.

### Desfazer Definição de Macro

A diretiva **`undef`** é usada para desfazer a definição de uma macro.

**Sintaxe:**

``` c
#undef MACRO
```

**Exemplo:**

``` c
#include <stdio.h>

#define VALOR 5

int main() {
    printf("Macro: %d\n", VALOR);
    // Output: Macro: 5

    #undef VALOR

    // A partir daqui, `VALOR` não é mais uma macro

    return 0;
}
```

### Inclusão Condicional com Macros

Permitem condicionar a compilação de partes do código fonte com base em expressões ou definições específicas. São usados **`#ifdef`**, **`ifndef`**, **`#else`** e **`endif`**.

* **'`#ifdef`'**: O bloco entre `ifdef` e `endif` é incluído na compilação apenas se a macro passada como condição estiver definida, caso contrário, o bloco é ignorado.

    ``` c
    #include <stdio.h>

    #define MACRO

    int main() {
        #ifdef MACRO
            printf("Macro definida.\n");
        #else
            printf("Macro não definida.\n");
        #endif
            printf("Código padrão.\n");

        return 0;
    }

    /* Output:
    Macro definida.
    Código padrão.
    */
    ```

* **'`ifndef`'**: É o oposto de `ifdef`, incluindo seu código na compilação apenas se a macro passado não estiver definida.

    ``` c
    #include <stdio.h>

    #define MACRO

    int main() {
        #ifndef MACRO
            printf("Macro definida.\n");
        #else
            printf("Macro não definida.\n");
        #endif
            printf("Código padrão.\n");

        return 0;
    }

    /* Output:
    Macro não definida.
    Código padrão.
    */
    ```

* **'`#else`'**: O bloco desta diretiva é compilado apenas quando as diretivas acima desta não são compiladas.

* **'`#elif`'**: Exatamente como um `else if`, só que como uma diretiva.

    ``` c
    #include <stdio.h>

    #define MACRO 2

    int main() {
        #if MACRO == 1
            printf("Macro definida como 1.\n");
        #elif MACRO == 2
            printf("Macro definida como 2.\n");
        #elif MACRO == 3
            printf("Macro definida como 3.\n");
        #else
            printf("Macro diferente de 1, 2 e 3, ou não definida.\n");
        #endif
            printf("Código padrão.\n");

        return 0;
    }

    /* Output:
    Macro definida como 2.
    Código padrão.
    */
    ```

* **'`#endif`'**: Como visto nas diretivas anteriores, encerra a estrura de condições.

### Diretiva `#pragma`

Fornece instruções específicas para o compilador, o linker ou outras ferramentas de construção durante a compilação do código. Essas diretivas são geralmente usadas para otimizações, controle de warning, alinhamento de memória e outras configurações específicas da implementação da plataforma.

**Sintaxe:**

``` c
#pragma diretiva
```

A diretiva pode variar de acordo com o compilador e a plataforma. As diretivas mais comuns são:

* **'`#pragma once`'**: Garante que um arquivo de cabeçalho seja incluído apenas uma vez durante a compilação, prevenindo inclusões duplicadas.

    ``` c
    #pragma once
    ```

* **'`#pragma warning`'**: Controla as mensagens de aviso geradas pelo compilador.

    ``` c
    #pragma warning(disable: codigo_de_aviso)
    ```

* **'`#pragma pack`'**: Controla o alinhamento de memória para estruturas.

    ``` c
    #pragma pack(n)
    // Define o alinhamento de memória para n bytes
    ```

* **'`#pragma comment`'**: Inclui informações adicionais no arquivo executável, como bibliotecas a serem vinculadas.

    ``` c
    #pragma comment(lib, "nome_biblioteca.lib")
    ```

* **'`#pragma optimize`'**: Controla o nível de otimização.

    ``` c
    #pragma optimize("02")
    ```

Por não se um padrão C, as diretivas `#pragma` podem variar entre compiladores.

O uso excessivo de `#pragma` pode tornar o código menos portátil entre diferentes ambientes de compilação.

## Arquivos

Para criar, abrir, ler ou escrever em arquivos, é necessário declarar um ponteiro do tipo **`FILE`** e usar a função `fopen()`.

``` c
FILE *ponteiro_arquivo;
ponteiro_arquivo = fopen(nome_arquivo, modo);
```

A função `open()` abre um arquivo, e recebe também como argumento o modo que define o propósito da abertura do arquivo (ler, adicionar ou ler o arquivo).

Os modos são:

* **'`w`'**: Escreve no arquivo.
* **'`a`'**: Adiciona um novo dado ao arquivo.
* **'`r`'**: Lê o arquivo.

**Exemplo:**

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;
    file_ptr = fopen("text.txt", "w"); // Cria um arquivo

    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

No exemplo acima, o arquivo `text.txt` é criado na mesma pasta que o script está rodando.

A função `fopen()` irá retornar `NULL` caso o arquivo não exista, e é uma boa prática criar uma condição para evitar erros.

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "r");
    if (file_ptr == NULL) {
        printf("Não foi possível abrir o arquivo.\n");
    }

    // Fecha o arquivo
    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

A função `fclose()` é usada para fechar o arquivo.

### Escrever em Arquivos

Para escrever em arquivos, é usado o modo **`w`**.

É usada a função `fprintf()` para escrever em arquivos:

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "w");

    // Escreve no arquivo
    fprintf(file_ptr, "Olá, Mundo!\n");

    // Fecha o arquivo
    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

No exemplo acima, foi escrito no arquivo `text.txt` a mensagem "Olá, Mundo!".

> Um arquivo se torna em branco sempre que é aberto com o modo `w`.

### Adicionar ao Arquivo

O modo **`a`** é usado para adicionar conteúdo ao fim do arquivo.

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "a");

    // Escreve no arquivo
    fprintf(file_ptr, "Olá, Mundo!\n");

    // Fecha o arquivo
    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

### Ler o Arquivo

O modo **`r`** é usado para ler arquivos.

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "r");

    // Fecha o arquivo
    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

Também é necessário criar uma string de largura suficiente para caber o conteúdo do arquivo.

Para atribuir o conteúdo à string criada, podemos usar a função `fgets()`, que recebe três argumentos.

1. Onde armazenar o conteúdo.
1. Tamanho máximo dos dados a serem lidos.
1. O ponteiro que vai ser usado para ler o arquivo.

**Exemplo:**

Arquivo de texto

``` txt
Olá, Mundo!
Olá, C!
```

Documento C

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "r");

    if (file_ptr == NULL) {
        printf("Não foi possível acessar o arquivo.\n")
    } else {
        // Armazena o conteúdo do arquivo
        char myString[100];
        fgets(myString, 100, file_ptr);

        // Imprime o conteúdo do arquivo
        printf("%s", myString); // Output: Olá, Mundo!

        // Fecha o arquivo
        fclose(file_ptr); // Fecha o arquivo
    }

    return 0;
}
```

No exemplo acima, o arquivo de texto possui duas linhas, uma com "Olá, Mundo!" e outra com "Olá, C!", e mesmo assim foi impresso somente "Olá, Mundo!", já que é a primeira linha. Para imprimir todas as linhas, podemos usar um loop `while`.

``` c
#include <stdio.h>

int main() {
    FILE *file_ptr;

    // Abre o arquivo
    file_ptr = fopen("text.txt", "r");

    if (file_ptr == NULL) {
        printf("Não foi possível acessar o arquivo.\n");
    } else {
        // Armazena o conteúdo do arquivo
        char myString[100];

        // Imprime o conteúdo do arquivo
        while (fgets(myString, 100, file_ptr)) {
            printf("%s", myString);
        }
        /* Output:
        Olá, Mundo!
        Olá, C!
        */
    }

    // Fecha o arquivo
    fclose(file_ptr); // Fecha o arquivo

    return 0;
}
```

## Bases Numéricas

Em C, as bases numéricas mais comuns são a decimal (base 10), a octal (base 8), a hexadecimal (base 16) e a base binária (base 2).

* **Decimal**: É o sistema numérico padrão, representados normalmente como no dia a dia.

    ``` c
    int decimal = 23;
    ```

* **Octal**: São representados com um zero à frente do número.

    ``` c
    int octal = 027; // 23 em decimal
    ```

* **Hexadecimal**: São representados com `0x` à frente do número.

    ``` c
    int hexadecimal = 0x17; // 23 em decimal
    ```

* **Binário**: Representado, geralmente, por `0b` à frente do número.

    ``` c
    int binario = 0b10111; // 23 em decimal
    ```

## Filas

Uma fila é uma estrutura de dados que segue o princípio FIFO (*First In*, *First Out*), ou "Primeira a entrar, primeiro a sair". Isso significa que o primeiro elemento adicionado à fila será o primeiro a ser removido.

Em C, a abordagem mais comum para implementar uma fila é utilizndo um array ou uma lista encadeada.

**Exemplo:**

``` c
#include <stdio.h>

#define MAX_ELEMENTOS 5

// Estrutura que representa uma fila
typedef struct {
    int elementos[MAX_ELEMENTOS];
    int frente; // Primeiro da fila
    int tras; // Último da fila
} Fila;

// Inicializa a fila
void inicializarFila(Fila *fila) {
    fila->frente = -1;
    fila->tras = -1;
}

// Verifica se a fila está cheia
int filaCheia(Fila *fila) {
    return ((fila->tras + 1) % MAX_ELEMENTOS == fila->frente);
}

// Veririca se a fila está vazia
int filaVazia(Fila *fila) {
    return (fila->frente == -1 && fila->tras == -1);
}

// Adiciona um elemento à fila
void adicionar(Fila *fila, int valor) {
    // Verifica se a fila está cheia
    if (filaCheia(fila)) {
        printf("Lista está cheia. Não é possível adicionar novos elementos.\n");
        return;
    }

    // Verifica se a fila está vazia
    if (filaVazia(fila)) {
        fila->frente = 0;
        fila->tras = 0;
    } else {
        fila->tras = (fila->tras + 1) % MAX_ELEMENTOS;
    }

    // Adiciona o valor à fila
    fila->elementos[fila->tras] = valor;
}

// Remove um elemento da lista
int remover(Fila *fila) {
    // Verifica se a lista está vazia
    if (filaVazia(fila)) {
        printf("Lista está vazia. Não é possível remover elementos.\n");
        return -1;
    }

    int valor = fila->elementos[fila->frente];

    if (fila->frente == fila->tras) {
        // Último elemento na fila
        inicializarFila(fila);
    } else {
        fila->frente = (fila->frente + 1) % MAX_ELEMENTOS;
    }

    return valor;
}

int main() {
    Fila minhaFila;
    inicializarFila(&minhaFila);

    adicionar(&minhaFila, 1);
    adicionar(&minhaFila, 2);
    adicionar(&minhaFila, 3);

    printf("Item removido: %d\n", remover(&minhaFila)); // Output: Item removido: 1
    printf("Item removido: %d\n", remover(&minhaFila)); // Output: Item removido: 2

    adicionar(&minhaFila, 4);

    printf("Item removido: %d\n", remover(&minhaFila)); // Output: Item removido: 3

    return 0;
}
```
