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

### Função `Sprintf()`

Formata um texto igual a função `Printf()`, mas ao invés de imprimir o texto, a função **`Sprintf()`** retorna o texto.

**Sintaxe:**

``` go
variavelParaOTexto := fmt.Sprintf(stringParaFormatar, formatador1, formatador2, ..., formatadorN)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Variáveis que serão formatadas
    x := 10
    y := 3

    // Formata o texto e o armazena em uma variável
    texto := fmt.Sprintf("A soma entre %d e %d é %d", x, y, x + y)

    // Imprime o texto formatado
    fmt.Println(texto) // Output => A soma entre 10 e 3 é 13
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

* **'`Split()`'**: Dada uma string e um separador, separa a string em uma slice de strings.

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

Para declarar uma slice, basta declarar um array sem especificar um tamanho fixo, deixando os colchetes vazios.

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

Como observado no exemplo acima, o comprimento de uma slice é determinado pela quantidade de elementos que ela armazena, ao contrário dos arrays, que têm um tamanho fixo.

### Criação de Slices

A função **`make()`** pode ser usada para criar uma slice.

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

A função **`len()`**, quando especificado uma slice, retorna a quantidade de elementos dentro dessa slice (comprimento da slice).

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

A função **`cap()`** retorna a capacidade de uma slice, que é o número de elementos que a slice pode aumentar.

``` go
package main

import "fmt"

func main() {
    // Criando uma slice
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

O termo *"slicing"* é usado para a ação de extrair partes de uma slice. É feito utilizando **`:`**.

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
    // Criando uma slice
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

### Adicionar Elementos a uma Slice

A função **`append()`** é usada para adicionar elementos a uma slice.

O primeiro argumento é a slice que será adicionada, e os próximos argumentos são os elementos a serem adicionados a esse slice.

É retornado uma nova slice contendo os elementos adicionados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando uma slice
    mySlice := []int{1, 2, 3, 4}

    // Nova slice com os elementos do anterior e um a mais
    novoSlice := append(mySlice[:], 5)

    // Imprime a slice antigo e o novo
    fmt.Println(mySlice)    // Output => [1 2 3 4]
    fmt.Println(novoSlice)  // Output => [1 2 3 4 5]
}
```

Geralmente é usado simplesmente para adicionar elementos a uma slice.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando uma slice
    mySlice := []int{1, 2, 3, 4}

    // Adicionando elementos à slice
    mySlice = append(mySlice[:], 5, 6, 7)

    // Imprime a slice
    fmt.Println(mySlice) // Output => [1 2 3 4 5 6 7]
}
```

Se ao invés de elementos for adicionada outra slice, é necessário definir **`...`** ao fim da slice.

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

### Remover Elementos de uma Slice

#### Remover Elemento por Índice

É usada a função **`append()`** junto a técnica "slicing" para remover um elemento por índice em um slice.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando uma slice
    mySlice := []int{1, 2, 3, 4, 5}

    // Índice do elemento a ser removido
    indexToRemove := 2

    // Remove o elemento da slice
    mySlice = append(mySlice[:indexToRemove], mySlice[indexToRemove + 1:]...)

    // Imprime a nova slice
    fmt.Println(mySlice) // Output => [1 2 4 5]
}
```

#### Remover Elemento por Valor

É feito criando uma nova slice e incluindo todos os elementos que não sejam o elemento a ser removido. Para isso, é usado um loop junto com **`append()`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Slice de exemplo
    mySlice := []int{1, 2, 3, 2, 4, 2, 5}

    // Elemento que será removido
    element := 2

    // Cria uma nova slice sem os elementos `2`
    var newSlice []int
    for _, v := range mySlice {
        if v != element {
            newSlice = append(newSlice, v)
        }
    }

    // Imprime a nova slice
    fmt.Println(newSlice) // Output => [1 3 4 5]
}
```

### Cópia entre Slices

