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

## Conversão entre Tipos

### Conversão para Inteiro

**Para converter um número de ponto flutuante para inteiro:**

``` go
package main

import "fmt"

func main() {
    // Valor float
    x := 5.13

    // Conversão para inteiro
    y := int(x)

    // Imprime o tipo e o valor após a conversão
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    // Output => Tipo: int | Valor: 5
}
```

**Para converter uma string para inteiro:**

``` go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Valor inteiro
    x := "5"

    // Conversão para string
    y, err := strconv.Atoi(x)

    // Verifica se ocorreu algum erro
    if err != nil {
        fmt.Println("Erro ao converter a string para inteiro:", err)
        return
    }

    // Imprime o tipo e o valor após a conversão
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    // Output => Tipo: int | Valor: 5
}
```

### Conversão para Float

**Para converter um inteiro para float:**

``` go
package main

import "fmt"

func main() {
    // Valor inteiro
    x := 5

    // Conversão para float
    y := float32(x)
    z := float64(x)

    // Imprime o tipo e o valor após a conversão
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    fmt.Printf("Tipo: %T | Valor: %v\n", z, z)
    // Output => Tipo: float32 | Valor: 5
    // Output => Tipo: float64 | Valor: 5
}
```

**Para converter uma string para float:**

``` go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Valor float
    x := "5.13"

    // Conversão para string
    y, err := strconv.ParseFloat(x, 64)

    // Verifica se ocorreu algum erro
    if err != nil {
        fmt.Println("Erro ao converter a string para float:", err)
        return
    }

    // Imprime o tipo e o valor após a conversão
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    // Output => Tipo: float64 | Valor: 5
}
```

### Conversão para String

Para converter qualquer tipo para string, pode-se usar `fmt.Sprintf()`.

``` go
package main

import "fmt"

func main() {
    // Valores que serão convertidos
    a := 5.13
    b := 8
    c := true

    // Valores convertidos para string
    x := fmt.Sprintf("%v", a)
    y := fmt.Sprintf("%v", b)
    z := fmt.Sprintf("%v", c)

    // Imprime o tipo e o valor das conversões
    fmt.Printf("Tipo: %T | Valor: %v\n", x, x)
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    fmt.Printf("Tipo: %T | Valor: %v\n", z, z)
    /* Output =>
    Tipo: string | Valor: 5.13
    Tipo: string | Valor: 8
    Tipo: string | Valor: true
    */
}
```

### Conversão para Booleano

Pode ser feito de maneira explícita:

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Valor inteiro
    x := 5

    // Conversão para booleano
    y := x > 0

    // Imprime o tipo e o valor após a conversão
    fmt.Printf("Tipo: %T | Valor: %v\n", y, y)
    // Output => Tipo: bool | Valor: true
}
```

## Input de Valores

### Com o Pacote `fmt`

Para capturar a entrada do usuário até o primeiro espaço em branco, pode ser utilizado **`fmt.Scan()`**, **`fmt.Scanf()`** ou **`fmt.Scanln()`**.

#### Função `fmt.Scan()`

Captura a entrada do usuário até o primeiro espaço em branco, independentemente do tipo de valor.

**Sintaxe:**

``` go
fmt.Scan(&variavel)
```

A função deve receber o endereço da variável, e por isso é usado o operador **`&`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Variável que receberá o input
    var nome string

    // Mensagem do input
    fmt.Print("Digite seu nome: ")

    // Pede um nome ao usuário
    fmt.Scan(&nome)

    // Imprime uma mensagem com o nome
    fmt.Printf("Olá, %s!\n", nome)
}
```

#### Função `fmt.Scanf()`

Similar a função `fmt.Scan()`, porém aceita apenas um tipo de entrada. A entrada permitida deve ser especifica por meio de um formatador, como `"%s"` ou `"%d"`.

**Sintaxe:**

``` go
fmt.Scanf(formatador, &variavel)
```

**Exemplo:**

``` go
package main

import (
    "fmt"
    "bufio"
    "os"
)

func LimparBuffer() {
    reader := bufio.NewReader(os.Stdin)
    _, _ = reader.ReadString('\n')
}

func main() {
    // Variável para os inputs
    var num1 int
    var num2 int

    // Pede um número ao usuário
    fmt.Print("Digite um número: ")
    fmt.Scanf("%d", &num1)

    // Limpa o buffer
    LimparBuffer()

    // Pede outro número ao usuário
    fmt.Print("Digite outro número: ")
    fmt.Scanf("%d", &num2)

    // Limpa o buffer
    LimparBuffer()

    // Imprime a soma dos números
    fmt.Printf("A soma entre %d e %d é %d\n", num1, num2, num1 + num2)
}
```

No código acima, a função **`LimparBuffer()`** é usada para ler uma linha de texto de entrada padrão e descartá-la. Isso é necessário para que na segunda entrada, não haja conflitos com a primeira.

A necessidade de limpar o buffer após uma entrada com `fmt.Scanf()` é por conta dessa função deixar uma quebra de linha no fim da entrada, afetando assim o próximo input, caso houver.

#### Função `fmt.Scanln()`

Funciona da mesma maneira que `fmt.Scan()`.

**Sintaxe:**

``` go
fmt.Scanln(&variavel)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Variável que receberá o nome
    var nome string

    // Mensagem para o input
    fmt.Print("Digite um nome: ")

    // Pede um nome ao usuário
    fmt.Scanln(&nome)

    // Mostra uma mensagem com o nome digitado
    fmt.Printf("Olá, %s!\n", nome)
}
```

### Com o Pacote `bufio`

O pacote `bufio` em conjunto com o pacote `os` permite ler entradas com mais de uma palavra.

**Sintaxe:**

``` go
scanner := bufio.NewScanner(os.Stdin) // Cria um scanner para leitura
scanner.Scan() // Lê uma linha da entrada do usuário
variavel := scanner.Text() // Retorna o texto lido da chamada anterior
```

