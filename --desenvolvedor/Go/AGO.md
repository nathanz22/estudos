# Go

## Sintaxe Básica

Um arquivo Go é composto pelas seguintes partes:

* Declaração de pacotes
* Importação de Pacotes
* Funções
* Declarações e Expressões

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    fmt.Println("Olá, Mundo!")
}
```

No exemplo acima:

1. **'`package main`'**: A palavra-chave `package` é usada para definir o pacote do programa, no caso, no pacote `main`.

1. **'`import "fmt"`'**: Importa o pacote `fmt`, no caso, usado para impressão.

1. **'`func main() {}`'**: É uma função, e tudo entre as chaves faz parte dela. É uma função especial, pois todo seu conteúdo é executado assim que o programa for executado.

1. **'`fmt.Println()`'**: Função do pacote `fmt`, usada para imprimir um texto. No caso, ela imprimiu "Olá, Mundo!".

### Declarações

As declarações são separadas por uma quebra de linha ou por um **`;`** (ponto e vírgula).

Então, é possível fazer várias declarações em apenas uma linha:

``` go
package main

import "fmt"

func main() {
    fmt.Println("Olá, Mundo!"); fmt.Println("Olá, Go!")
}
/* Output =>
Olá, Mundo!
Olá, Go!
*/
```

### Comentários

Em Go, comentários de uma única linha são representados por **`//`**, enquanto comentários de múltiplas linhas são representados por **`/* */`**.

**Exemplo:**

``` go
// Comentário de uma linha

/*
Comentário
de
Várias
Linhas
*/
```

## Variáveis

Go é uma linguagem de programação com tipagem forte e estática, o que significa que os tipos das variáveis são verificados em tempo de compilação. Isso cria a necessidade de especificar o tipo da variável assim que ela for declarada.

Variáveis são declaradas com a palavra-chave **`var`**, seguida do nome e tipo da variável. O valor da variável é atribuído por meio do operador **`=`**.

**Sintaxe:**

``` go
var nomeVariavel tipo = valor
```

**Os tipos de variáveis são:**

* **'`int`'**: Armazena úmeros inteiros.
* **'`float32`'**: Armazena números de ponto flutuante.
* **'`string`'**: Armazenam textos.
* **'`bool`'**: Armazenam valores booleanos (`true` e `false`).

**Exemplo:**

``` go
var myInt int = 5
var myFloat float32 = 3.14
var myStr string = "Olá, Mundo!"
var myBool bool = true
```

Não é necessariamente obrigatório inicializar uma variável assim que declará-la.

``` go
// Declara as variáveis
var myInt int
var myFloat float32
var myStr string
var myBool bool

// Atribui os valores a elas
myInt = 5
myFloat = 3.14
myStr = "Olá, Mundo!"
myBool = true
```

### Tipagem Automática

Também chamado de "inferência de tipo", a tipagem automática é a capacidade de deduzir automaticamente o tipo de uma variável com base no seu valor atribuído. É feita a partir do operador **`:=`**.

**Sintaxe:**

``` go
nomeVariável := valor
```

Perceba que não há necessidade de escrever `var` ao início da declaração.

> **OBS.:** Ao usar a tipagem automática, é obrigatória inicializar a variável no mesmo momento da declaração.

**Exemplo:**

``` go
myInt := 5
myFloat := 3.14
myStr := "Olá, Mundo!"
myBool := true
```

> **OBS.:** Variáveis de tipagem automática não podem ser declaradas fora de funções.

### Declaração Múltipla de Variáveis

É possível declarar várias variáveis na mesma linha.

**Exemplo:**

``` go
var x, y, z int = 2, 5, 8
```

Os valores podem ser atribuídos posteriormente também.

**Exemplo:**

``` go
var x, y, z int
x, y, z = 2, 5, 8
```

Se não passado o tipo, é possível declarar variáveis de tipos diferentes na mesma linha.

**Exemplo:**

``` go
var x, y = 5, "Go!"
```

**O mesmo para variáveis inferidas:**

``` go
x, y, z := 5, "Go!", 7.2
```

#### Declaração Múltipla de Variáveis em Bloco

É possível declarar múltiplas variáveis dentro de um bloco, declarando com **`var ()`**.

**Exemplo:**

``` go
var (
    x int = 5
    y string = "Go!"
    z float32 = 7.2
)
```

### Regras para Nome de Variáveis

As regras são:

* Devem iniciar com uma letra ou `_`.

* Podem conter caracteres alfanuméticos e underlines (`a-z`, `A-Z`, `0-9`, `_`);

* São case-sensitive, ou seja, caracteres maiúsculos e minúsculos são diferentes (`x` é diferente de `X`).

* Geralmente são escritas em *camelCase*.

## Constantes

Constantes são declaradas usando a palavra-chave **`const`**, semelhante à declaração de variáveis, e podem ser tipadas ou não tipadas.

**Sintaxe:**

``` go
// Contante tipada
const NOMECONST tipo = valor

// Constante não tipada
const NAMECONST = valor
```

**Exemplo:**