A função **`copy()`** copia os elementos de uma slice para uma outra slice e retorna a quantidade de elementos copiados.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Criando uma slice
    mySlice := []int{1, 2, 3, 4, 5}

    // Slice que será a cópia
    newSlice := make([]int, 6)
    numElements := copy(newSlice, mySlice)

    // Imprime os slices
    fmt.Printf("Slice original: %v\n", mySlice)
    fmt.Printf("Elementos copiados: %d\n", numElements)
    fmt.Printf("Cópia da slice: %v\n", newSlice)

    /* Output =>
    Slice original: [1 2 3 4 5]
    Elementos copiados: 5
    Cópia da slice: [1 2 3 4 5 0]
    */
}
```

### Slices Multidimensionais

Slices multidimensionais são basicamente slices de slices.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Cria uma matriz bidimensional 3x3
    matriz := [][]int{
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9},
    }

    // Imprime a matriz
    fmt.Println(matriz)
    // Output => [[1 2 3] [4 5 6] [7 8 9]]
}
```

Além disso, é possível criar uma slice multidimensional vazia e preenchê-la depois.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Cria uma matriz bidimensional 3x3
    matriz := make([][]int, 3) // Linhas da matriz

    for i := 0; i < len(matriz); i++ {
        matriz[i] = make([]int, 3) // Colunas da matriz
    }

    // Preenche a matriz
    cont := 0
    for i := 0; i < len(matriz); i++ {
        for j := 0; j < cap(matriz); j++ {
            cont++
            matriz[i][j] = cont
        }
    }

    // Imprime a matriz
    fmt.Println(matriz)
    // Output => [[1 2 3] [4 5 6] [7 8 9]]
}
```

### Ordenação de Elementos em Slices

O pacote **`sort`** fornece funcionalidades para ordenar slices e arrays.

* **'`Ints()`'**: Ordena uma slice de inteiros.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myIntSlice := []int{5, 2, 1, 3, 4}

        // Ordenando a slice
        sort.Ints(myIntSlice)

        // Imprime a slice ordenada
        fmt.Println(myIntSlice) // Output => [1 2 3 4 5]
    }
    ```

* **'`Float64s`'**: Ordena uma slice de `float64`.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myFloatSlice := []float64{5.4, 5.2, 5.1, 5.5, 5.3}

        // Ordenando a slice
        sort.Float64s(myFloatSlice)

        // Imprime a slice ordenada
        fmt.Println(myFloatSlice) // Output => [5.1 5.2 5.3 5.4 5.5]
    }
    ```

* **'`Strings`'**: Ordena uma slice de strings.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myStrSlice := []string{"Go", "Python", "Ruby", "C++"}

        // Ordenando a slice
        sort.Strings(myStrSlice)

        // Imprime a slice ordenada
        fmt.Println(myStrSlice) // Output => [C++ Go Python Ruby]
    }
    ```

* **'`IntsAreSorted()`'**: Retorna verdadeiro se uma dada slice de inteiros estiver ordenada.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myIntSlice := []int{1, 2, 3, 4, 5}

        // Verifica se a slice está ordenada
        ordenado := sort.IntsAreSorted(myIntSlice)

        fmt.Println(ordenado) // Output => true
    }
    ```

* **'`Float64AreSorted()`'**: Retorna verdadeiro se uma dada slice do tipo `float64` estiver ordenada.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myFloatSlice := []float64{5.1, 5.2, 5.3, 5.4, 5.5}

        // Verifica se a slice está ordenada
        ordenado := sort.Float64sAreSorted(myFloatSlice)

        fmt.Println(ordenado) // Output => true
    }
    ```