**Exemplo:**

``` go
package main

import (
    "fmt"
    "bufio"
    "os"
)

func main() {
    // Scanner para ler a entrada do usuário
    scanner := bufio.NewScanner(os.Stdin)

    // Pede um texto ao usuário
    fmt.Print("Digite algo: ")

    // Lê a entrada do usuário
    scanner.Scan()

    // Obtém o texto digitado pelo usuário
    userInput := scanner.Text()

    // Exibe o texto
    fmt.Printf("Texto digitado: %s\n", userInput)
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

### Funções Variádicas

Uma função variádica é uma função que aceita uma quantidade valores variáveis por meio de um parâmetro. Esse parâmetro se torna uma slice.

Para declarar um parâmetro variádico, deve ser definido **`...`** antes do tipo de dado desse parâmetro.

**Sintaxe:**

``` go
func NomeFuncao(param1 tipo, paramVariadico ...tipo) {
    // Bloco da função
}
```

**Exemplo:**

``` go
package main

import "fmt"

func Sum(nums ...int) int {
    sum := 0
    for _, v := range nums {
        sum += v
    }
    return sum
}

func main() {
    fmt.Println("Soma:", Sum(1, 2, 3, 4, 5)) // Output => 15
    fmt.Println("Soma:", Sum(5, 2, 4)) // Output => 11
    fmt.Println("Soma:", Sum()) // Output => 0
}
```

No exemplo acima, a função `Sum` soma todos os valores que ela recebe, podendo a quantidade desses valores ser diferente em cada chamada da função.

> **OBS.:** O parâmetro para os valores variáveis deve ser o último parâmetro da função.

### Funções Anônimas

Também chamadas de "funções literais" ou "funções sem nome", são usadas para um único contexto no código (geralmente para callback) que não possuem nome.

**Sintaxe:**

``` go
// Função anônima
func(param1 tipo, param2 tipo, ..., paramN tipo) {
    // Bloco da função
}()

// Função anônima em uma variável
nomeFunc := func(param1 tipo, param2 tipo, ..., paramN tipo) {
    // Bloco da função
}
```

> **NOTA:** Ao atribuir uma função a uma variável, não é necessário adicionar parênteses no fim do bloco.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Função anônima
    func() {
        fmt.Println("Olá, Mundo!") // Output => Olá, Mundo!
    }()

    // Função anônima em uma variável
    myFunc := func() {
        fmt.Println("Olá, Go!")
    }

    // Chama a variável (que é uma função)
    myFunc() // Output => Olá, Go!
}
```

#### Closures

Um closure é uma função que pode referenciar variáveis do escopo onde foi definida, mesmo após a execução ter saído desse escopo.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    contador := func() func() int {
        count := 0
        return func() int {
            count++
            return count
        }
    }()

    fmt.Println(contador()) // Output => 1
    fmt.Println(contador()) // Output => 2
    fmt.Println(contador()) // Output => 3
}
```

No exemplo acima, `contador` é um closure que funciona como um contador, incrementando 1 sempre que chamado. `contador` é uma função que retorna uma outra função que retorna um inteiro, e nesse caso, deve haver os parênteses ao fim de `contador` para que a variável `count` seja inicializada.

### Callbacks

Um callback é passar uma função como argumento para outra função.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "math"
)

// Função callback
func RaizQuadrada(n float64) float64 {
    return math.Pow(n, 0.5)
}

// Função que aceita um callback
func MostrarResultado(n float64, callback func(float64) float64) {
    resultado := callback(n)
    fmt.Printf("A raiz quadrada de %.1f é %.1f\n", n, resultado)
}

func main() {
    MostrarResultado(25, RaizQuadrada)
    // Output => A raiz quadrada de 25.0 é 5.0
}
```

A função passada como argumento pode ser uma função anônima.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "math"
)

// Função que aceita um callback
func MostrarResultado(n float64, callback func(float64) float64) {
    resultado := callback(n)
    fmt.Printf("A raiz quadrada de %.1f é %.1f\n", n, resultado)
}

func main() {
    MostrarResultado(25, func(n float64) float64 {
        return math.Pow(n, 0.5)
    })
    // Output => A raiz quadrada de 25.0 é 5.0
}
```

## Structs

Estruturas são usadas para criar uma coleção de membros que pode ser composta por diferentes tipos de dados.

Diferente de arrays, que armazenam múltiplos dados do mesmo tipo em uma única variável, structs permitem armazenar vários tipos de dados em uma única variável.

Estruturas são declaradas com as palavra-chave **'`type`'** e **`struct`**. Nas estruturas, os identificadores dos valores são chamados de membros, e ao definí-los, deve ser especificado o tipo de dado que cada um deve receber.

**Sintaxe:**

``` go
type NomeEstrutura struct {
    membro1 tipoDeDado
    membro2 tipoDeDado
    membro3 tipoDeDado
    ...
    membroN tipoDeDado
}
```

Membros de estruturas são acessados por meio de notação de ponto, tanto para atribuição quanto para leitura.

**Exemplo:**

``` go
package main

import "fmt"

type Pessoa struct {
    nome string
    idade int
}

func main() {
    // Variável de estrutura
    var pessoa1 Pessoa

    // Atribuição de valores aos membros da estrutura
    pessoa1.nome = "João"
    pessoa1.idade = 23

    // Imprime os valores
    fmt.Printf("Nome: %s\n", pessoa1.nome)
    fmt.Printf("Idade: %d\n", pessoa1.idade)

    /* Output:
    Nome: João
    Idade: 23
    */
}
```

Também é possível declarar uma variável de estrutura de maneira inferida com **`:=`**. Dessa forma, devem ser passados os valores para os membros dentro de um bloco.

**Exemplo:**

``` go
package main

import "fmt"

type Pessoa struct {
    nome string
    idade int
}