``` go
const PI = 3.14159
```

### Regras para Constantes

* Nomes para constantes possuem a mesmas regras de variáveis.

* Constantes geralmente são escritas com letras maiúsculas.

* Constantes podem ser declaradas dentro e fora de funções.

### Declaração Múltipla de Constantes

Para declarar múltiplas constantes, é usado **`const ()`**.

**Exemplo:**

``` go
const (
    X int = 5
    Y string = "Olá, Mundo!"
    Z = 3.14
)
```

## Output

Em Go, há três funções para saída de texto:

* **`Print()`**
* **`Println()`**
* **`Printf()`**

### Função `Print()`

Imprime os valores sem quebra de linha no fim.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    str1 := "Olá"; str2 := "Mundo"

    fmt.Print(str1)
    fmt.Print(str2)
    // Output => OláMundo!
}
```

**Pode aceitar múltiplos argumentos para impressão:**

``` go
package main

import "fmt"

func main() {
    str1 := "Olá"; str2 := "Mundo"

    fmt.Print(str1, ", ", str2)
    // Output => Olá, Mundo!
}
```

**Se os argumentos para impressão não forem strings, será criado um espaço entre eles:**

``` go
package main

import "fmt"

func main() {
    var x, y = 13, 22

    fmt.Print(x, y)
    // Output => 13 22
}
```

### Função `Println()`

Similar a função `Print()`, porém imprime um espaço entre osargumentos e quebra a linha no fim.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var str1, str2 = "Olá", "Mundo!"

    fmt.Println(str1)
    fmt.Println(str2)

    /* Output =>
    Olá
    Mundo!
    */
}
```

**Com mais de um argumento:**

``` go
package main

import "fmt"

func main() {
    var x, y, z = 5, 10, 15

    fmt.Println(x, y)
    fmt.Println(z)

    /* Output =>
    5 10
    15
    */
}
```

### Função `Printf()`

Formata os valores antes de imprimir.

**Formatadores:**

* **'`%v`'**: Imprime o valor do argumento.
* **'`%T`'**: Imprime o tipo do argumento.

Antes de imprimir, os formatadores são substituídos pelo valor ou tipo de seu respectivo argumento.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x, y, z = "Olá, Mundo!", 15, true

    fmt.Printf("Valor: %v | Tipo: %T\n", x, x)
    fmt.Printf("Valor: %v | Tipo: %T\n", y, y)
    fmt.Printf("Valor: %v | Tipo: %T\n", z, y)

    /* Output =>
    Valor: Olá, Mundo! | Tipo: string
    Valor: 15 | Tipo: int
    Valor: true | Tipo: int
    */
}
```

## Formatadores

### Formatadores para Inteiros

* **'`%d`'**: Formata um valor como número decimal.
* **'`%b`'**: Formata um valor como número binário.
* **'`%o`'**: Formata um valor como número octal.
* **'`%x`'**: Formata um número como hexadecimal (letras minúsculas).
* **'`%X`'**: Formata um número como hexadecimal (letras maiúsculas).

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x = 43

    fmt.Printf("Valor em decimal: %d\n", x)
    fmt.Printf("Valor em binário: %b\n", x)
    fmt.Printf("Valor em octal: %o\n", x)
    fmt.Printf("Valor em hexadecimal: %x\n", x)
    fmt.Printf("Valor hexadecimal maiúsculo: %X\n", x)

    /* Output
    Valor em decimal: 43
    Valor em binário: 101011
    Valor em octal: 53
    Valor em hexadecimal: 2b
    Valor hexadecimal maiúsculo: 2B
    */
}
```

### Formatadores para Números de Pontos Flutuante

* **'`%f`'**: Formata um valor como um número de ponto flutuante na notação decimal.
* **'`%e`'**: Formata um valor usando notação científica (letras minúsculas).
* **'`%E`'**: Formata um valor usando notação científica (letras maiúsculas).
* **'`%g`', '`%G`'**: Formata um valor usando a notação de `%e` ou `%f`, dependendo da magnitude no número.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x = 3.14159

    fmt.Printf("Valor padrão: %f\n", x)
    fmt.Printf("Valor em notação científica: %e\n", x)
    fmt.Printf("Valor em notação científica: %E\n", x)
    fmt.Printf("Valor com `%%g`: %g\n", x)

    /* Output
    Valor padrão: 3.141590
    Valor em notação científica: 3.141590e+00
    Valor em notação científica: 3.141590E+00
    Valor com `%g`: 3.14159
    */
}
```

### Formatadores para Strings

* **'`%s`'**: Formata um valor para uma string.
* **'`%q`'**: Formata um valor para uma string com aspas duplas (imprime as aspas duplas).
* **'`%x`'**: Formata um valor para bytes hex dump.
* **'`% x`'**: Formata um valor para bytes hex dump com espaços.

> **OBS.:** Se nos formatos `%x` e `% x` o `x` for escrito em maiúsculo, será formatado as letras em maiúsculas.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var str = "Go!"

    fmt.Printf("String: %s\n", str)
    fmt.Printf("String com aspas: %q\n", str)
    fmt.Printf("String como hex dump: %x\n", str)
    fmt.Printf("String como hex dump com espaços: % x\n", str)

    /* Output
    String: Go!
    String com aspas: "Go!"
    String como hex dump: 476f21
    String como hex dump com espaços: 47 6f 21
    */
}
```

