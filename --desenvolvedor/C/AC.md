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

## Strings

Para serem armazenadas em variáveis, essas variáveis devem ser `char`, e ao fim do identificador deve conter colchetes.

Exemplo:

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

Em C não existe o tipo de dado String. Strings em C são arrays, e por isso a maneira de declará-las como variáveis é a mesma (só que sem chaves e vários valores).

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

Ao fim, deve haver o elemento `\0` para determinar o fim da string.

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

Existe uma maneira ainda mais fácil, que é utilizando a função `strlen()`, mas primeiro, é necessário importar **`<string.h>`**.

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

### Strings Para Maiúsculo ou Minúsculo

A função **`toupper()`** e **`tolower()`** são da biblioteca padrão **`ctype.h`** e convertem um caractere para maiúsculo e minúsculo, respectivamente.

Exemplo com `toupper()`

``` c
#include <stdio.h>
#include <ctype.h>

int main() {
    char myChar = 'a';
    myChar = toupper(myChar);
    printf("%c", myChar); // Output: A
}
```

Exemplo com `tolower()`

``` c
#include <stdio.h>
#include <ctype.h>

int main() {
    char myChar = 'A';
    myChar = tolower(myChar);
    printf("%c", myChar); // Output: a
}
```

Para converter uma string inteiro, será necessário criar um loop que passa por toda a string, e assim, converter caractere por caractere.

``` c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void converterParaMinusculo(char str[]);

int main() {
    char myStr[15] = "Hello, World!";
    converterParaMinusculo(myStr);
    printf("%s", myStr); // Output: hello, world!
}

void converterParaMinusculo(char str[]) {
    for (int i = 0; i < strlen(str); i++) {
        str[i] = tolower((unsigned char)str[i]);
    }
}
```

No exemplo acima:

1. A função `converterParaMinusculo()` recebe uma string que será convertida em letras minúsculas.

1. Há um loop `for` que percorre a string passada.

1. Dentro do loop, é atribuído os caracteres minúsculos à string (substituindo a string original).

1. `(unsigned char)` é útil para que a função `tolower()` funcione corretamente.

Se o objetivo for converter a string para maiúculo, é só substituir a função `tolower()` por `toupper()`.

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
1. Tamanho da variável que vai receber o input (sizeof(var_name)).
1. Palavra `stdin`.

Exemplo:

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

> É uma boa prática indicar o número de caracteres da variável menos 1 para garantir que `\0` ao fim da string.

A importância de especificar o tamanho máximo de caracteres que a string pode conter se deve a prevenção de estouro de buffer.

Para a função `fgets()`, também é necessário especificar o tamanho máximo do buffer para garantir que não haja estouro. O tamanho do buffer deve ser o segundo argumento passado para `fgets()` (`sizeof(var_str)`).

#### Limpeza do Buffer

Quando utilizar `scanf()` e `fgets()` pode ser útil limpar o buffer do teclado (stdin). Isso evita que `fgets()` capture caracteres de nova linha (`\n`) deixados pelo `scanf()`. Isso é feito com a função **`getchar()`** após `scanf()`.

``` c
#include <stdio.h>

int main() {
    int userInt;
    char userStr[20];

    // Input de um valor inteiro
    printf("Digite um inteiro: ");
    scanf("%d", &userInt);

    // Limpa o buffer do teclado
    getchar();

    // Input de uma string
    printf("Digite algo: ");
    fgets(userStr, sizeof(userStr), stdin);

    // Output dos valores
    printf("Número: %d\n", userInt);
    printf("String: %s", userStr);

    return 0;
}
```

#### Entrada de Números com `fgets()`

A função `fgets()` recebe uma string do usuário, porém, é muito útil para verificar se uma entrada é ou não um número inteiro antes de continuar a execução do programa. Para isso, é necessário converter o valor de entrada para um número inteiro com a função **`sscanf()`**, que recebe os seguintes argumentos:

1. String de entrada.
1. Formato de entrada.
1. String de armazenamento.

Exemplo:

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

## Arrays

Arrays são usados para armazenar vários valores em uma única variável.

Arrays são declarados em variáveis `int` com `[]` ao fim do identificador, os valores são escritos entre chaves e separados por vírgula.

Sintaxe:

``` c
int myArray[] = {valor1, valor2, valor3};
```

Exemplo:

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

## Funções

São blocos de códigos reutilizáveis que podem receber dados.

Sintaxe:

``` c
void myFunction() {
    // Código a ser executado
}
```

`void` significa que a função não retorna nenhum valor.

Exemplo:

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
    return 2 * 2;
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

Sintaxe:

``` c
tipoDeRetorno myFunction(tipo param1, tipo param2, tipo param3) {
    // Código da função
}
```

Exemplo:

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

### Boas Práticas Para Funções

Em C, é uma boa prática declarar as funções antes de `main()` e as definições dessas funções abaixo de `main()`.

``` c
#include <stdio.h>

// Declaração de função
int soma(int valor1, int valor2);

int main() {
    printf("%d\n", soma(2, 3)); // Output: 5
    printf("%d\n", soma(5, 2)); // Output: 7
    printf("%d\n", soma(1, 0)); // Output: 1

    return 0;
}

// Definição de função
int soma(int valor1, int valor2) {
    return (valor1 + valor2);
}
```

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

São declarados como variáveis, porém os identificadores iniciam com `*` e seus valores são variáveis que se iniciam com `&` (referencia o endereço de memória da variável).

Exemplo:

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

* Ponteiros são declarados com `*` antes do identificador.

* Ao atribuir um endereço a um ponteiro, não deve ser usado `*` ao início do identificador (a menos que a atribuição seja feita no momento da declaração).