func main() {
    // Variável de estrutura
    pessoa1 := Pessoa {
        nome: "João",
        idade: 23,
    }

    // Imprime os valores
    fmt.Printf("Nome: %s\n", pessoa1.nome)
    fmt.Printf("Idade: %d\n", pessoa1.idade)

    /* Output:
    Nome: João
    Idade: 23
    */
}
```

### Structs Anônimas

Também chamadas de "tipos embutidos", as estruturas anônimas são estruturas que não possui um nome explicitamente declarado. Em vez disso, ela é incorporada diretamente em outra estrutura ou tipo de dado.

**Sintaxe:**

``` go
func main() {
    nomeVariavel := struct {
        membro1 tipo
        membro2 tipo
        ...
        membroN tipo
    }{
        membro1: valor,
        membro2: valor,
        ...
        membroN: valor,
    }
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Estrutura anônima
    pessoa := struct {
        nome string
        idade int
    }{
        nome: "João",
        idade: 23,
    }

    // Imprime os valores
    fmt.Printf("Nome: %s\n", pessoa.nome)
    fmt.Printf("Idade: %d\n", pessoa.idade)

    /* Output:
    Nome: João
    Idade: 23
    */
}
```

**Struct dentro de uma struct anônima:**

``` go
package main

import "fmt"

type Pessoa struct {
    nome string
    idade int
}

func main() {
    // Estrutura anônima
    pessoa := struct {
        Pessoa
        msg string

    }{
        Pessoa: Pessoa {
            nome: "João",
            idade: 23,
        },
        msg: "Olá, Mundo!",
    }

    // Imprime os valores
    fmt.Printf("Nome: %s\n", pessoa.nome)
    fmt.Printf("Idade: %d\n", pessoa.idade)
    fmt.Printf("Mensagem: %s\n", pessoa.msg)

    /* Output:
    Nome: João
    Idade: 23
    Mensagem: Olá, Mundo!
    */
}
```

Structs anônimas são específicas ao escopo em que são declaradas, ou seja, elas são usadas localmente me funções ou como parte de outras structs, e não são declaradas globalmente.

## Maps

Armazenam dados em pares chave-valor. Maps são mutáveis e não permitem duplicidade de chaves.

Há algumas formas de criar um map:

**Com `var`:**

``` go
var nomeMap = map[tipoChave]tipoValor{
    chave1: valor1,
    chave2: valor2,
    ...,
    chaveN: valorN,
}
```

**Com `:=`:**

``` go
nomeMap := map[tipoChave]tipoValor{
    chave1: valor1,
    chave2: valor2,
    ...,
    chaveN: valorN,
}
```

**Com `make()`:**

``` go
var nomeMap = make(map[tipoChave]tipoValor)

// Ou

nomeMap := make(map[tipoChave]tipoValor)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var myMap = map[string]string{
        "z": "Exemplo1",
        "a": "Exemplo2",
        "c": "Exemplo3",
    }

    fmt.Println(myMap)
    // Output => map[a:Exemplo2 c:Exemplo3 z:Exemplo1]

}
```

Perceba que na saída os elementos são ordenados alfabeticamente.

Elementos em maps são acessados por meios de suas chaves, especificando-as com notação de colchetes.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map vazio
    myMap := make(map[string]string)

    // Atribui elementos ao map
    myMap["nome"] = "João"
    myMap["idade"] = "16"

    // Imprime os valores do map
    fmt.Printf("Nome: %s\n", myMap["nome"])
    fmt.Printf("Idade: %s\n", myMap["idade"])
    /* Output:
    Nome: João
    Idade: 16
    */
}
```

### Exclusão de Elementos em Maps

Um elemento de um map pode ser excluído a partir de sua chave com a função **`delete()`**.

**Sintaxe:**

``` go
delete(nomeMap, chave)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map com três elementos
    myMap := map[string]int{
        "num1": 5,
        "num2": 7,
        "num3": 9,
    }

    // Excluindo o elemento "num2"
    delete(myMap, "num2")

    // Imprime o map
    fmt.Println(myMap)
    // Output => map[num1:5 num3:9]
}
```

### Verificar se Chave Existe

Para verificar se uma chave existe dentro de um map, é feito o seguinte:

**Sintaxe:**

``` go
val, ok := nomeMap[chave]
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map com três elementos
    myMap := map[string]int{
        "num1": 5,
        "num2": 7,
        "num3": 9,
    }

    // Verifica a existência de algumas chaves
    val1, exist1 := myMap["num1"]
    val2, exist2 := myMap["num2"]
    val3, exist3 := myMap["num3"]
    val4, exist4 := myMap["num4"]

    // Imprime os resultados
    fmt.Println(val1, exist1) // Output => 5 true
    fmt.Println(val2, exist2) // Output => 7 true
    fmt.Println(val3, exist3) // Output => 9 true
    fmt.Println(val4, exist4) // Output => 0 false
}
```

Se não houver a necessidade do valor, pode substituir por **`_`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map com três elementos
    myMap := map[string]int{
        "num1": 5,
        "num2": 7,
        "num3": 9,
    }

    // Verifica a existência de algumas chaves
    _, exist1 := myMap["num1"]
    _, exist2 := myMap["num2"]
    _, exist3 := myMap["num3"]
    _, exist4 := myMap["num4"]

    // Imprime os resultados
    fmt.Println(exist1) // Output => true
    fmt.Println(exist2) // Output => true
    fmt.Println(exist3) // Output => true
    fmt.Println(exist4) // Output => false
}
```

### Cópia entre Maps

Não é possível copiar um map apenas atribuindo-o a uma outra variável.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map com três elementos
    map1 := map[string]int{
        "num1": 5,
        "num2": 7,
        "num3": 9,
    }

    // Declaração do segundo map
    map2 := map1

    // Substituindo um elemento
    map2["num1"] = 11

    // Imprime os maps
    fmt.Println(map1) // Output => map[num1:11 num2:7 num3:9]
    fmt.Println(map2) // Output => map[num1:11 num2:7 num3:9]
}
```