### Formatadores para Booleanos

Pode-se usar **`%t`** ou **`%v`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x = true
    var y = false

    fmt.Printf("Valor de x: %t\n", x)
    fmt.Printf("Valor de y: %t\n", y)

    /* Output
    Valor de x: true
    Valor de y: false
    */
}
```

### Outros Formatadores

* **'`%v`'**: Formata um valor na forma mais simples para sua representação.

    ``` go
    package main

    import "fmt"

    func main() {
        var x = 22
        var y = "Olá, Mundo!"
        var z = true

        fmt.Printf("Valor de x: %v\n", x)
        fmt.Printf("Valor de y: %v\n", y)
        fmt.Printf("Valor de z: %v\n", z)

        /* Output
        Valor de x: 22
        Valor de y: Olá, Mundo!
        Valor de z: true
        */
    }
    ```

* **'`%T`'**: Formata um valor para seu tipo.

    ``` go
    package main

    import "fmt"

    func main() {
        var x = 22
        var y = "Olá, Mundo!"
        var z = true

        fmt.Printf("Tipo de x: %T\n", x)
        fmt.Printf("Tipo de y: %T\n", y)
        fmt.Printf("Tipo de z: %T\n", z)

        /* Output
        Tipo de x: int
        Tipo de y: string
        Tipo de z: bool
        */
    }
    ```

* **'`%c`'**: Formata um valor como um caractere (unicode).
* **'`%U`'**: Formata um valor como ponto de código Unicode.

**Exemplo `%c` e `%U`:**

``` go
package main

import "fmt"

func main() {
    char := 'A'

    fmt.Printf("Caractere: %c\n", char)
    fmt.Printf("Código Unicode: %U\n", char)

    /* Output
    Caractere: A
    Código Unicode: U+0041
    */
}
```

## Tipos Primitivos

Em Go, os tipos primitivos básicos são:

* **'`int`'**: Representa números inteiros.
* **'`float32`', '`float64`'**: Representam números de ponto flutuante.
* **'`complex64`', '`complex128`'**: Representam complexos.
* **'`string`'**: Representa uma string
* **'`bool`'**: Representa um valor booleano.

### Inteiros

O tipo **`int`** é a maneira mais simples de representar números inteiros, e seu tamanho varia de acordo com a arquitetura da máquina.

``` go
var inteiro int
```

#### Inteiros com Tamanho Específico

Os tipos **`int8`**, **`int16`**, **`int32`** e **`int64`** representam números inteiros com tamanhos específicos de 8, 16, 32 e 64 bits, respectivamente.

``` go
var inteiro8 int8
var inteiro16 int16
var inteiro32 int32
var inteiro64 int64
```

#### Inteiros sem Sinal

São inteiros que não têm sinal negativo, e assim como os tipos com sinal. Os tipos são **`uint8`**, **`uint16`**, **`uint32`** e **`uint64`**, e eles têm tamanhos específicos de 8, 16, 32 e 64 bits.

``` go
var inteiroSemSinal8 uint8
var inteiroSemSinal16 uint16
var inteiroSemSinal32 uint32
var inteiroSemSinal64 uint64
```

Há também o tipo **`uintptr`**, que é usado para armazenar valores inteiros não assinados suficientes para armazenar todos os bits de um ponteiro.

### Números de Ponto Flutuante

Há dois tipos para representar números de ponto flutuante: **`float32`** e **`float64`**.

* **'`float32`'**: Ocupa 32 bits, e sua faixa é **`-3.4e+38`** até **`3.4e+38`**

    ``` go
    package main

    import "fmt"

    func main() {
        var x float32 = 123.456
        var y float32 = 3.4e+38

        fmt.Printf("Tipo: %T | Valor: %v\n", x, x)
        fmt.Printf("Tipo: %T | Valor: %v\n", y, y)

        /* Output =>
        Tipo: float32 | Valor: 123.456
        Tipo: float32 | Valor: 3.4e+38
        */
    }
    ```

* **'`float64`'**: Ocupa 64 bits, e sua faixa é **`-1.7e+308`** até **`1.7e+308`**. Este é o valor padrão quando não especificado o tipo do valor float.

    ``` go
    package main

    import "fmt"

    func main() {
        var x float64 = 123.456
        var y float64 = 1.7e+308

        fmt.Printf("Tipo: %T | Valor: %v\n", x, x)
        fmt.Printf("Tipo: %T | Valor: %v\n", y, y)

        /* Output =>
        Tipo: float64 | Valor: 123.456
        Tipo: float64 | Valor: 1.7e+308
        */
    }
    ```

### Strings

Em Go, strings são envoltas em aspas duplas.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var str1 string = "Olá, Mundo!"
    var str2 string = "Olá, Go!"

    fmt.Printf("Tipo: %T | Valor: %v\n", str1, str1)
    fmt.Printf("Tipo: %T | Valor: %v\n", str2, str2)

    /* Output =>
    Tipo: string | Valor: Olá, Mundo!
    Tipo: string | Valor: Olá, Go!
    */
}
```