* Os valores de ponteiros são endereços de memória, por isso ao atribuir esses endereços é especificada a variável com `&` no início para referenciar o endereço de memória da mesma.

* Ao imprimir endereços de variáveis deve ser usado o formatador de tipo `%p`.

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

Então é possível usar `*` antes do nome do array para desreferência.

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

Exemplo:

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

Exemplo:

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
        printf("Falha na alocação de memória!\n");
        return 1; // Retorna verdadeiro quando o código der erro
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

Exemplo:

``` c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Alocação de memória
    int* ponteiro = (int*)malloc(10 * sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        printf("Falha na alocação de memória!\n");
        return 1;
    }

    // Modificando a memória alterada
    int* novo_ponteiro = (int*)realloc(ponteiro, 5 * sizeof(int));

    // Verificando se a realocação foi bem-sucedida
    if (novo_ponteiro == NULL) {
        printf("Falha ao realocar a memória!\n");
        free(ponteiro); // Liberando a memória original
        return 1;
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

Exemplo:

``` c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Alocação de memória para um array de 3 inteiros
    int* ponteiro = (int*)calloc(3, sizeof(int));

    // Verificando se a alocação foi bem-sucedida
    if (ponteiro == NULL) {
        printf("Falha na alocação de memória!\n");
        return 1;
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
        printf("Falha na alocação de memória!\n");
        return 0; // Retorna falso quando o código der erro
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
        printf("Falha na alocação de memória!\n");
        return 0; // Retorna falso quando o código der erro
    }

    // Definindo todos os elementos da memória para zero
    memset(ponteiro, 0, 5 * sizeof(int));

    // Libera a memória
    free(ponteiro);

    return 0;
}
```

##### Alocação de Strings

<!-- Não demore a escrever, por favor :) -->

##### Alocação de Estruturas

<!-- Não demore a escrever, por favor :) -->

##### Alocação de Matrizes Dinâmicas

<!-- Não demore a escrever, por favor :) -->

## Estruturas

Estruturas possibilitam agrupar diversas variáveis relacionadas em um único lugar.

Estruturas permitem diferentes tipos de valores, ao contrário de arrays.

Uma estrutura pode ser criada com a palavra-chave **`struct`**, e as variáveis que compõem estruturas são chamadas de **membros**.

Exemplo:

``` c
struct myStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};
```

> Estruturas devem ser finalizadas com ponto e vírgula.

Para acessar uma estrutura, é necessário criar uma variável para ela.

``` c
#include <stdio.h>

struct myStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};

int main() {
    struct myStructure structure1;
    return 0;
}
```

E para acessar os membros dessa estrutura, é usado a sintaxe de ponto '`.`'.

``` c
#include <stdio.h>

// Cria a estrutura `myStructure`
struct myStructure {
    int num1;       // Membro int
    float num2;     // Membro float
    char letter;    // Membro char
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct myStructure structure1;

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

### Strings em Estruturas

Não é possível atribuir uma string a um membro da mesma maneira que outros tipos de dados. Então para isso, é necessário usar a função **`strcpy()`** da biblioteca padrão `string.h`.

``` c
#include <stdio.h>
#include <string.h>

// Cria a estrutura `myStructure`
struct myStructure {
    char myStr[20];
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct myStructure structure1;

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

// Cria a estrutura `myStructure`
struct myStructure {
    int myInt;
    float myFloat;
    char myStr[20];
};

int main() {
    // Nova variável de estrutura que se chama `structure1`
    struct myStructure structure1 = { 13, 2.2, "Hello, World!" };

    // Impressão de valores.
    printf("%d\n", structure1.myInt);   // Output: 13
    printf("%f\n", structure1.myFloat); // Output: 2.200000
    printf("%s\n", structure1.myStr);   // Output: Hello, World!

    return 0;
}
```

> Atribuir valores aos membros desta maneira, torna desnecessário usar a função `strcpy()` para atribuir valores à membros strings.

## Enums

Um **enum** é um tipo especial que representa um grupo de constantes.

Enums são criados a partir da palavra-chave `enum`, seguido do nome do enum. Cada item dentro do enum é chamado de **membro**, e esses membros são separados por vírgula.

Exemplo:

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

## `typedef`

A palavra-chave **`typedef`** é usada para criar um alias de um tipo de dado.

> Um alias é um nome altenativo para identificar ou se referir ao mesmo objeto de dados.

São usados para tornar o código mais legível para para facilitar a manutenção futuramente, pois não haverá a necessidade de alterar o tipo de dado de diversos dados com o mesmo tipo um por um.

A sintaxe é a seguinte:

``` c
typedef tipo_original novo_nome;
```

Exemplo:

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

### Estruturas e `typedef`

Frequentemente é utilizado `typedef` junto a estruturas para criar nomes mais legíveis e expressivos para tipos de dados complexos.

``` c
#include <stdio.h>

// Declarando uma estrutura
struct myStructure {
    int num1;
    int num2;
};

// Criando um alias para a estrutura `myStructure`
typedef struct myStructure Numeros;

int main() {
    // Atribuindo valores à estrutura
    Numeros structure1 = {13, 22};

    // Imprimindo os valores
    printf("%d\n", structure1.num1); // Output: 13
    printf("%d\n", structure1.num2); // Output: 22

    return 0;
}
```

### Ocultar Detalhes de Implementação

Usar `typedef` permite ocultar detalhes de implementação, o ajuda a criar uma interface mais limpa, isolando os detalhes internos de uma implementação específica.

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

Exemplo:

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

Exemplo:

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