Como visto no exemplo acima, a "cópia" teve um elemento modificado, o map original também sofreu a alteração. Isso acontece porque maps são referências de hash tables, e dessa meneira, ambos os maps são referências de um mesmo hash table.

Para realmente copiar um map, pode-se iterar sobre ele e atribuir chave à chave para um novo map.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara um map com três elementos
    myMap := map[string]int{
        "num1": 5,
        "num2": 7,
        "num3": 9,
    }

    // Declaração do segundo map
    copyMap := map[string]int{}

    // Itera sobre o map original
    for k, v := range myMap {
        // Copia os elementos do map original para a cópia
        copyMap[k] = v
    }

    // Substitui um elemento de `copyMap`
    copyMap["num1"] = 11

    // Imprime os maps
    fmt.Println(myMap)   // Output => map[num1:5 num2:7 num3:9]
    fmt.Println(copyMap) // Output => map[num1:11 num2:7 num3:9]
}
```

## Interfaces

São tipos que especificam um conjunto de métodos que uma struct deve implementar para ser considerada uma instância desse tipo de interface.

**Sintaxe:**

``` go
type NomeInterface interface {
    Metodo1() tipo
    Metodo2() tipo
    ...
    MetodoN() tipo
}
```

Uma estrutura implementa uma interface se ela define todos os métodos listados na interface.

**Exemplo:**

``` go
package main

import "fmt"

// Estrutura vazia
type MyStruct struct{}

// Interface com 2 métodos
type MyInterface interface {
    OlaMundo()
    Soma(x, y int) int
}

// Define OlaMundo() como método da struct
func (s MyStruct) OlaMundo() {
    fmt.Println("Olá, Mundo!")
}

// Define Soma() como método da struct
func (s MyStruct) Soma(x, y int) int {
    return x + y
}

func main() {
    // Usa a função OlaMundo()
    MyStruct.OlaMundo(MyStruct{}) // Output => Olá, Mundo!

    // Usa a função Soma() e imprime o resultado dela
    resultadoSoma := MyStruct.Soma(MyStruct{}, 5, 2)
    fmt.Println(resultadoSoma) // Output => 7
}
```

Perceba que como primeiro argumento em ambos os métodos é definido `MyStruct{}`, isso está ali porque os métodos estão sendo acessados diretamente pela estrutura, e não por uma instância dela.

**Exemplo com instância de struct:**

``` go
package main

import "fmt"

// Estrutura vazia
type MyStruct struct{}

// Interface com 2 métodos
type MyInterface interface {
    OlaMundo()
    Soma(x, y int) int
}

// Define OlaMundo() como método da struct
func (s MyStruct) OlaMundo() {
    fmt.Println("Olá, Mundo!")
}

// Define Soma() como método da struct
func (s MyStruct) Soma(x, y int) int {
    return x + y
}

func main() {
    // Instância de `MyStruct`
    instanceStruct := MyStruct{}

    // Usa a função OlaMundo()
    instanceStruct.OlaMundo() // Output => Olá, Mundo!

    // Usa a função Soma() e imprime o resultado dela
    resultadoSoma := instanceStruct.Soma(5, 2)
    fmt.Println(resultadoSoma) // Output => 7
}
```

Uma interface serve basicamente como um modelo de métodos para structs.

**Exemplo:**

``` go
package main

import "fmt"

// Estrutura
type Numeros struct {
    num1, num2 int
}

// Interface com métodos para operações
type Operacoes interface {
    Soma() int // Soma os membros da struct
    Sub() int // Subtrai o primeiro membro da struct pelo segundo
    Mult() int // Multiplica os membros da struct
    Div() float64 // Divide o primeiro membro da struct pelo segundo
}

// Implementação do método Soma()
func (s Numeros) Soma() int {
    return s.num1 + s.num2
}

// Implementação do método Sub()
func (s Numeros) Sub() int {
    return s.num1 - s.num2
}

// Implementação do método Mult()
func (s Numeros) Mult() int {
    return s.num1 * s.num2
}

// Implementação do método Div()
func (s Numeros) Div() float64 {
    return float64(s.num1) / float64(s.num2)
}

func main() {
    // Variável de estrutura
    numeros := Numeros{5, 2}

    // Resultados das operações
    soma := numeros.Soma()
    subtracao := numeros.Sub()
    multiplicacao := numeros.Mult()
    divisao := numeros.Div()

    // Imprime os resultados
    fmt.Println("Soma:", soma) // Output => 7
    fmt.Println("Subtração:", subtracao) // Output => 3
    fmt.Println("Multiplicação:", multiplicacao) // Output => 10
    fmt.Println("Divisão:", divisao) // Output => 2.5
}
```

### Interfaces Vazias

Uma interface vazia (**`interface{}`**) não especifica nenhum método, o que significa que qualquer tipo implementa implicitamente a interface vazia.

Interfaces vazias podem ser usadas para criar estruturas de dados ou funções que podem armazenar ou manipular valores de tipos diversos. Isso é útil para lidar com dados de maneira genérica.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var valorGenerico interface{}

    // Atribui um valor inteiro à variável
    valorGenerico = 23
    fmt.Println(valorGenerico) // Output => 23

    // Atribui uma string à variável
    valorGenerico = "Olá, Mundo!"
    fmt.Println(valorGenerico) // Output => "Olá, Mundo!"
}
```

> **PITFALLS:** O uso excessivo de interfaces vazias pode tornar o código menos seguro e legível, pois a verificação de tipos é adiada para tempo de execução. O uso consciente e apropriado são essenciais para evitar potenciais armadilhas.

#### Reflexão (Reflection)

Geralmente as interfaces vazias são usadas em conjunto com o pacote **`reflect`** para realizar operações de reflexão em tempo de execuçã, permitindo inspecionar tipos de valores de maneira dinâmica.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "reflect"
)

func Tipo(v interface{}) reflect.Type {
    return reflect.TypeOf(v)
}