> **OBS.:** Aspas simples são usadas para caracteres, e não strings.

#### Comprimento de uma String

A função **`len()`** retorna o comprimento de uma string.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    myStr := "Hello, World!"
    fmt.Println(len(myStr)) // Output => 13
}
```

#### Pacote `strings`

O pacote **`strings`** fornece várias funções para manipulação de strings.

**Algumas das funções são:**

* **'`ToUpper()`'**: Transforma todos os caracteres de uma dada string para maiúsculo e a retorna.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        resultado := strings.ToUpper(myStr)

        fmt.Println(resultado)
        // Output => OLÁ, MUNDO!
    }
    ```

* **'`ToLower()`'**: Transforma todos os caracteres de uma dada string para minúsculo e a retorna.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        resultado := strings.ToLower(myStr)

        fmt.Println(resultado)
        // Output => olá, mundo!
    }
    ```

* **'`Contains()`'**: Dada a string e uma substring, verifica se a substring existe dentro da string.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        subStr := "Mundo"

        resultado := strings.Contains(myStr, subStr)
        fmt.Println(resultado) // Output => true
    }
    ```

* **'`Count`'**: Dada uma string e uma substring, retorna a quantidade de vezes que a substring ocorreu dentro da string.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "I love Golang!"
        subStr := "o"

        resultado := strings.Count(myStr, subStr)
        fmt.Println(resultado) // Output => 2
    }
    ```

* **'`HasPrefix()`'**: Dada uma string e uma substring, analisa se a string se inicia com a substring.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        subStr := "Olá"

        resultado := strings.HasPrefix(myStr, subStr)
        fmt.Println(resultado) // Output => true
    }
    ```

* **'`HasSuffix()`'**: Dada uma string e uma substring, analisa se a string se inicia com a substring.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        subStr := "!"

        resultado := strings.HasSuffix(myStr, subStr)
        fmt.Println(resultado) // Output => true
    }
    ```

* **'`Index()`'**: Dada uma string e uma substring, retorna o índice da primeira ocorrência da substring.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Hello, World!"
        subStr := "W"

        resultado := strings.Index(myStr, subStr)
        fmt.Println(resultado) // Output => 7
    }
    ```

* **'`Replace()`'**: Substitui n ocorrências de uma substring dentro da string e retorna uma cópia.

    Os parâmetros são:

    1. **'`s`'**: String que será feita as substituições.
    1. **'`old`'**: Substring que será substituída.
    1. **'`new`'**: Substring que substituirá.
    1. **'`n`'**: Quantas ocorrências serão substituídas. Se especificado `-1`, será feita as substituições em todas as ocorrências.

    **Exemplo:**

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Golang is powerful. Golang is amazing."

        resultado := strings.Replace(myStr, "Golang", "Go", -1)
        fmt.Println(resultado)
        // Output => Go is powerful. Go is amazing.
    }
    ```

* **'`ReplaceAll()`'**: Substitui todas as ocorrências de uma substring dentro de uma string e retorna uma cópia.

    Os parâmetros são:

    1. **'`s`'**: String que será feita as substituições.
    1. **'`old`'**: Substring que será substituída.
    1. **'`new`'**: Substring que substituirá.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Golang is powerful. Golang is amazing."

        resultado := strings.ReplaceAll(myStr, "Golang", "Go")
        fmt.Println(resultado)
        // Output => Go is powerful. Go is amazing.
    }
    ```

* **'`Split()`'**: Dada uma string e um separador, separa a string em um slice de strings.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "I love Golang!"
        mySplit := strings.Split(myStr, " ")

        fmt.Println(mySplit)
        // Output => [I love Golang!]
    }
    ```

* **'`Repeat()`'**: Repete uma string n vezes e a retorna.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "Olá, Mundo!"
        resultado := strings.Repeat(myStr, 2)

        fmt.Println(resultado)
        // Output => Olá, Mundo!Olá, Mundo!
    }
    ```

* **'`TrimSpace()`'**: Remove os espaços em branco no início e fim de uma string e a retorna.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "     \"Olá, Mundo!\"     "
        resultado := strings.TrimSpace(myStr)

        fmt.Println(resultado)
        // Output => "Olá, Mundo!"
    }
    ```

* **'`Trim()`'**: Remove um dado caractere no início e no final de uma string e a retorna.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        myStr := "-----\"Olá, Mundo!\"-----"
        resultado := strings.Trim(myStr, "-")

        fmt.Println(resultado)
        // Output => "Olá, Mundo!"
    }
    ```