* **'`StringAreSorted()`'**: Retorna verdadeiro se um dada slice de strings estiver ordenada.

    ``` go
    package main

    import (
        "fmt"
        "sort"
    )

    func main() {
        // Criando uma slice
        myStrSlice := []string{"C++", "Go", "Python", "Ruby"}

        // Verifica se a slice está ordenada
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

### Operadores de Atribuição

O operador de atribuição mais comum é **`=`**, mas também há outros operadores que realizam uma operação e armazenam o resultado na variável.

**Os operadores de atribuição são:**

* **'`=`'**: Atribui o valor à variavel.
* **'`+=`'**: Soma um valor à variável.
* **'`-=`'**: Subtrai um valor da variável.
* **'`*=`'**: Multiplica a variável por um valor.
* **'`/=`'**: Divide a variável por um valor.
* **'`%=`'**: Calcula o resto da divisão da variável pelo valor e atribui o resultado à variável.
* **'`&=`'**: Realiza a operação bit a bit AND com a variável e o valor, e então atribui o resultado à variável.
* **'`|=`'**: Realiza a operação bit a bit OR com a variável e o valor, e então atribui o resultado à variável.
* **'`^=`'**: Realiza a operação bit a bit XOR com a variável e o valor, e então atribui o resultado à variável.
* **'`<<=`'**: Desloca os bits da variável para a esquerda na mesma quantidade de vezes do valor.
* **'`>>=`'**: Desloca os bits da variável para a direita na mesma quantidade do valor.

## Estruturas de Repetição

Em Go, **`for`** é o único loop, podendo ser usado para diferentes casos.

**Sintaxe:**

``` go
for variavelInicial; condicao; incremento
```

* **'`variavelInicial`'**: Inicia uma variável.
* **'`condicao`'**: É analisada em toda iteração do loop, encerrando o loop quando se torna falsa.
* **'`incremento`'**: Incrementa a variável iniciada a cada iteração do loop.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Printf("%d ", i)
    }
    // Output => 0 1 2 3 4
}
```

### Palavra-chave `break`

A palavra-chave **`break`** sai de um loop imediatamente.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 { break }
        fmt.Printf("%d ", i)
    }
    // Output => 0 1 2 3 4
}
```

No exemplo acima, o loop é encerrado quando a variável de inicialização se torna 5.

### Palavra-chave `continue`

A palavra-chave **`continue`** pula para a próxima iteração do loop.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i % 2 != 0 { continue }
        fmt.Printf("%d ", i)
    }
    // Output => 0 2 4 6 8
}
```

No exemplo acima, é pulado para a príxima iteração toda vez que a variável de inicialização for ímpar.

### Loop apenas com Condição

Um loop **`for`** com apenas condições executa até que a condição se torne falsa ou o loop seja interrompido com `break`.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    cont := 0
    for cont < 5 {
        fmt.Printf("%d ", cont)
        cont++
    }
    // Output => 0 1 2 3 4
}
```

### Loop Infinito

Declarar **`for`** sem mais outras declarações, resultará em um loop infinito que só se encerrará com `break`.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    cont := 0
    for {
        fmt.Printf("%d ", cont)
        cont++
        if cont == 5 { break }
    }
    // Output => 0 1 2 3 4
}
```

### Loop com `range`

Para iterar sobre strings, arrays, slices, maps ou canais, são declaradas variáveis de índice e valor junto à declaração `for`.

**Sintaxe:**

``` go
for indice, valor := range array {
    // Bloco de código
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    mySlice := []int{1, 2, 3, 4, 5}
    for i, v := range mySlice {
        fmt.Printf("Índice: %d | Valor: %v\n", i, v)
    }
    /* Output:
    Índice: 0 | Valor: 1
    Índice: 1 | Valor: 2
    Índice: 2 | Valor: 3
    Índice: 3 | Valor: 4
    Índice: 4 | Valor: 5
    */
}
```

Quando o índice não for necessário para a lógica do código, deve ser definido **`_`** (underline) ao invés do nome para a variável de índice.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    mySlice := []int{1, 2, 3, 4, 5}
    for _, v := range mySlice {
        fmt.Printf("Valor: %v\n", v)
    }
    /* Output:
    Valor: 1
    Valor: 2
    Valor: 3
    Valor: 4
    Valor: 5
    */
}
```

## Estruturas Condicionais

### Estruturas `if`, `else` e `else if`

#### Declaração `if`

Uma estrutura condicional é iniciada com a declaração **`if`**, e após ele uma condição e um bloco de código. O bloco de código só irá executar se a condição for verdadeira.

**Sintaxe:**

``` go
if condicao {
    // Bloco que executa quando a `condicao` for `true`
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := true
    if x {
        fmt.Println("Olá, Mundo!")
    }
    // Output => Olá, Mundo!
}
```

#### Declaração `else`

Além de `if`, há também a declaração **`else`**, que executa quando o `if` não é verdadeiro.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := false
    if x {
        fmt.Println("Olá, Mundo!")
    } else {
        fmt.Println("Olá, Go!")
    }
    // Output => Olá, Go!
}
```