func main() {
    fmt.Println(Tipo(5)) // Output => int
    fmt.Println(Tipo(2.3)) // Output => float64
    fmt.Println(Tipo("Olá")) // Output => string
    fmt.Println(Tipo(false)) // Output => bool
}
```

No exemplo acima, a função `Tipo()` retorna o tipo de um valor.

## Ponteiros

São referências para valores na memória.

**Sintaxe:**

``` go
var ponteiro *tipo = &variavel
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Variável do tipo int
    x := 23

    // Ponteiro para a variável x
    var ponteiroInteiro *int = &x

    // Imprime o endereço de memória da variável x
    fmt.Println(ponteiroInteiro)
}
```

O operador **`&`** é usado para obter o endereço de memória de uma variável. No exemplo acima, é usado para obter o endereço de memória da variável `x`.

Um endereço de memória referencia o lugar onde uma variável está armazenada na memória. Esses endereços são representados por um número hexadecimal.

Em Go, a alocação de memória é gerenciada automaticamente pelo coletor de lixo (garbage collector), e por isso não há necessidade de explicitamente liberar a memória alocada.

### Operador de Desreferência

Quando usado em um ponteiro, o operador **`*`** procura pelo valor que esse ponteiro aponta.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Variável do tipo int
    x := 23

    // Ponteiro para a variável x
    var ponteiroInteiro *int = &x

    // Imprime o valor que o ponteiro aponta
    fmt.Println(*ponteiroInteiro) // Output => 23
}
```

### Ponteiro Nulo

Um ponteiro que não aponta para nenhum endereço é chamada de ponteiro nulo. Isso significa que um ponteiro que ainda não aponta para um endereço é **`nil`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Ponteiro nulo
    var ponteiroInteiro *int

    // Imprime o valor que o ponteiro aponta
    fmt.Println(ponteiroInteiro) // Output => <nil>
}
```

### Uso de Ponteiros

Ao usar ponteiros, é evitada a cópia de grandes blocos de dados, já que os ponteiros simplesmente referenciam a localização na memória. Isso é especialmente útil quando se trabalha com estruturas de dados grandes.

Além disso, ao passar um valor para uma função, normalmente é feita uma cópia desse valor. Porém, ao passar um ponteiro para o valor, a função pode modificar diretamente o valor na memória ao invés de operar em uma cópia local.

**Exemplo:**

``` go
package main

import "fmt"

func AlterarValor(x *int) {
    *x = 5
}

func main() {
    valor := 10
    AlterarValor(&valor)
    fmt.Println(valor) // Output => 5
}
```

## Time

O pacote **`time`** possui diversas funcionalidades para trabalhar com informações relacionadas ao tempo, como funções para representar e manipular datas, horários e durações.

### Constantes de `time`

**Constantes que representam tempo:**

* **'`Nanosecond`'**: Representa um nanossegundo.
* **'`Microsecond`'**: Representa um microssegundo.
* **'`Millisecond`'**: Representa um milissegundo.
* **'`Second`'**: Representa um segundo.
* **'`Minute`'**: Representa um minuto.
* **'`Hour`'**: Representa uma hora;

**Constantes para dias da semana:**

* **'`Sunday`'**: Representa domingo.
* **'`Monday`'**: Representa segunda-feira.
* **'`Tuesday`'**: Representa terça-feira.
* **'`Wednesday`'**: Representa quarta-feira.
* **'`Thursday`'**: Representa quinta-feira.
* **'`Friday`'**: Representa sexta-feira.
* **'`Saturday`'**: Representa sábado.

**Constantes para os meses:**

* **'`January`'**: Representa janeiro.
* **'`February`'**: Representa fevereiro.
* **'`March`'**: Representa março.
* **'`April`'**: Representa abril.
* **'`May`'**: Representa maio.
* **'`June`'**: Representa junho.
* **'`July`'**: Representa julho.
* **'`August`'**: Representa agosto.
* **'`September`'**: Representa setembro.
* **'`October`'**: Representa outubro.
* **'`November`'**: Representa novembro.
* **'`December`'**: Representa dezembro.

### Datas e Horários

Para representar uma datas e horários, são usadas funções.

* **'`Now()`'**: Retorna a data e hora atuais.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        dataAtual := time.Now() // Data e hora atuais
        fmt.Println(dataAtual) // Imprime a data e horas atuais
    }
    ```

* **'`Date()`'**: Cria uma data e horário específicos. A variável que armazena será uma instância de `time.Time`.

    Os argumentos são:

    1. Ano
    1. Mês
    1. Dia
    1. Horas
    1. Minutos
    1. Segundos
    1. Milisegundos
    1. Timezone

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Cria a data Data => 30/01/2005 13:22:04
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Imprime a data criada
        fmt.Println(data) // Output => 2005-01-30 13:22:04 +0000 UTC
    }
    ```

* **'`Parse()`'**: Converte uma string em uma instância `time.Time` usando um formato específico.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Data em string
        dataString := "2005-01-30T13:22:04Z"

        // Converte a data em string para uma instância `time.Time`
        data, err := time.Parse(time.RFC3339, dataString)

        // Verifica se houve um erro na conversão
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Imprime a data criada
        fmt.Println(data) // Output => 2005-01-30 13:22:04 +0000 UTC
    }
    ```

**Métodos de Instâncias `time.Time`:**

* **'`Format()`'**: Converte uma instância de `time.Time` em um formato específico.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Converte a instância `time.Time` para uma string
        dataFormatada := data.Format(time.RFC822)

        // Imprime a data criada
        fmt.Println(dataFormatada) // Output => 30 Jan 05 13:22 UTC
    }
    ```

* **'`Year()`'**: Retorna o ano da data.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Ano da data
        ano := data.Year()

        // Imprime o ano da data
        fmt.Println(ano) // Output => 2005
    }
    ```