* **'`Compare()`'**: Compara duas strings lexicograficamente. Retorna **`0`** se são iguais, um **número negativo** se a string à esquerda for menor ou um **número positivo** se a string da esquerda for maior.

    ``` go
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        fmt.Println(strings.Compare("abc", "abc")) // Output => 0
        fmt.Println(strings.Compare("abc", "def")) // Output => -1
        fmt.Println(strings.Compare("def", "abc")) // Output => 1
    }
    ```

#### Formatação de Strings

<!-- Já vai! -->

### Booleanos

O tipo **`bool`** representa valores booleanos, que são **`true`** e **`false`**.

``` go
package main

import "fmt"

func main() {
    var x bool
    fmt.Printf("Tipo: %T\n", x) // Output => Tipo: bool
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x bool = true
    var y bool = false
    var z bool

    fmt.Println(x) // Output => true
    fmt.Println(y) // Output => false
    fmt.Println(z) // Output => false
}
```

## Arrays

Em Go, arrays só podem armazenar valores de mesmo tipo. Declarar um array é similar a declaração de uma variável comum, mas ao definir o valor, deve-se especificar o tamanho, tipo de dado e os valores do array.

**Sintaxe:**

``` go
// Com `var`
var nomeArray = [comprimento]tipo{valor1, valor2, ..., valor10}

// Com `:=`
nomeArray := [comprimento]tipo{valor1, valor2, ..., valor10}
```

**Exemplo:**

``` go
// Com `var`
var myArray = [5]int{2, 4, 6, 8, 10}

// Com `:=`
myArray := [5]int{2, 4, 6, 8, 10}
```

### Comprimento Inferido em Arrays

Definir o comprimento de um array como **`...`** indica que o comprimento é inferido, o que significa que o compilador decide a largura do array baseado no número de dados.

**Exemplo:**

``` go
// Com `var`
var myArray = [...]int{2, 4, 6, 8, 10}

// Com `:=`
myArray := [...]int{2, 4, 6, 8, 10}
```

### Acesso aos Elementos de um Array

É feito por meio de notação de colchetes e índices numéricos, onde `0` é o primeiro elemento do array.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Array de inteiros
    myArray := [5]int{2, 4, 6, 8, 10}


    fmt.Println(myArray[0]) // Output => 2
    fmt.Println(myArray[1]) // Output => 4
    fmt.Println(myArray[2]) // Output => 6
    fmt.Println(myArray[3]) // Output => 8
    fmt.Println(myArray[4]) // Output => 10
}
```

Dessa maneira, é possível também alterar o valor de um elemento dentro de um array.

``` go
package main

import "fmt"

func main() {
    // Array de inteiros
    myArray := [4]int{2, 4, 6, 8}

    // Altera o segundo elemento para `20`
    myArray[1] = 20

    fmt.Println(myArray) // Output => [2 20 6 8]
}
```

### Inicialização de Arrays

O valor padrão para elementos não inicializados em arrays depende do tipo do array.

* **Array de inteiros**: **`0`**.
* **Array de floats**: **`0`**.
* **Array de strings**: **`""`**.
* **Array de booleanos**: **`false`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declaração de arrays vazios
    intArray := [3]int{}
    floatArray := [3]float32{}
    strArray := [3]string{}
    boolArray := [3]bool{}

    // Imprime os arrays
    fmt.Println(intArray)   // Output => [0 0 0]
    fmt.Println(floatArray) // Output => [0 0 0]
    fmt.Println(strArray)   // Output => [  ]
    fmt.Println(boolArray)  // Output => [false false false]
}
```

#### Inicializar Valores Específicos

É possível inicializar um array com elementos especificando suas respectivas posições.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declaração do array
    myArray := [5]int{1:5, 2:10}

    // Imprime o array
    fmt.Println(myArray) // Output => [0 5 10 0 0]
}
```

## Slices

São similares a arrays, porém são mais frexíveis e úteis. Slices podem aumentar dinamicamente em tempo de execução.

Para declarar um slice, basta declarar um array sem especificar um tamanho fixo, deixando os colchetes vazios.

**Sintaxe:**

``` go
nomeSlice := []tipo{valor1, valor2, ..., valor10}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declaração dos slices
    mySlice1 := []int{}
    mySlice2 := []int{3, 2, 1}
    mySlice3 := []int{5, 4, 3, 2}

    // Imprime a largura dos slices
    fmt.Println(len(mySlice1)) // Output => 0
    fmt.Println(len(mySlice2)) // Output => 3
    fmt.Println(len(mySlice3)) // Output => 4
}
```

Como observado no exemplo acima, o comprimento de um slice é determinado pela quantidade de elementos que ele armazena, ao contrário dos arrays, que têm um tamanho fixo.

### Criação de Slices

A função **`make()`** pode ser usada para criar um slice.

**Sintaxe:**

``` go
nomeSlice := make([]tipo, comprimento, capacidade)
```

> **OBS.:** Se a capacidade não for definida, ela será o mesmo que o comprimento.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando slices com `make()`
    mySlice1 := make([]int, 3, 5)
    mySlice2 := make([]int, 2)

    // Imprimindo os slices
    fmt.Println(mySlice1) // Output => [0 0 0]
    fmt.Println(mySlice2) // Output => [0 0]

    // Imprimindo largura e capacidade dos slices
    fmt.Println(len(mySlice1)) // Output => 3
    fmt.Println(cap(mySlice1)) // Output => 5

    fmt.Println(len(mySlice2)) // Output => 2
    fmt.Println(cap(mySlice2)) // Output => 2
}
```