> **OBS.:** Em uma estrutura condicinal só pode haver um `else`.

#### Declaralção `else if`

E por fim, há a declaração **`else if`**, que funciona como o `if`, mas só é verificada se as condições acima dela forem falsas.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 2
    if x == 1 {
        fmt.Println("Olá, Mundo!")
    } else if x == 2 {
        fmt.Println("Olá, Go!")
    } else {
        fmt.Println("Valor diferente de 1 e 2")
    }
    // Output => Olá, Go!
}
```

> **OBS.:** Em uma estrutura condicional pode haver vários `else if`.

### Estrutura `switch`

Executa um bloco dentre vários, baseando-se no valor de uma dada variável ou expressão.

Para cada possível valor de uma expressão, é criado um **`case`**, e no fim é criado um **`default`** caso nenhum `case` seja executado.

**Sintaxe:**

``` go
switch expressao {
case opcao1:
    // Executa caso o valor de `expressao` seja `opcao1`
case opcao2:
    // Executa caso o valor de `expressao` seja `opcao2`
...
case opcaoN:
    // Executa caso o valor de `expressao` seja `opcaoN`
default:
    // Executa quando nenhum caso acima é executado
}
```

> **OBS.:** O valor de cada `case` deve ser do mesmo tipo da expressão, ou será lançado um erro.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 3

    switch x {
    case 1:
        fmt.Println("x é igual a 1")
    case 2:
        fmt.Println("x é igual a 2")
    case 3:
        fmt.Println("x é igual a 3")
    default:
        fmt.Println("x é diferente de 1, 2 e 3")
    }
    // Output => x é igual a 3
}
```

#### Múltiplos Valores para `case`

Um `case` pode receber mais de um valor, e assim, permitindo executar um único bloco para diferentes valores, sem a necessidade de duplicar blocos.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 3

    switch x {
    case 1, 2, 3:
        fmt.Println("x é igual a 1, 2 ou 3")
    default:
        fmt.Println("x não é igual a 1, 2 e 3")
    }
    // Output => x é igual a 3
}
```

## Funções

São criadas a partir da palavra-chave **`func`**, seguida de parênteses e um bloco de código.

**Sintaxe:**

``` go
func NomeFuncao() {
    // Bloco da função
}
```

Para **chamar uma função**, basta escrever o nome dela com os parênteses.

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func OlaMundo() {
    fmt.Println("Olá, Mundo!")
}

func main() {
    OlaMundo() // Chama a função
    // Output => Olá, Mundo!
}
```

A função acima imprime "Olá, Mundo!".

### Regras para Nomes de Funções

* São case-sensitive.
* Devem se iniciar com um letra.
* Podem conter apenas caracteres alfanuméricos e `_`.
* Geralmente são escritas em PascalCase.

### Parâmetros e Argumentos

**Sintaxe:**

``` go
func NomeFuncao(param1 tipo, param2 tipo, ..., paramN tipo) {
    // Bloco da função
}
```

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func DigaOla(nome string) {
    fmt.Printf("Olá, %s!\n", nome)
}

func main() {
    DigaOla("Mundo") // Chama a função
    // Output => Olá, Mundo!
}
```

**Exemplo com múltiplos parâmetros:**

``` go
package main

import "fmt"

// Declaração de função
func Soma(x int, y int) {
    fmt.Printf("A soma entre %d e %d é %d\n", x, y, x + y)
}

func main() {
    Soma(5, 2) // Chama a função
    // Output => A soma entre 5 e 2 é 7
}
```

> **NOTA:** Ao chamar uma função, ela deve receber o mesmo número de argumentos em relação aos parâmetros.

### Retorno de Valores

Funções que retornam valores devem ser declaradas com o tipo de valor que elas retornam. Para retornar valores, é usada a palavra-chave **`return`**.

**Sintaxe:**

``` go
func NomeFuncao() tipoRetorno {
    // Bloco de código
    return valor
}
```

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func Multiplicar(x int, y int) int {
    return x * y
}

func main() {
    resultado := Multiplicar(5, 2) // Chama a função
    fmt.Printf("Resultado da multiplicação: %d\n", resultado)
    // Output => Resultado da multiplicação: 10
}
```