* **'`Month()`'**: Retorna o mês da data.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Mês da data
        mes := data.Month()

        // Imprime o mês da data
        fmt.Println(mes) // Output => January
    }
    ```

* **'`Day()`'**: Retorna o dia da data.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Dia da data
        dia := data.Day()

        // Imprime o dia da data
        fmt.Println(dia) // Output => 30
    }
    ```

* **'`Weekday()`'**: Retorna o dia da semana da data.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Dia da semana da data
        diaSemana := data.Weekday()

        // Imprime o dia da semana da data
        fmt.Println(diaSemana) // Output => Sunday
    }
    ```

* **'`Add()`'**: Retorna uma nova data que é a soma entre `self` e um dado tempo.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 22, 4, 0, time.UTC)

        // Adiciona 2 dias a data
        novaData := data.Add(48 * time.Hour)

        // Imprime a nova data
        fmt.Println(novaData) // Output => 2005-02-01 13:22:04 +0000 UTC
    }
    ```

* **'`Sub()`'**: Retorna a diferença entre `self` e uma dada data.

    ``` go
    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        // Instância de `time.Time`
        data := time.Date(2005, time.January, 30, 13, 0, 0, 0, time.UTC)

        // Subtrai 2 dias da data
        novaData := data.Sub(time.Date(2005, time.January, 30, 9, 0, 0, 0, time.UTC))

        // Imprime a nova data
        fmt.Println(novaData) // Output => 4h0m0s
    }
    ```

#### Comparação entre Datas

As funções **`Equal()`**, **`Before()`** e **`After()`** verificam se `self` e igual, anterior ou posterior a uma dada data, retornando um valor booleano.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    // Instâncias de `time.Time`
    data1 := time.Date(2005, 05, 23, 12, 0, 0, 0, time.UTC)
    data2 := time.Date(2002, 03, 15, 13, 30, 0, 0, time.UTC)

    // Verifica a ordem das datas
    if data1.Equal(data2) {
        fmt.Println("As datas são iguais")
    } else if data1.Before(data2) {
        fmt.Println("A primeira data é anterior à segunda")
    } else { // Ou `data1.After(data2)`
        fmt.Println("A primeira data é posterior à segunda")
    }
}
```

### Duração

Com a função `Duration()` do pacote `time` é possível expressar durações para impressão ou como argumentos.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    duration := 5 * time.Second
    fmt.Println("Duração:", duration)
    // Output => Duração: 5s
}
```

### Espera na Execução

A função **`Sleep()`** do pacote `time` permite pausar a execução do programa por um determinado tempo.

**Sintaxe:**

``` go
time.Sleep(tempo)
```

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    for i := 10; i >= 0; i-- {
        fmt.Printf("%d ", i)
        time.Sleep(time.Second)
        if i == 0 {
            fmt.Println("FIM")
        }
    }
    // Imprime uma contagem regressiva
}
```

### Temporizadores

Um *timer* é usado para agendar a execução de uma determinada ação após um certo período de tempo.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    // Timer que dispara após 5 segundos
    timer := time.NewTimer(5 * time.Second)

    // Espera o temporizador expirar
    <-timer.C

    fmt.Println("Temporizador expirado!")
}
```

### Tickers

Um ticker é semelhante a um temporizador, mas ele dispara repetidamente em intervalos regulares até ser parado.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    // Ticker que dispara a cada segundo
    ticker := time.NewTicker(time.Second)

    // Executa a cada segundo
    i := 0
    for {
        <-ticker.C
        i++
        fmt.Printf("%d ", i)
        if i == 10 {
            fmt.Println("FIM")
            ticker.Stop() // Para o ticker
            break
        }
    }
}
```

> **NOTA:** Lembre-se de parar o ticker quando não for mais necessário para evitar vazamentos de recursos. Para parar um ticker, use o método **`Stop()`** no ticker.

## Concorrência

Concorrência refere-se à execução simultânea de tarefas ou processos independentes, onde a ordem de execução não é prioridade.

Em Go, a abordagem principal para a concorrência é baseada em goroutines e canais (channels).

### Goroutines

É uma função que é executada concorrentemente com outras goroutines.

São criadas a partir da palavra-chave **`go`** antes de chamar uma função. Isso inicia a execução da função em uma nova goroutine, permitindo que ela seja executada em paralelo com outras partes do programa.

**Sintaxe:**

``` go
// Função concorrente (goroutine)
func FuncaoConcorrente() {
    // Código da goroutine
}

func main() {
    // Chama a goroutine
    go FuncaoConcorrente()
}
```

Também é comum utilizá-las como funções anônimas.

``` go
func main() {
    // Chama a goroutine
    go func() {
        // Código da goroutine
    }()
}
```

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

// Função que imprime "Olá, Mundo!" a cada 1 segundo
func OlaMundo() {
    for {
        fmt.Println("Olá, Mundo!")
        time.Sleep(time.Second) // Espera 1 segundo
    }
}

func main() {
    go OlaMundo()

    // Entrada para encerrar
    fmt.Println("Pressione ENTER para encerrar")
    fmt.Scanln()
}
```

### Channels

Os canais são usados para a comunicação entre goroutines. Eles permitem que as goroutines enviem e recebam dados de forma segura e coordenada.

Um canal é declarado usando **`make`** e a função **`chan`**. A comunicação é feita através do operador **`<-`**, que pode ser usado para enviar e receber dados no canal.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

// Função que faz uma contagem progressiva
func Contagem(canal chan int) {
    cont := 0
    for {
        cont++
        canal <- cont
        time.Sleep(time.Second) // Espera 1 segundo antes de continuar
    }
}

// Função que imprime cada valor da contagem
func ImprimirContagem(canal chan int) {
    for {
        valor := <- canal
        fmt.Println(valor)
    }
}

