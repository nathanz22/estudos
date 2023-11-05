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