### Comprimento e Capacidade de Slices

A função **`len()`**, quando especificado um slice, retorna a quantidade de elementos dentro desse slice (comprimento do slice).

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declaração dos slices
    mySlice1 := []int{}
    mySlice2 := []int{3, 2, 1}
    mySlice3 := []int{5, 4, 3, 2}

    // Imprime a largura dos slices
    fmt.Println(len(mySlice1)) // Output => 0
    fmt.Println(len(mySlice2)) // Output => 3
    fmt.Println(len(mySlice3)) // Output => 4
}
```

A função **`cap()`** retorna a capacidade de um slice, que é o número de elementos que o slice pode aumentar.

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice1 := make([]int, 5, 10)
    mySlice2 := make([]int, 2)
    mySlice3 := make([]int, 3, 4)

    // Imprime a capacidade dos slices
    fmt.Println(cap(mySlice1)) // Output => 10
    fmt.Println(cap(mySlice2)) // Output => 2
    fmt.Println(cap(mySlice3)) // Output => 4
}
```

### Fatiamento de Slices

O termo *"slicing"* é usado para a ação de extrair partes de um slice. É feito utilizando **`:`**.

**Sintaxe:**

``` go
novoSlice := slice[inicio:fim]
```

No exemplo acima, `inicio` e `fim` se refere aos índices dos elementos que serão capturados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice := []int{1, 2, 3, 4, 5, 6, 7, 8, 9}

    // Criando uma fatia
    slice1 := mySlice[3:7]
    slice2 := mySlice[1:3]
    slice3 := mySlice[5:]
    slice4 := mySlice[2:5]
    slice5 := mySlice[:4]
    slice6 := mySlice[:]

    // Imprime as fatias
    fmt.Println(slice1) // Output => [4 5 6 7]
    fmt.Println(slice2) // Output => [2 3]
    fmt.Println(slice3) // Output => [6 7 8 9]
    fmt.Println(slice4) // Output => [3 4 5]
    fmt.Println(slice5) // Output => [1 2 3 4]
    fmt.Println(slice6) // Output => [1 2 3 4 5 6 7 8 9]
}
```

> **OBS.:** Não especificar o início, será o mesmo que especificar o primeiro elemento. Não especificar o fim, é o mesmo que especificar o último elemento.

### Adicionar Elementos a um Slice

A função **`append()`** é usada para adicionar elementos a um slice.

O primeiro argumento é slice que será adicionado, e os próximos argumentos são os elementos a serem adicionados a esse slice.

É retornado um novo slice contendo os elementos adicionados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice := []int{1, 2, 3, 4}

    // Novo slice com os elementos do anterior e um a mais
    novoSlice := append(mySlice[:], 5)

    // Imprime o slice antigo e o novo
    fmt.Println(mySlice)    // Output => [1 2 3 4]
    fmt.Println(novoSlice)  // Output => [1 2 3 4 5]
}
```

Geralmente é usado simplesmente para adicionar elementos a um slice.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice := []int{1, 2, 3, 4}

    // Adicionando elementos ao slice
    mySlice = append(mySlice[:], 5, 6, 7)

    // Imprime o slice
    fmt.Println(mySlice) // Output => [1 2 3 4 5 6 7]
}
```

Se ao invés de elementos for adicionado outro slice, é necessário definir **`...`** ao fim do slice.

``` go
package main

import "fmt"

func main() {
    // Criando dois slices
    mySlice1 := []int{1, 2, 3}
    mySlice2 := []int{10, 20, 30}

    // Slice com os elementos dos outros slices
    mySlice3 := append(mySlice1, mySlice2...)

    // Imprimindo a cópia dos slices
    fmt.Println(mySlice3) // Output => [1 2 3 10 20 30]
}
```

### Remover Elementos de um Slice

É usada a função **`append()`** junto a técnica "slicing" para criar um novo slice que exclui os elementos desejados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice := []int{1, 2, 3, 4, 5}

    // Índice do elemento a ser removido
    indexToRemove := 2

    // Remove o elemento do slice
    mySlice = append(mySlice[:indexToRemove], mySlice[indexToRemove + 1:]...)

    // Imprime o novo slice
    fmt.Println(mySlice) // Output => [1 2 4 5]
}
```

### Cópia entre Slices