func main() {
    // Canal
    canal := make(chan int)

    // Chama a contagem
    go Contagem(canal)

    // Chama a função para imprimir
    go ImprimirContagem(canal)

    // Entrada para encerrar
    fmt.Println("Pressione ENTER para encerrar")
    fmt.Scanln()
}
```

### Declaração `select`

É usado para lidar com várias operações de canal de forma concorrente. Ele permite que o programa aguarde várias comunicações de canal, escolhendo a primeira que estiver pronta.

**Sintaxe:**

``` go
select {
case msg1 := <- canal1:
    // Código
case msg2 := <- canal2:
    // Código
case msg3 := <- canal3:
    // Código
default:
    // Código
}
```

A sintaxe básica de `select` é semelhando a um bloco `switch`, mas em vez de avaliar condições de caso, o `select` lida com operações de canal.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "time"
)

// Função que faz uma contagem regressiva
func Contagem(canal chan int) {
    cont := 10
    for cont >= 0 {
        canal <- cont
        cont--
        time.Sleep(time.Second) // Espera 1 segundo antes de continuar
    }
    close(canal) // Fecha o canal
}

// Função que imprime cada valor da contagem
func ImprimirContagem(canal chan int) {
    for {
        select {
        case valor, ok := <- canal:
            if !ok {
                fmt.Println("Canal fechado...")
                return
            }
            fmt.Println(valor)
        case <- time.After(2 * time.Second):
            fmt.Println("TIMEOUT | Nenhuma mensagem após 2 segundos")
        }
    }
}

func main() {
    // Canal
    canal := make(chan int)

    // Chama a contagem
    go Contagem(canal)

    // Chama a função para imprimir
    go ImprimirContagem(canal)

    // Espera a execução das goroutines
    time.Sleep(15 * time.Second)
}
```

No exemplo acima, a goroutine `ImprimirContagem()` imprime o valor do canal depois de verificar se o canal foi fechado por meio da variável `ok`, atribuída por meio do próprio canal junto do valor desse canal. Se não houver nenhuma resposta por 2 segundos, é executado o segundo caso.

## Rand

O pacote **`math/rand`** é usado para gerar números pseudoaleatórios considerando uma semente.

**As principais funções são:**

* **'`Float64()`'**: Gera um número float aleatório no intervalo [0, 1).

* **'`Int()`'**: Gera um número inteiro aleatório.

* **'`Intn()`'**: Gera um número inteiro aleatório no intervalo [0, n).

* **'`Seed()`'**: Inicializa a fonte de números aleatórios com um valor semente.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "math/rand"
)

func main() {
    // Números aleatórios
    randomFloat := rand.Float64()
    randomInt := rand.Intn(10)

    // Imprime os resultados
    fmt.Println(randomFloat)
    fmt.Println(randomInt)
}
```

> **OBS.:** Números gerados pelo pacote `math/rand` não são adequados em situações que exigem segurança, como criptografia. Nesses casos, use `crypto/rand`.

## Expressões Regulares

As expressões regulares são implementas no pacote padrão **`regexp`**. Este pacote fornece funções para compilar e usar padrões de expressões regulares.

### Sintaxe de Expressões Regulares

#### Correspondência Literal

**Exemplo:**

``` go
// Corresponde à sequência literal "abc" na string "abcdef"
regexp.MatchString("abc", "abcdef")
```

#### Meta-caracteres

* **'`.`'**: Corresponde a qualquer caractere entre os dois caracteres que cercam o `.`.

    ``` go
    // Corresponde a qualquer caractere entre "a" e "c"
    regexp.MatchString("a.c", "abc")
    ```

* **'`*`'**: Corresponde a zero ou mais ocorrências do elemento anterior.

    ``` go
    // Corresponde a "ac", "abc", "abbc", etc
    regexp.MatchString("ab*c", "ac")
    ```

* **'`+`'**: Corresponde a uma ou mais ocorrências do elemento anterior.

    ``` go
    // Corresponde a "abc", "abbc", "abbbc", "etc
    regexp.MatchString("ab+c", "abbc")
    ```

* **'`?`'**: Torna o elemento anterior opcional (zero ou uma ocorrência).

    ``` go
    // Corresponde a "ac" ou "abc"
    regexp.MatchString("ab?c", "ac")
    ```

#### Classes de Caracteres

* **'`[abc]`'**: Corresponde a "a", "b" ou "c".
* **'`[^abc]`'**: Corresponde a qualquer caractere que não seja "a", "b" ou "c".
* **'`[a-z]`'**: Corresponde a qualquer caractere de  "a" a "z". O mesmo funciona para caracteres em maiúsculo (`[A-Z]`) e para números (`[0-9]`) .

#### Quantificadores

* **'`{n}`'**: Corresponde se houver n ocorrências do caractere anterior.

    ``` go
    // Corresponde a "aaa"
    regexp.MatchString("a{3}", "aaa")
    ```

* **'`{n,}`'**: Corresponde se houver pelo menos n ocorrências do caractere anterior.

    ``` go
    // Corresponde a "aaa", "aaaa", "aaaaa", etc
    regexp.MatchString("a{3,}", "aaaaa")
    ```

* **'`{n, m}`'**: Corresponde se o caractere anterior se repetir entre n e m.

    ``` go
    // Corresponde a "aa", "aaa", "aaaa" e "aaaaa"
    regexp.MatchString("a{2, 5}", "aaaaa")
    ```

#### Âncoras

* **'`^`'**: Corresponde se o padrão estiver no início da string.

    ``` go
    // Corresponde se a string se iniciar com "a"
    regexp.MatchString("^a", "abc")
    ```

* **'`$`'**: Corresponde se o padrão estiver no final da string.

    ``` go
    // Corresponde a qualquer string que terminar com "c"
    regexp.MatchString("c$", "abc")
    ```

#### Caracteces de Escape em RegExp

* **'`\`'**: Corresponde a um caractere de escape literal.

    ``` go
    regexp.MatchString("\\.", ".abc")
    ```

* **'`\b`'**: Corresponde à posição entre um caractere de palavra (como letras e números) e um caractere que não é uma palavra.

    ``` go
    // Corresponde a "Olá, Mundo!"
    regexp.MatchString(`\bMundo\b`, "Olá, Mundo!")
    ```

#### Grupos de Captura

* **'`()`'**: Agrupa caracteres, fazendo-os agir como se fosse um.

    ``` go
    // Corresponde a "abc", "abcabc", "abcabcabc", etc
    regexp.MatchString("(abc)+", "abcabcabc")
    ```

### Compilação de Expressões Regulares

Para começar a trabalhar com exmpressões regulares, é necessário compilar o padrão de expressão regular usando a função **`Compile()`**. Essa função retorna um objeto `*Regexp`, que pode ser usado para realizar operações de correspondência em strings.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    // Compila uma expressão regular para verificar se há letras
    regex, err := regexp.Compile(`[a-zA-Z]`)

    // Em caso de erro na compilação da expressão regular
    if err != nil {
        fmt.Println("Erro ao compilar a regexp:", err)
        return
    }

    // Verifica se há correspondência na string "Olá, Mundo!"
    match := regex.MatchString("Olá, Mundo!")
    fmt.Println(match) // Output => true
}
```