#### Nomear Valores de Retorno

É possível nomear valores de retorno.

**Sintaxe:**

``` go
func NomeFuncao() (nomeValorRetorno tipo) {
    // Bloco da função
    return
}
```

Basicamente, `nomeValorRetorno` é uma variável do tipo especificado que será retornada quando chamado `return`.

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func Multiplicar(x int, y int) (resultado int) {
    resultado = x * y
    return resultado
}

func main() {
    resultado := Multiplicar(5, 2) // Chama a função
    fmt.Printf("Resultado da multiplicação: %d\n", resultado)
    // Output => Resultado da multiplicação: 10
}
```

Mesmo que haja o retorno nomeado em uma função, é possível retornar valores que não sejam esse retorno nomeado.

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func Multiplicar(x int, y int) (resultado int) {
    resultado = x * y
    return x + y
}

func main() {
    resultado := Multiplicar(5, 2) // Chama a função
    fmt.Printf("Resultado da multiplicação: %d\n", resultado)
    // Output => Resultado da multiplicação: 7
}
```

No exemplo acima, mesmo que a função multiplique `x` e `y`, ela retorna a soma deles.

#### Retono Múltiplo de Valores

Para retornar mais de um valor, é necessário que esses valores sejam nomeados previamente.

**Sintaxe:**

``` go
func NomeFuncao() (valor1 tipo, valor2 tipo) {
    // Bloco da função
    return
}
```

Para utilizá-los, é necessário declarar duas variáveis.

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func SomarEMultiplicar(x int, y int) (soma int, mult int) {
    soma = x + y
    mult = x * y
    return
}

func main() {
    resultadoSoma, ResultadoMult := SomarEMultiplicar(5, 2) // Chama a função

    // Imprime os resultados
    fmt.Printf("Resultado da soma: %d\n", resultadoSoma)
    fmt.Printf("Resultado da multiplicação: %d\n", ResultadoMult)
    /* Output
    Resultado da soma: 7
    Resultado da multiplicação: 10
    */
}
```

Se não for necessário o uso dos dois valores, você pode substituir a variável desse respectivo valor por **`_`**.

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func SomarEMultiplicar(x int, y int) (soma int, mult int) {
    soma = x + y
    mult = x * y
    return
}

func main() {
    _, ResultadoMult := SomarEMultiplicar(5, 2) // Chama a função

    // Imprime o resultado da multiplicação
    fmt.Printf("Resultado da multiplicação: %d\n", ResultadoMult)
    // Output => Resultado da multiplicação: 10
}
```

### Funções de Recursão

Uma função de recursão é uma função que chama ela mesma até atingir um ponto de parada (condição).

**Exemplo:**

``` go
package main

import "fmt"

// Declaração de função
func SomarEMultiplicar(x int, y int) (soma int, mult int) {
    soma = x + y
    mult = x * y
    return
}

func main() {
    _, ResultadoMult := SomarEMultiplicar(5, 2) // Chama a função

    // Imprime o resultado da multiplicação
    fmt.Printf("Resultado da multiplicação: %d\n", ResultadoMult)
    // Output => Resultado da multiplicação: 10
}
```

O exemplo acima imprime "Olá, Mundo!" na mesma quantidade definida no argumento da função quando chamada.

**Exemplo de cálculo de fatorial:**

``` go
package main

import "fmt"

// Função que calcula o fatorial
func Fatorial(valor int) (resultado int) {
    if valor > 0 {
        resultado = valor * Fatorial(valor - 1)
    } else {
        resultado = 1
    }

    return
}

func main() {
    valor := 5
    resultado := Fatorial(5) // Chama a função
    fmt.Printf("%d! = %d\n", valor, resultado)
    // Output => 5! = 120
}
```

No exeplo acima, a função `Fatorial` é uma função de recursão que percorre do valor dado até 1, e então retorna o resultado acumulado de todas as "iterações".

> **OBS.:** Chamadas excessivas de funções recursivas pode levar a uma redução de desempenho, podendo ser mais útil utilizar um loop nessas situações.