A função **`copy()`** copia os elementos de um slice para um outro slice e retorna a quantidade de elementos copiados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando um slice
    mySlice := []int{1, 2, 3, 4, 5}

    // Slice que será a cópia
    newSlice := make([]int, 6)
    numElements := copy(newSlice, mySlice)

    // Imprime os slices
    fmt.Printf("Slice original: %v\n", mySlice)
    fmt.Printf("Elementos copiados: %d\n", numElements)
    fmt.Printf("Cópia do slice: %v\n", newSlice)

    /* Output =>
    Slice original: [1 2 3 4 5]
    Elementos copiados: 5
    Cópia do slice: [1 2 3 4 5 0]
    */
}
```

### Ordenação de Elementos em Slices

O pacote **`sort`** fornece funcionalidades para ordenar slices e arrays.

* **'`Ints()`'**: Ordena um slice de inteiros.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myIntSlice := []int{5, 2, 1, 3, 4}

        // Ordenando o slice
        sort.Ints(myIntSlice)

        // Imprime o slice ordenado
        fmt.Println(myIntSlice) // Output => [1 2 3 4 5]
    }
    ```

* **'`Float64s`'**: Ordena um slice de `float64`.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myFloatSlice := []float64{5.4, 5.2, 5.1, 5.5, 5.3}

        // Ordenando o slice
        sort.Float64s(myFloatSlice)

        // Imprime o slice ordenado
        fmt.Println(myFloatSlice) // Output => [5.1 5.2 5.3 5.4 5.5]
    }
    ```

* **'`Strings`'**: Ordena um slice de strings.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myStrSlice := []string{"Go", "Python", "Ruby", "C++"}

        // Ordenando o slice
        sort.Strings(myStrSlice)

        // Imprime o slice ordenado
        fmt.Println(myStrSlice) // Output => [C++ Go Python Ruby]
    }
    ```

* **'`IntsAreSorted()`'**: Retorna verdadeiro se um dado slice de inteiros estiver ordenado.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myIntSlice := []int{1, 2, 3, 4, 5}

        // Verifica se o slice está ordenado
        ordenado := sort.IntsAreSorted(myIntSlice)

        fmt.Println(ordenado) // Output => true
    }
    ```

* **'`Float64AreSorted()`'**: Retorna verdadeiro se um dado slice do tipo `float64` estiver ordenado.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myFloatSlice := []float64{5.1, 5.2, 5.3, 5.4, 5.5}

        // Verifica se o slice está ordenado
        ordenado := sort.Float64sAreSorted(myFloatSlice)

        fmt.Println(ordenado) // Output => true
    }
    ```

* **'`StringAreSorted()`'**: Retorna verdadeiro se um dado slice de strings estiver ordenado.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando um slice
        myStrSlice := []string{"C++", "Go", "Python", "Ruby"}

        // Verifica se o slice está ordenado
        ordenado := sort.StringsAreSorted(myStrSlice)

        fmt.Println(ordenado) // Output => true
    }
    ```

## Operadores

Em Go, os quatro tipos de operadores principais são:

* Operadores aritméticos
* Operadores de comparação
* Operadores lógicos
* Operadores bitwise

### Operadores Aritméticos

Permitem realizar operações matemáticas em variáveis ou valores numéricos. Os operadores aritméticos são:

* **'`+`'**: Adição.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 10 + 5
        y := 7 + 4
        z := 1 + 1

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 15
        fmt.Println(y) // Output => 11
        fmt.Println(z) // Output => 2
    }
    ```

* **'`-`'**: Subtração.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 5 - 2
        y := 1 - 3
        z := 10 - 8

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 3
        fmt.Println(y) // Output => -2
        fmt.Println(z) // Output => 2
    }
    ```

* **'`*`'**: Multiplicação.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 10 * 3
        y := 13 * 1
        z := 8 * 8

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 30
        fmt.Println(y) // Output => 13
        fmt.Println(z) // Output => 64
    }
    ```

* **'`/`'**: Divisão.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 12 / 2
        y := 21 / 3
        z := 5 / 2

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 6
        fmt.Println(y) // Output => 7
        fmt.Println(z) // Output => 2
    }
    ```

    Se ambos os operandos forem inteiros, o resultado será inteiro e por isso `5 / 2 = 2`. Para a divisão real, pelo menos um dos operandos deve ser um número de ponto flutuante.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 13 / 2.0
        y := 9.0 / 6.0
        z := 5.0 / 2

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 6.5
        fmt.Println(y) // Output => 1.5
        fmt.Println(z) // Output => 2.5
    }
    ```

* **'`%`'**: Módulo (resto da divisão).

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 13 % 2
        y := 9 % 6
        z := 5 % 2

        // Imprime o resultado de operações
        fmt.Println(x) // Output => 1
        fmt.Println(y) // Output => 3
        fmt.Println(z) // Output => 1
    }
    ```

* **'`++`'**: Incrementa 1 à uma variável.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variável com o valor 10
        x := 10

        // Incrementa 1 à variável
        x++ // O mesmo que `x += 1` ou `x = x + 1`

        // Imprime a variável
        fmt.Println(x) // Output => 11
    }
    ```

* **'`--`'**: Decrementa 1 de uma variável.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variável com o valor 10
        x := 10

        // Decrementa 1 de uma variável
        x-- // O mesmo que `x -= 1` ou `x = x - 1`

        // Imprime a variável
        fmt.Println(x) // Output => 9
    }
    ```

### Operadoes de Comparação

* **'`==` (Igual)'**: Verdadeiro se os operandos forem iguais (mesmo tipo e valor).

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := "Go!" == "Go!"
        y := 2 == 2.0
        z := 5 == '5'

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => false
    }
    ```