No exemplo acima, `regex` é um objeto `*Regexp` que posteriormente é usado para verificar se há letras em uma string com o método **`MatchString()`**.

> **NOTA:** Sempre que possível, reutilize objetos `*Regexp` para melhorar o desempenho, especialmente em cenários de alto uso.

Se houver a certeza de que a expressão regular está correta, você pode usar a função **`MustCompile()`** para compilar. Essa função assume que a expressão está correta e não retorna um erro.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    // Compila uma expressão regular para verificar se há letras
    regex := regexp.MustCompile(`[a-zA-Z]`)

    // Verifica se há correspondência na string "Olá, Mundo!"
    match := regex.MatchString("Olá, Mundo!")
    fmt.Println(match) // Output => true
}
```

#### `CompilePOSIX()`

É possível também compilar com a função **`CompilePOSIX()`**, que usa uma interpretação mais restrita, seguindo o padrão POSIX (Portable Operating System Interface). É considerada geralmente quando há requisitos específicos em relação a compatibilidade com POSIX ou precise de um conjunto de recursos mais restrito.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    // Compila uma expressão regular para verificar se há letras
    regex, err := regexp.CompilePOSIX(`[a-zA-Z]`)

    // Em caso de erro na compilação da expressão regular
    if err != nil {
        fmt.Println("Erro ao compilar a regexp:", err)
        return
    }

    // Verifica se há correspondência na string "Olá, Mundo!"
    match := regex.MatchString("Olá, Mundo!")
    fmt.Println(match) // Output => true
}
```

Assim como `MustCompile()`, há também a função **`MustCompilePOSIX()`** que não retorna um erro, pois assume que a expressão regular está correta.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    // Compila uma expressão regular para verificar se há letras
    regex := regexp.MustCompilePOSIX(`[a-zA-Z]`)

    // Verifica se há correspondência na string "Olá, Mundo!"
    match := regex.MatchString("Olá, Mundo!")
    fmt.Println(match) // Output => true
}
```

### Principais Métodos de `*Regexp`

* **'`MatchString()`'**: Verifica se a expressão regular corresponde a uma dada string.

    ``` go
    package main

    import (
        "fmt"
        "regexp"
    )

    func main() {
        // Expressão regular que verifica se a primeira letra é maiúcula
        regex, err := regexp.Compile(`[A-Z]`)

        // Veririca se há um erro na compilação
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Verifica se a expressão regular corresponde duas strings
        fmt.Println(regex.MatchString("Olá")) // Output => true
        fmt.Println(regex.MatchString("olá")) // Output => false
    }
    ```

* **'`FindString()`'**: Retorna a primeira correspondência da expressão regular na string fornecida.

    ``` go
    package main

    import (
        "fmt"
        "regexp"
    )

    func main() {
        // Expressão regular que verifica há a palavra "Mundo"
        regex, err := regexp.Compile(`Mundo`)

        // Veririca se há um erro na compilação
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Verifica se a expressão regular corresponde a uma string
        str := "Olá, Mundo!"
        match := regex.FindString(str)
        fmt.Println(match) // Output => Mundo
    }
    ```

* **'`FindAllString()`'**: Retorna todas as correspondências da expressão regular na string fornecida em um slice. Aceita um segundo argumento, que deve ser um valor inteiro relativo ao máximo de correspondências.

    ``` go
    package main

    import (
        "fmt"
        "regexp"
    )

    func main() {
        // Expressão regular
        regex, err := regexp.Compile(`lang`)

        // Veririca se há um erro na compilação
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Verifica se a expressão regular corresponde duas strings
        str := "Golang! Clang!"
        matches := regex.FindAllString(str, len(str))
        fmt.Println(matches) // Output => [lang lang]
    }
    ```

* **'`FindStringIndex()`'**: Retorna um slice de inteiros que contém os índices de início e fim da primeira ocorrência da expressão regular na string fornecida.

    ``` go
    package main

    import (
        "fmt"
        "regexp"
    )

    func main() {
        // Expressão regular
        regex, err := regexp.Compile(`lang`)

        // Veririca se há um erro na compilação
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Verifica se a expressão regular corresponde a uma string
        str := "Golang!"
        index := regex.FindStringIndex(str)
        fmt.Println(index) // Output => [2 6]
    }
    ```

* **'`ReplaceAllString()`'**: Substitui todas as correspondências da expressão regular na string fornecida pela segunda string fornecida.

    ``` go
    package main

    import (
        "fmt"
        "regexp"
    )

    func main() {
        // Expressão regular
        regex, err := regexp.Compile(`Mundo`)

        // Veririca se há um erro na compilação
        if err != nil {
            fmt.Println("Erro:", err)
            return
        }

        // Substitui uma palavra na string
        str := "Olá, Mundo!"
        replace := regex.ReplaceAllString(str, "Go")
        fmt.Println(replace) // Output => Olá, Go!
    }
    ```