* **'`!=` (Diferente)'**: Verdadeiro se os operandos forem diferentes.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := "Go!" != "Go!"
        y := 2 != 2.0
        z := 5 != '5'

        // Imprime o resultado de operações
        fmt.Println(x) // Output => false
        fmt.Println(y) // Output => true
        fmt.Println(z) // Output => true
    }
    ```

* **'`<`' (Menor)**: Verdadeiro se o operando à esquerda for menor que o da direita.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 2 < 5
        y := 5.3 < 4
        z := 6 < 7

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => true
    }
    ```

* **'`>`' (Maior)**: Verdadeiro se o operando à esquerda for maior que o da direita.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 5 > 2
        y := 2 > 3
        z := 7 > 7

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => false
    }
    ```

* **'`<=`' (Menor ou igual)**: Verdadeiro se o operando à esquerda for menor ou igual ao da direita.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 2 <= 5
        y := 5 <= 4
        z := 6 <= 6

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => true
    }
    ```

* **'`>=`' (Maior ou igual)**: Verdadeiro se o operando à esquerda for maior ou igual ao da direita.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := 5 >= 2
        y := 2 >= 3
        z := 7 >= 7

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => true
    }
    ```

### Operadores Lógicos

* **'`&&`' (AND)**: Verdadeiro se ambos os operandos forem verdadeiro.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := true && true
        y := true && false
        z := false && false

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => false
    }
    ```

* **'`||`' (OR)**: Verdadeiro se pelo menos um dos operandos for verdadeiro.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := true || true
        y := true || false
        z := false || false

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => true
        fmt.Println(z) // Output => false
    }
    ```

* **'`!`' (NOT)**: Inverte o valor booleano, ou seja, se a variável ou expressão for verdadeira, ela se torna false, e se for falsa, se torna verdadeira.

    ``` go
    package main

    import "fmt"

    func main() {
        // Variáveis que armazenam operações
        x := !false
        y := !true
        z := !(5 < 10)

        // Imprime o resultado de operações
        fmt.Println(x) // Output => true
        fmt.Println(y) // Output => false
        fmt.Println(z) // Output => false
    }
    ```

### Operadores Bitwise

São utilizados para realizar operações a nível de bits em números inteiros. Os operadores bitwise atuam em cada bit individual de dois números e executam operações como deslocamento, AND, OR, XOR, entre outros.

**Os operadores bitwise são:**

* **'`&`' (AND)**: Retorna 1 para cada posição de bit em que ambos os operadores têm o bit 1.

  ``` go
    package main

    import "fmt"

    func main() {
        // Operação bitwise
        x := 5 // 0101 em binário
        y := 3 // 0011 em binário
        resultado := x & y // 0001 (1 em decimal)

        // Imprime o resultado da operação
        fmt.Println(resultado) // Output => 1
    }
  ```

* **'`|`' (OR)**: Retorna 1 para cada posição de bit em que pelo menos um dos operandos tem o bit 1.

  ``` go
    package main

    import "fmt"

    func main() {
        // Operação bitwise
        x := 5 // 0101 em binário
        y := 3 // 0011 em binário
        resultado := x | y // 0111 (7 em decimal)

        // Imprime o resultado da operação
        fmt.Printf("Biário: %b | Decimal: %d\n", resultado, resultado)
        // Output => Biário: 111 | Decimal: 7
    }
  ```

* **'`^`' (XOR)**: Retorna 1 para cada posição de bit em que apenas um dos operandos tem um bit 1.

  ``` go
    package main

    import "fmt"

    func main() {
        // Operação bitwise
        x := 5 // 0101 em binário
        y := 3 // 0011 em binário
        resultado := x ^ y // 0110 (6 em decimal)

        // Imprime o resultado da operação
        fmt.Printf("Biário: %b | Decimal: %d\n", resultado, resultado)
        // Output => Biário: 110 | Decimal: 6
    }
  ```

* **'`<<`' (Deslocamento à Esquerda)**: Move os bits dos números para a esquerda.

  ``` go
    package main

    import "fmt"

    func main() {
        // Operação bitwise
        x := 5 // 0101 em binário
        resultado := x << 2 // 10100 (20 em decimal)

        // Imprime o resultado da operação
        fmt.Printf("Biário: %b | Decimal: %d\n", resultado, resultado)
        // Output => Biário: 10100 | Decimal: 20
    }
  ```

* **'`>>`' (Deslocamento à Direita)**: Move os bits dos números para a direta.

  ``` go
    package main

    import "fmt"

    func main() {
        // Operação bitwise
        x := 5 // 0101 em binário
        resultado := x >> 2 // 0001 (1 em decimal)

        // Imprime o resultado da operação
        fmt.Println(resultado) // Output => 1
    }
  ```
