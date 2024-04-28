# Go

## Sintaxe Básica

Um código Go possui três áreas principais.

1. Declaração do pacote
1. Importação de pacotes
1. Funções

**Exemplo:**

``` Go
package main

import "fmt"

func main() {
  fmt.Println("Hello, World!")
}
```

A função **`main()`** é chamada assim que o código é executado. Essa função só pode existir em um arquivo Go se o arquivo for declarado como parte do pacote `main`, ou ele simplesmente não irá executar.

Na função `main()` acima, é executado `fmt.Println("Hello, World!)`, que imprime "Hello, World!" utilizando a função `Println()`, que por sua vez pertence ao pacote **`fmt`**.

**Para rodar o código:**

``` bash
go run diretorio_do_arquivo.go
```

> **NOTA:** Se o arquivo de dependência (`.mod`) existir, é possível executar o código com **`go run .`** caso ele esteja no mesmo diretório.

### Comentários

Há dois tipos de comentários:

* **`//`**: Comentário de linha única.
* **`/**/`**: Comentário de múltiplas linhas.

**Exemplo:**

``` go
// Isso é um comentário

/* Isso também
é um comentário */
```

### Declarações

Uma declaração em Go é finalizada assim que há uma quebra de linha.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!") // Isso é uma declaração
    fmt.Println("Hello, Go!")    // Isso é outra declaração
}
```

Outra maneira de finalizar declarações é utilizando **`;`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Duas declarações em uma única linha
    fmt.Println("Foo!"); fmt.Println("Bar!")
}
```

## Variáveis

Variáveis com tipos definidos na declaração são declaradas com a palavra-chave **`var`**, seguida do nome e tipo da variável.

**Sintaxe:**

``` go
var nomeVariavel tipo
```

**Os principais tipos são:**

* **'`int`'**: Representa valores inteiros.
* **'`float32`'** e **`float64`**: Representam valores de ponto flutuante (reais).
* **'`string`'**: Representa strings.
* **'`bool`'**: Representa valores booleanos.

Declarar uma variável significa reservar um espaço na memória para um valor que pode mudar durante a execução do programa, e para atribuir ou alterar o valor de uma variável, é usado o operador **`=`**.

> **NOTA:** Ocorrerá um erro caso haja a tentativa de atribuir um valor de tipo diferente da variável. Por exemplo, tentar atribuir uma string a uma variável do tipo `int`.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara a variável `msg` do tipo string
    var msg string

    // Atribui um valor à variável e a imprime
    msg = "Hello, World!"
    fmt.Println(msg) // -> Hello, World!

    // Altera o valor da variável e a imprime
    msg = "Hello, Go!"
    fmt.Println(msg) // -> Hello, Go!
}
```

É possível também atribuir um valor à variável no mesmo momento de declaração da mesma.

**Sintaxe:**

``` go
var nomeVariavel tipo = valor
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var msg string = "Hello, World!"
    fmt.Println(msg) // -> Hello, World!
}
```

### Tipagem Automática

Também chamada de **inferência de tipo**, a tipagem automática permite declarar uma variável sem especificar o tipo, deixando esse trabalho para o compilador. O compilador irá considerar o valor atribuído à variável para definir o tipo dela.

Para essas variáveis, deve-se atribuir um valor no momento de sua declaração, e além disso, deve ser usado o operador **`:=`**.

**Sintaxe:**

``` go
nomeVariavel := valor
```

Para alterar o valor dessas variáveis, é usado o operador de atribuição comum (**`=`**).

> **NOTA:** Também é possível declarar variáveis automaticamente tipadas com `var nomeVariavel = valor`, só que menos comum.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // Declara a variável do tipo string (pois seu valor é uma string)
    msg := "Hello, World!"

    // Imprime a variável
    fmt.Println(msg) // -> Hello, World!

    // Altera o valor da variável e a imprime
    msg = "Hello, Go!"
    fmt.Println(msg) // -> Hello, Go!
}
```

> **NOTA:** Com exceção da declaração, variáveis comuns e variáveis automaticamente tipadas são exatamente iguais.

### Nomes para Variáveis

Existem algumas regras para nomear variáveis:

* Devem iniciar com uma letra ou `_`.
* Podem conter caracteres alfanuméricos e underlines (`a-Z`, `0-9`, `_`).
* São case-sensitive, ou seja, caracteres maiúsculos e minúsculos são diferentes (`x` é diferente de `X`).

Além disso, normalmente as variáveis em Go são escritas em *camelCase*, onde a primeira palavra é escrita inteiramente em letras minúsculas, e a primeira letra das próximas palavras são escritas em maiúsculas.

### Declaração Múltipla de Variáveis

É possível declarar várias variáveis em uma única linha, e para isso, é necessário separá-las com vírgula.

**Sintaxe:**

``` go
var x, y, z tipo
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x, y, z int = 5, 7, 2
    fmt.Println(x) // -> 5
    fmt.Println(y) // -> 7
    fmt.Println(z) // -> 2
}
```

É possível também declarar múltiplas variáveis com valores de tipos diferentes entre elas, utilizando assim, variáveis automaticamente tipadas.

**Sintaxe:**

``` go
x, y, z := valorX, valorY, valorZ
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x, y, z := 1.2, 5, "Hello"
    fmt.Println(x) // -> 1.2
    fmt.Println(y) // -> 5
    fmt.Println(z) // -> "Hello"
}
```

> **NOTA:** As mesmas variáveis acima podem ser declaradas com `var x, y, z = 1.2, 5, "Hello"`.

Outra maneira de declarar múltiplas variáveis ao mesmo tempo, é utilizando `var ()`, onde `()` é um bloco que irá declarar as variáveis.

**Sintaxe:**

``` go
var (
    x tipo = valorX
    y tipo = valorY
    z tipo = valorZ
)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var (
        x float32 = 1.2
        y int     = 5
        z string  = "Hello"
    )
    fmt.Println(x) // -> 1.2
    fmt.Println(y) // -> 5
    fmt.Println(z) // -> "Hello"
}
```

### Declaração de Variáveis Fora de Funções

É possível declarar variáveis fora de qualquer função, o que torna ele uma variável global - o que significa que ela pode ser usada e modificada em qualquer lugar do código.

**Exemplo:**

``` go
package main

import "fmt"

var msg = "Hello, World!"

func main() {
    fmt.Println(msg)
}
```

> No exemplo acima, a variável é automaticamente tipada, no entanto, não é possível declarar variáveis automaticamente tipadas omitindo `var` e utilizando o operador `:=`.

## Constantes

Constantes são como variáveis, porém seus valores não podem ser alterados uma vez que definidos em sua declaração.

São declaradas a partir da palavra-chave **`const`**, seguida do nome e o valor da constante.

**Sintaxe:**

``` go
// Constante tipada
const NOMECONST tipo = valor

// Constante automaticamente tipada
const NOMECONST = valor
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    const PI = 3.14159
    fmt.Println(PI) // -> 3.14159
}
```

> **NOTA:** Tentar modificar o valor de uma constante irá resultar em um erro.

### Nomes para Constantes

As regras para nomear constantes são as mesmas que para variáveis. Normalmente, os nomes para constantes são escritos com todas as letras em maiúsculas.

### Declaração Múltipla de Constantes

A declaração múltipla de constantes é feita da mesma maneira que para variáveis.

**Sintaxe:**

``` go
const X, Y, Z tipo = valorX, valorY, valorZ
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    const X, Y, Z int = 5, 7, 2
    fmt.Println(X) // -> 5
    fmt.Println(Y) // -> 7
    fmt.Println(Z) // -> 2
}
```

**Para constantes automaticamente tipadas:**

``` go
package main

import "fmt"

func main() {
    const X, Y, Z = 5, 9.7, "Hello"
    fmt.Println(X) // -> 5
    fmt.Println(Y) // -> 9.7
    fmt.Println(Z) // -> Hello
}
```

**Para múltipla declaração com bloco `const ()`:**

``` go
package main

import "fmt"

func main() {
    const (
        X int     = 5
        Y float32 = 9.7
        Z string  = "Hello"
    )
    fmt.Println(X) // -> 5
    fmt.Println(Y) // -> 9.7
    fmt.Println(Z) // -> Hello
}
```

### Declaração de Constantes Fora de Funções

Assim como com as variáveis, é possível declarar constantes fora de qualquer função, tornando-as globais.

**Exemplo:**

``` go
package main

import "fmt"

const MSG = "Hello, World!"

func main() {
    fmt.Println(MSG)
}
```

## Saída

Saída se refere a impressão de dados na tela, e pode se feito de várias maneiras. O pacote `fmt` fornece três funções que imprimem valores na saída padrão (`stdout`).

* **`Println()`**
* **`Print()`**
* **`Printf()`**

### Função `fmt.Println()`

Imprime os valores de seus argumentos e, no fim, adiciona uma quebra de linha (`\n`).

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    s1 := "Hello"
    s2 := "World"
    fmt.Println(s1) // -> Hello
    fmt.Println(s2) // -> World
}
```

Essa função aceita múltiplos argumentos para impressão, separando-os com um espaço e quebrando a linha no final.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    s1 := "Hello"
    s2 := "World"
    fmt.Println(s1, s2) // -> Hello World
}
```

### Função `fmt.Print()`

Imprime os valores de seus argumentos sem quebrar a linha no final.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    s1 := "Hello"
    s2 := "World"
    fmt.Print(s1) // -> Hello
    fmt.Print(s2) // -> World

    // O output final será: HelloWorld
}
```

Também aceita múltiplos argumentos, mas ao contrário de `fmt.Println()`, não os separa a não ser que os valores não sejam strings - ou seja, se o próximo argumento não for uma string, ele irá separar com um espaço.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    fmt.Print("Hello", ", ") // -> Hello,
    fmt.Print("World", "!")  // -> World!
    // O output final será: Hello, World!
}
```

### Função `fmt.Printf()`

A função **`fmt.Printf()`** permite formatar os valores antes de imprimir.

**Principais formatadores:**

* **'`%v`'**: Imprime o valor do argumento.
* **'`%T`'**: Imprime o tipo do argumento.

Antes da impressão, os formatadores são substituídos pelo valor ou tipo de seu respectivo argumento.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x, y, z := "Hello", 15, true
    fmt.Printf("Valor: %v | Tipo: %T\n", x, x) // -> Valor: Hello | Tipo: string
    fmt.Printf("Valor: %v | Tipo: %T\n", y, y) // -> Valor: 15 | Tipo: int
    fmt.Printf("Valor: %v | Tipo: %T\n", z, y) // -> Valor: true | Tipo: int
}
```

## Tipos de Dados

Em Go, os tipos de dados básicos são:

* **'`int`'**: Representa números inteiros.
* **'`float32`', '`float64`'**: Representam números de ponto flutuante (números reais).
* **'`complex64`', '`complex128`'**: Representam números complexos.
* **'`string`'**: Representa uma string (cadeia de caracteres).
* **'`bool`'**: Representa um valor booleano.

### Inteiros

O tipo **`int`** é maneira mais simples de representar números inteiros, e seu tamanho varia de acordo com a arquitetura da máquina.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    myInt := 23
    fmt.Printf("Valor: %v | Tipo: %T\n", myInt, myInt)
    // -> Valor: 23 | Tipo: int
}
```

#### Inteiros com Tamanho Específico

Existem vários tipos de inteiros, onde cada tipo possui um limite diferente de valores.

**Os tipos são:**

* **'`int8`'**: Representa números inteiros com o tamanho de 8 bits.
* **'`int16`'**: Representa números inteiros com o tamanho de 16 bits.
* **'`int32`'**: Representa números inteiros com o tamanho de 32 bits.
* **'`int64`'**: Representa números inteiros com o tamanho de 64 bits.

``` go
var inteiro8  int8
var inteiro16 int16
var inteiro32 int32
var inteiro64 int64
```

#### Inteiros sem Sinal

Inteiros sem sinal são inteiros não negativos.

**Os tipos para inteiros sem sinal são:**

* **'`uint`'**: Representa números inteiros sem sinal, e seu tamanho varia de acordo com a arquitetura da máquina.
* **'`uint8`'**: Representa números inteiros sem sinal com tamanho de 8 bits.
* **'`uint16`'**: Representa números inteiros sem sinal com tamanho de 16 bits.
* **'`uint32`'**: Representa números inteiros sem sinal com tamanho de 32 bits.
* **'`uint64`'**: Representa números inteiros sem sinal com tamanho de 64 bits.

``` go
var uinteiro    uint
var uinteiro8   uint8
var uinteiro16  uint16
var uinteiro32  uint32
var uinteiro64  uint64
```

> **NOTA:** Há também o tipo `uintptr`, que é usado para armazenar valores inteiros não assinados suficientes para armazenar todos os bits de um ponteiro.

#### Tipo `byte`

O tipo **`byte`** é um alias para o tipo `uint8`, que equivale a 8 bits, sendo assim, perfeito para representar caracteres ASCII.

**Exemplo:**

``` go
package main

import (
    "fmt"
    "unsafe"
)

func main() {
    var x byte = 2
    fmt.Printf("Tamanho: %v byte(s) | Tipo: %T\n", unsafe.Sizeof(x), x)
    // -> Tamanho: 1 byte(s) | Tipo: uint8
}
```

O tamanho impresso é de 1 byte, pois 8 bits equivalem a 1 byte.

> **NOTA:** A função `unsafe.Sizeof()` é usada para verificar a quantidade de bytes que uma variável possui.

##### Buffer para Slice de Bytes

O pacote `bytes` fornece o tipo **`Buffer`**, cujo variáveis com esse tipo se tornam um buffer temporário para armazenar bytes.

**Declarar um `bytes.buffer`:**

``` go
var b bytes.Buffer
```

**Declaração com funções:**

* **'`bytes.NewBuffer()`'**: Cria um buffer a partir de um slice de bytes.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        fmt.Println(b.String())
        // -> Hello, World!
    }
    ```

* **'`bytes.NewBufferString()`'**: Cria um buffer a partir de uma string.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBufferString("Hello, World!")
        fmt.Println(b)
        // -> Hello, World!
    }
    ```

Essas funções são especialmente úteis quando a necessidade é criar um buffer já com um valor definido inicialmente.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func ReverseString(s string) string {
    // Buffer
    var b bytes.Buffer

    // Largura da string que será invertida
    length := len(s)

    // Itera sobre os caracteres da string de maneira inversa
    for i := length - 1; i >= 0; i-- {
        // Escreve cada caractere em ordem inversa
        b.WriteByte(s[i])
    }

    // Retorna a string invertida
    return b.String()
}

func main() {
    str := "Hello, World!"
    fmt.Println("Reversed:", ReverseString(str))
}
```

No exemplo acima, a função **`ReverseString()`** inverte a ordem dos caracteres da string passada - "Hello, World" no caso - usando um buffer de bytes, escrevendo os caracteres um a um por meio de um loop em ordem inversa. No fim, é retornado o buffer com `b.String()`, que converte o buffer em uma string.

**Os principais métodos de `Buffer` são:**

* **'`Bytes()`'**: Retorna o que está gravado no buffer como um slice de bytes.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        fmt.Println(b.Bytes())
        // -> [72 101 108 108 111 44 32 87 111 114 108 100 33]
    }
    ```

* **'`String()`'**: Retorna o que está gravado no buffer como uma string.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        fmt.Println(b.String())
        // -> Hello, World!
    }
    ```

* **'`Len()`'**: Retorna o número de bytes da parte não lida do buffer.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        fmt.Println(b.Len()) // -> 13
    }
    ```

* **'`Cap()`'**: Retorna o total de dados alocodos no buffer.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        fmt.Println(b.Cap()) // -> 13
    }
    ```

* **'`Grow()`'**: Aumenta a capacidade do buffer.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        var b bytes.Buffer
        fmt.Println(b.Cap()) // -> 0
        b.Grow(64)
        fmt.Println(b.Cap()) // -> 64
    }
    ```

    > **NOTA:** Se o buffer não puder aumentar, ele entrará em pânico com `ErrTooLarge`.

* **'`Read()`'**: Lê a mesma largura de bytes definidos pela largura do slice de bytes passado como argumento.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        n, err := b.Read(b.Bytes())
        if err != nil {
            fmt.Println("Err:", err)
        }

        fmt.Println("Bytes lidos:", n)
        // -> Bytes lidos: 13
    }
    ```

* **'`ReadByte()`'**: Lê e retorna o próximo byte do buffer.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        n, err := b.ReadByte()
        if err != nil {
            fmt.Println("Err:", err)
        }

        fmt.Println("Byte lido:", n)
        // -> Bytes lidos: 72

        fmt.Println(b.String()) // -> ello, World!
    }
    ```

* **'`ReadBytes()`'**: Lê até a primeira ocorrência do byte especificado. Retorna um slice de bytes contendo todos os bytes lidos (inclui o byte que foi especificado).

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        n, err := b.ReadBytes('W')
        if err != nil {
            fmt.Println("Err:", err)
        }

        fmt.Println("Bytes lidos:", n)
        // -> Bytes lidos: [72 101 108 108 111 44 32 87]

        fmt.Println(b.String()) // -> orld!
    }
    ```

* **'`ReadString()`'**: Lê até a prieira ocorrência do byte especificado. Retorna uma string contendo o que foi lido (inclui até o caractere que foi especificado).

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        n, err := b.ReadString('W')
        if err != nil {
            fmt.Println("Err:", err)
        }

        fmt.Println("Bytes lidos:", n)
        // -> Hello, W

        fmt.Println(b.String()) // -> orld!
    }
    ```

* **'`Next()`'**: Retorna os próximos `n` bytes.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        for i := b.Len() / 2; i >= 0; i-- {
            fmt.Printf("%s\n", b.Next(2))
        }
        /* Output:
        He
        ll
        o,
        W
        or
        ld
        !
        */
    }
    ```

* **'`Reset()`'**: Redefine o buffer, tornando-o vazio.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        b.Reset()

        b.WriteString("Hello, Go!")
        fmt.Println(b.String()) // -> Hello, Go!
    }
    ```

* **'`Truncate()`'**: Descarta todos os byte, com exceção dos `n` bytes não lidos.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        b := bytes.NewBuffer([]byte("Hello, World!"))
        b.Truncate(5)
        fmt.Println(b.String()) // -> Hello
    }
    ```

* **'`Write()`'**: Adiciona um slice de bytes ao buffer e retorna a quantidade de bytes escritos.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        var b bytes.Buffer
        n, err := b.Write([]byte("Hello, World!"))
        if err != nil {
            fmt.Println("Err:", err)
            return
        }
        fmt.Println("Bytes lidos:", n)
        fmt.Println(b.String())
        /* Output:
        Bytes lidos: 13
        Hello, World!
        */
    }
    ```

* **'`WriteByte()`'**: Adiciona um único byte ao buffer.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        var b bytes.Buffer
        err := b.WriteByte('W')
        if err != nil {
            fmt.Println("Err:", err)
            return
        }
        fmt.Println(b.String())
        // -> W
    }
    ```

* **'`WriteString()`'**: Adiciona uma string ao buffer e retorna a quantidade de bytes escritos.

    ``` go
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {
        var b bytes.Buffer
        n, err := b.WriteString("Hello, World!")
        if err != nil {
            fmt.Println("Err:", err)
            return
        }
        fmt.Println("Bytes lidos:", n)
        fmt.Println(b.String())
        /* Output:
        Bytes lidos: 13
        Hello, World!
        */
    }
    ```

###### Comparação entre Slice de Bytes

A comparação entre slice de bytes pode ser feita com a função `bytes.Compare()`, que compara dois slices de bytes lexicograficamente.

Dependendo da comparação, é retornado:

* **'`-1`'**: Caso o primeiro slice de bytes seja menor que o segundo.
* **'`0`'**: Caso ambos os slices de bytes sejam iguais.
* **'`1`'**: Caso o primeiro slice de bytes seja maior que o segundo.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice com os caracteres "G" e "o"
    slice1 := []byte{71, 111}     // Caracteres "G" e "o"
    slice2 := []byte{71, 111, 33} // Caracteres "G", "o" e "!"

    result := bytes.Compare(slice1, slice2)
    fmt.Println(result) // -> -1
}
```

###### Subslice em Slice de Bytes

A função **`bytes.Contains()`** verifica se há um subslice de bytes dentro de um slice de bytes. Ela retorna `true` caso haja, e `false` caso não haja.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice e subslice
    slice :=    []byte("Hello, World!")
    subSlice := []byte("World")

    // Verifica se o subslice está dentro do primeiro
    result := bytes.Contains(slice, subSlice)
    fmt.Println(result) // -> true
}
```

Há também a função **`bytes.ContainsAny()`**, que verifica se o dado caractere está presente no slice de bytes. Essa função analisa caracteres encodado em UTF-8.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Olá, Mundo!")

    // Verifica se há o caractere "á" no slice
    result := bytes.ContainsAny(slice, "á")
    fmt.Println(result) // -> true
}
```

###### Caracteres por Índice em Slice de Bytes

A função **`bytes.Index()`** retorna o índice correspondendo ao caractere passado dentro do slice de bytes.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Hello, World!")

    // Encontra o índice do caractere "W"
    index := bytes.Index(slice, []byte("W"))
    fmt.Println(index) // -> 6
}
```

A função **`bytes.IndexAny()`** funciona de maneira semelhante, porém aceitando qualquer caractere UTF-8 para verificação.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Olá, Mundo!")

    // Encontra o índice do caractere "W"
    index := bytes.IndexAny(slice, "á")
    fmt.Println(index) // -> 2
}
```

Para encontrar o índice de um determinado byte em si ao invés do caractere que o mesmo representa, há a função **`bytes.IndexByte()`**.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Hello, World!")

    // Verifica o índice do caractere "W" (byte 87)
    result := bytes.IndexByte(slice, 87)
    fmt.Println(result) // -> 7
}
```

As funções **`bytes.LastIndex()`**, **`bytes.LastIndexAny()`** e **`bytes.LastIndexByte()`** fazem a verificação começando pelo final do slice de bytes.

###### Mapping em Slice de Bytes

A função **`bytes.Map()`** mapeia um slice de bytes, aceitando uma função callback e permitindo a criação de um novo slice de bytes a partir desse callback.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Hello, World!")

    // Função para mapping
    mapping := func(r rune) rune {
        switch {
        case r >= 'A' && r <= 'Z':
            return 'A'
        case r >= 'a' && r <= 'z':
            return 'a'
        }
        return r
    }

    // Mapeia o slice de bytes
    newSlice := bytes.Map(mapping, slice)
    fmt.Printf("%s\n", newSlice) // -> Aaaaa, Aaaaa!
}
```

###### Concatenação de Slice de Bytes

A função **`bytes.Join()`** concatena dois slices de bytes, separando-as com um separador definido na chamada da função.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes multidimensional
    slice := [][]byte{
        []byte("H"),
        []byte("e"),
        []byte("l"),
        []byte("l"),
        []byte("o"),
        []byte("!"),
    }

    // Imprime o slice multidimensional como um único slice
    fmt.Printf("%s\n", bytes.Join(slice, []byte(" ")))
    fmt.Printf("%s\n", bytes.Join(slice, []byte("")))

    /* Output:
    H e l l o !
    Hello!
    */
}
```

###### Separarão em Slice de Bytes

A função **`bytes.Split()`** separa um slice de bytes a partir de um separador e, no fim, retorna um slice de bytes multidimensional.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Hello World")

    // Separa as palavras no slice de bytes
    newSlice := bytes.Split(slice, []byte(" "))

    // Imprime o resultado
    fmt.Printf("%s\n", newSlice)

    // -> [Hello World]
}
```

Com a função **`bytes.SplitN()`** é possível especificar o número mínimo de slices internos.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("a,b,c,d,e,f,g")

    // Separa as palavras no slice de bytes
    newSlice := bytes.SplitN(slice, []byte(","), 5)

    // Imprime o resultado
    fmt.Printf("%s\n", newSlice)

    // -> [a b c d e,f,g]
}
```

Para separar incluindo o separador, use a função **`bytes.SplitAfter()`** ou **`bytes.SplitAfterN()`** (para separar com um número mínimo de slices internos).

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("a,b,c,d,e,f,g")

    // Separa as palavras no slice de bytes
    newSlice := bytes.SplitAfter(slice, []byte(","))

    // Imprime o resultado
    fmt.Printf("%s\n", newSlice)

    // -> [a, b, c, d, e, f, g]
}
```

###### Repetição de Slice de Bytes

A função **`bytes.Repeat()`** retorna um novo slice, composto das repetições de um dado slice.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    // Slice de bytes
    slice := []byte("Foo")

    // Repete o slice 3 vezes
    newSlice := bytes.Repeat(slice, 3)

    // Imprime o novo slice
    fmt.Println(newSlice)
    fmt.Printf("%s\n", string(newSlice))

    /* Output:
    [70 111 111 70 111 111 70 111 111]
    FooFooFoo
    */
}
```

###### Substituição em Slice de Bytes

A função **`bytes.Replace()`** substitui a primeira ocorrência de um byte no slice de bytes. Essa função retorna um novo slice com as substituições e não altera o original.

**Os parâmetros são:**

1. **'`s`'**: Slice que ocorrerá a(s) substituição(ões)
1. **'`old`'**: Byte que será substituído.
1. **'`new`'**: Byte pelo qual `old` será substituído.
1. **'`n`'**: Quantidade de ocorrências que serão substituídas.

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    slice := []byte("Hello, World! Hello, Go!")
    newSlice := bytes.Replace(
        slice,
        []byte("Hello"),
        []byte("Hi"),
        1,
    )

    // Imprime os slices
    fmt.Printf("%s\n", slice)
    fmt.Printf("%s\n", newSlice)

    /* Output:
    Hello, World! Hello, Go!
    Hi, World! Hello, Go!
    */
}
```

Para substituir todas as ocorrências, use a função **`bytes.ReplaceAll()`**, que tem os mesmo parâmetros que `bytes.Replace()`, com exceção do último (`n`).

**Exemplo:**

``` go
package main

import (
    "bytes"
    "fmt"
)

func main() {
    slice := []byte("Hello, World! Hello, Go!")
    newSlice := bytes.ReplaceAll(
        slice,
        []byte("Hello"),
        []byte("Hi"),
    )

    // Imprime os slices
    fmt.Printf("%s\n", slice)
    fmt.Printf("%s\n", newSlice)

    /* Output:
    Hello, World! Hello, Go!
    Hi, World! Hi, Go!
    */
}
```

#### `rune`

É um alias para `int32`, e é usado para representar um Unicode Code Point.

Uma string é uma sequência de bytes, onde cada caractere UTF-8 pode ocupar mais de um byte. Assim, para trabalhar com caracteres individuais em uma string de forma consistente, é necessário usar `rune` para garantir que os caracteres sejam interpretados corretamente, independentemente de quantos bytes cada caractere ocupa na representação UTF-8.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    // String com diferentes caracteres
    x := "Hello, 界"

    // Imprime a largura da string
    fmt.Println(len(x)) // -> 10

    for _, char := range x {
        // Imprime cada caractere da string
        fmt.Printf("%c ", char) // -> H e l l o ,   界
    }
}
```

### Números de Ponto Flutuante

Há dois tipos para representar números de ponto flutuante: **`float32`** e **`float64`**.

* **'`float32`'**: Ocupa 32 bits, e sua faixa é **`-3.4e+38`** até **`3.4e+38`**.

    ``` go
    package main

    import "fmt"

    func main() {
        var x float32 = 123.456
        var y float32 = 3.4e+38

        fmt.Printf("Tipo: %T | Valor: %v\n", x, x)
        fmt.Printf("Tipo: %T | Valor: %v\n", y, y)

        /* ->
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

        /* ->
        Tipo: float64 | Valor: 123.456
        Tipo: float64 | Valor: 1.7e+308
        */
    }
    ```

### Números Complexos

São representados por **`complex64`** e **`complex128`**, sendo `complex128` o tipo de complexo padrão.

``` go
package main

import "fmt"

func main() {
    var x complex64
    var y complex128

    x = 5 + 2i
    y = 2 + 1i

    fmt.Println(x)
    fmt.Println(y)
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
    // -> Tipo: string | Valor: Olá, Mundo!
    fmt.Printf("Tipo: %T | Valor: %v\n", str2, str2)
    // -> Tipo: string | Valor: Olá, Go!
}
```

> **OBS.:** Aspas simples são usadas para caracteres, e não strings.

#### Comprimento de uma String

A função **`len()`**, quando recebe uma string, retorna o comprimento da mesma.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    str := "Hello, World!"
    fmt.Println(len(str)) // -> 13
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
        // -> OLÁ, MUNDO!
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
        // -> olá, mundo!
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
        fmt.Println(resultado) // -> true
    }
    ```

* **'`Count()`'**: Dada uma string e uma substring, retorna a quantidade de vezes que a substring ocorreu dentro da string.

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
        fmt.Println(resultado) // -> 2
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
        fmt.Println(resultado) // -> true
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
        fmt.Println(resultado) // -> true
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
        fmt.Println(resultado) // -> 7
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
        // -> Go is powerful. Go is amazing.
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
        // -> Go is powerful. Go is amazing.
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
        // -> [I love Golang!]
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
        // -> Olá, Mundo!Olá, Mundo!
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
        // -> "Olá, Mundo!"
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
        // -> "Olá, Mundo!"
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
        fmt.Println(strings.Compare("abc", "abc")) // -> 0
        fmt.Println(strings.Compare("abc", "def")) // -> -1
        fmt.Println(strings.Compare("def", "abc")) // -> 1
    }
    ```

#### Formatação de Strings

Para formatar uma string em uma variável, é usada a função **`fmt.Sprintf()`**. Essa função funciona de maneira similar a função `fmt.Printf()`, mas ao invés de imprimir, ela retorna a string.

**Sintaxe:**

``` go
texto := fmt.Sprintf(s, formatador1, formatador2, ..., formatadorN)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x, y := 5, 2
    s := fmt.Sprintf("A soma entre %d e %d é igual a %d", x, y, x + y)
    fmt.Println(s) // -> A soma entre 5 e 2 é igual a 7
}
```

##### Formatadores

###### Formatadores para Inteiros

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

###### Formatadores para Números de Pontos Flutuante

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

    /* Output:
    Valor padrão: 3.141590
    Valor em notação científica: 3.141590e+00
    Valor em notação científica: 3.141590E+00
    Valor com `%g`: 3.14159
    */
}
```

###### Formatadores para Strings

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

    /* Output:
    String: Go!
    String com aspas: "Go!"
    String como hex dump: 476f21
    String como hex dump com espaços: 47 6f 21
    */
}
```

###### Formatadores para Booleanos

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

    /* Output:
    Valor de x: true
    Valor de y: false
    */
}
```

###### Outros Formatadores

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

        /* Output:
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

        /* Output:
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

    /* Output:
    Caractere: A
    Código Unicode: U+0041
    */
}
```

### Booleanos

São valores booleanos (`true` e `false`) são representados pelo tipo **`bool`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x bool = true
    var y bool = false
    var z bool

    fmt.Println(x) // -> true
    fmt.Println(y) // -> false
    fmt.Println(z) // -> false
}
```

### Conversão entre Tipos

#### Conversão para Inteiro

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
    // -> Tipo: int | Valor: 5
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
    // -> Tipo: int | Valor: 5
}
```

#### Conversão para Float

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
    // -> Tipo: float32 | Valor: 5
    // -> Tipo: float64 | Valor: 5
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
    // -> Tipo: float64 | Valor: 5
}
```

#### Conversão para String

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
    /* Output:
    Tipo: string | Valor: 5.13
    Tipo: string | Valor: 8
    Tipo: string | Valor: true
    */
}
```

#### Conversão para Booleano

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
    // -> Tipo: bool | Valor: true
}
```

## Operadores

Em Go, os quatro tipos de operadores principais são:

* Operadores aritméticos
* Operadores de comparação
* Operadores lógicos
* Operadores bitwise

### Operadores Aritméticos

Os operadores aritméticos realizam operações matemáticas em variáveis ou valores numéricos literais.

**Os operadores aritméticos são:**

* **'`+`'**: Operador de adição.
* **'`-`'**: Operador de subtração
* **'`*`'**: Operador de multiplicação.
* **'`/`'**: Operador de divisão.
* **'`%`'**: Operador de resto da divisão.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 5
    y := 2

    fmt.Println("Soma:", x + y)             // -> Soma: 7
    fmt.Println("Subtração:", x - y)        // -> Subtração: 3
    fmt.Println("Multiplicação:", x * y)    // -> Multiplicação: 10
    fmt.Println("Divisão:", x / y)          // -> Divisão: 2
    fmt.Println("Resto da divisão:", x % y) // -> Resto da divisão: 1
}
```

> **NOTA:** Na divisão, o resultado é 2 porque ambos os operandos são inteiros, e por isso o resultado também é um inteiro. Para corrigir isso, um dos operados pode ser convertido para `float32` ou `float64`.

Além disso, há também os operadores de incremento e decremento.

* **'`++`'**: Operador de incremento.
* **'`--`'**: Operador de decremento.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 5
    x++
    fmt.Println(x) // -> 6

    x--
    fmt.Println(x) // -> 5
}
```

### Operadores de Comparação

Os operadores de comparação compararam dois valores e retornam um valor booleano.

Os operadores de comparação são:

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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> false
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
        fmt.Println(x) // -> false
        fmt.Println(y) // -> true
        fmt.Println(z) // -> true
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> true
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> false
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> true
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> true
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> false
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> true
        fmt.Println(z) // -> false
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
        fmt.Println(x) // -> true
        fmt.Println(y) // -> false
        fmt.Println(z) // -> false
    }
    ```

### Operadores Bitwise

Os operadores bitwise são utilizados para realizar operações a nível de bits em números inteiros. Os operadores bitwise atuam em cada bit individual de dois números e executam operações como deslocamento, AND, OR, XOR, entre outros.

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
        fmt.Println(resultado) // -> 1
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
        // -> Biário: 111 | Decimal: 7
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
        // -> Biário: 110 | Decimal: 6
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
        // -> Biário: 10100 | Decimal: 20
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
        fmt.Println(resultado) // -> 1
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

## Estruturas Condicionais

### `if`, `else` e `else if`

As palavras-chaves `if`, `else` e `else if` são usadas para analisar condições, sendo essas condições uma expressão ou variável que retorna um valor booleano.

**Sintaxe `if`:**

``` go
if condicao {
    // Bloco executa quando a condição for verdadeira
}
```

A condição deve ser uma expressão ou uma variável que retorna um valor booleano, e ela testar verdadeiro, será executado o código dentro do bloco.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    if 1 + 1 == 2 {
        // Esse bloco irá executar, já que 1 + 1 é 2
        fmt.Println("1 + 1 é igual a 2!") // -> 1 + 1 é igual a 2
    }
}
```

**Sintaxe `if`/`else`:**

``` go
if condicao {
    // Executa quando a condicao é verdadeira
} else {
    // Executa quando o bloco `if` não executa
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    if 1 + 1 == 3 {
        // Esse bloco não irá executar
        fmt.Println("1 + 1 é igual a 3!")
    } else {
        // Esse bloco irá executar, já que o bloco acima não executou
        fmt.Println("Bloco else") // -> Bloco else
    }
}
```

**Sintaxe `if`/`else if`:**

``` go
if condicao1 {
    // Executa caso a `condicao1` seja verdadeira
} else if condicao2 {
    // Executa caso a `condicao2` seja verdadeira
} // Pode ou não possuir `else`
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 2
    if x == 1 {
        fmt.Println("X é 1")
    } else if x == 2 {
        // Apenas esse bloco executará
        fmt.Println("X é 2") // -> X é 2
    } else if x == 3 {
        fmt.Println("X é 3")
    } else {
        fmt.Println("X é diferente de 1, 2 e 3")
    }
}
```

> **NOTA:** Em uma estrutura condicional podem haver nenhum ou vários `else if`, e apenas um `else`. Além disso, a estrutura sempre deve ser inicializada com `if`.

### Estrutura `switch`

Uma estrutura **`switch`** permite executar um bloco diferente de acordo com o valor de uma dada variável ou expressão.

**Sintaxe:**

``` go
switch expressao {
case valor1:
    // Executa caso `expressao` seja igual a `valor1`
case valor2:
    // Executa caso `expressao` seja igual a `valor2`
case valor3:
    // Executa caso `expressao` seja igual a `valor3`
default:
    // Executa caso nenhum `case` anterior execute
}
```

Se o valor passado após a palavra-chave `case` for igual ao valor da expressão passada em `switch`, o bloco abaixo é executado, mas se o valor não corresponder, então é passado para o próximo `case`. Se nenhum `case` corresponder, é executado o bloco `default`.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 2
    switch x {
    case 1:
        fmt.Println("X é 1")
    case 2:
        // Apenas este bloco irá executar
        fmt.Println("X é 2") // -> X é 2
    case 3:
        fmt.Println("X é 3")
    default:
        fmt.Println("X é diferente de 1, 2 e 3")
    }
}
```

#### Múltiplos Valores em `case`

Um `case` pode receber mais de um valor, permitindo executar um único bloco para diferentes valores, sem a necessidade de duplicar blocos.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 3
    switch x {
    case 1, 2, 3:
        // Este bloco irá executar, já que x é 3
        fmt.Println("X é 1, 2 ou 3") // -> X é 1, 2 ou 3
    default:
        fmt.Println("X é diferente de 1, 2 e 3")
    }
}
```

#### `switch` sem Expressão

Se não definida uma expressão em uma estrutura `switch`, os `case`s aceitam uma condição, executando seus blocos caso essa expressão seja verdadeira.

**Sintaxe:**

``` go
switch {
case condicao1:
    // Executa quando `condicao1` for verdadeira
case condicao2:
    // Executa quando `condicao2` for verdadeira
case condicao3:
    // Executa quando `condicao3` for verdadeira
default:
    // Executa quando nenhum `case` corresponder
}
```

Basicamente, uma estrutura `switch` sem expressão é uma estrutura condicional `if`/`else if`, e geralmente é mais eficiente, além de ser mais legível.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 2
    switch {
    case x == 1:
        fmt.Println("X é 1")
    case x == 2:
        // Apenas este bloco irá executar
        fmt.Println("X é 2") // -> X é 2
    case x == 3:
        fmt.Println("X é 3")
    default:
        fmt.Println("X é diferente de 1, 2 e 3")
    }
}
```

#### Palavra-chave `fallthrough`

A palavra-chave **`fallthrough`** é usada para executar também o próximo bloco `case`.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 2
    switch {
    case x == 1:
        fmt.Println("X é 1")
    case x == 2:
        // Este bloco irá executar
        fmt.Println("X é 2") // -> X é 2
        fallthrough
    case x == 3:
        // Este bloco também irá executar
        fmt.Println("X é 3") // -> X é 3
    default:
        fmt.Println("X é diferente de 1, 2 e 3")
    }
}
```

## Input de Valores

### Input de No Mínimo Uma Palavra

Para capturar a entrada do usuário até o primeiro espaço em branco, pode ser utiliado as funções **`fmt.Scan()`**, **`fmt.Scanf()`** e **`fmt.Scanln()`**.

#### Função `fmt.Scan()`

A função `fmt.Scan()` captura a entrada do usuário até o primeiro espaço em branco, independentemente do tipo de valor.

**Sintaxe:**

``` go
fmt.Scan(&variavel)
```

A variável passada será a variável que vai receber o valor passado pelo usuário. A função deve receber o endereço de memória da variável, e por isso é usado o operador **`&`**.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var nome string
    fmt.Print("Digite seu nome: ")
    fmt.Scan(&nome)
    fmt.Printf("Olá, %s!\n", nome)
}
```

#### Função `fmt.Scanf()`

A função `fmt.Scanf()` é similar a função `fmt.Scan()`, porém aceita apenas um tipo de entrada. A entrada permitida deve ser especifica por meio de um formatador, como `"%s"` e `"%d"`.

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

No exemplo acima, a função **`LimparBuffer()`** é usada para ler uma linha de texto de entrada padrão e descartá-la. Isso é necessário para que não haja conflitos da primeira entrada com a segunda.

A necessidade de limpar o buffer após uma entrada com `fmt.Scanf()` é por conta dessa função deixar uma quebra de linha no fim da entrada, afetando assim o próximo input, caso haja.

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

### Input com Mais de Uma Palavra

O pacote `bufio` em conjunto com o pacote `os` fornece ferramentas que permitem ler entradas com mais de uma palavra.

**Sintaxe:**

``` go
// Cria um scanner para leitura
scanner := bufio.NewScanner(os.Stdin)

// Lê uma linha de entrada do usuário
scanner.Scan()

// Retorna o texto lido da chamada anterior
variavel := scanner.Text()
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
var nomeArray = [comprimento]tipo{valor1, valor2, ..., valorN}

// Com `:=`
nomeArray := [comprimento]tipo{valor1, valor2, ..., valorN}
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


    fmt.Println(myArray[0]) // -> 2
    fmt.Println(myArray[1]) // -> 4
    fmt.Println(myArray[2]) // -> 6
    fmt.Println(myArray[3]) // -> 8
    fmt.Println(myArray[4]) // -> 10
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

    fmt.Println(myArray) // -> [2 20 6 8]
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
    fmt.Println(intArray)   // -> [0 0 0]
    fmt.Println(floatArray) // -> [0 0 0]
    fmt.Println(strArray)   // -> [  ]
    fmt.Println(boolArray)  // -> [false false false]
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
    fmt.Println(myArray) // -> [0 5 10 0 0]
}
```

## Slices

São similares a arrays, porém são mais frexíveis e úteis. Slices podem aumentar dinamicamente em tempo de execução.

Para declarar uma slice, basta declarar um array sem especificar um tamanho fixo, deixando os colchetes vazios.

**Sintaxe:**

``` go
nomeSlice := []tipo{valor1, valor2, ..., valorN}
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
    fmt.Println(len(mySlice1)) // -> 0
    fmt.Println(len(mySlice2)) // -> 3
    fmt.Println(len(mySlice3)) // -> 4
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
    fmt.Println(mySlice1) // -> [0 0 0]
    fmt.Println(mySlice2) // -> [0 0]

    // Imprimindo largura e capacidade dos slices
    fmt.Println(len(mySlice1)) // -> 3
    fmt.Println(cap(mySlice1)) // -> 5

    fmt.Println(len(mySlice2)) // -> 2
    fmt.Println(cap(mySlice2)) // -> 2
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
    fmt.Println(len(mySlice1)) // -> 0
    fmt.Println(len(mySlice2)) // -> 3
    fmt.Println(len(mySlice3)) // -> 4
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
    fmt.Println(cap(mySlice1)) // -> 10
    fmt.Println(cap(mySlice2)) // -> 2
    fmt.Println(cap(mySlice3)) // -> 4
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
    fmt.Println(slice1) // -> [4 5 6 7]
    fmt.Println(slice2) // -> [2 3]
    fmt.Println(slice3) // -> [6 7 8 9]
    fmt.Println(slice4) // -> [3 4 5]
    fmt.Println(slice5) // -> [1 2 3 4]
    fmt.Println(slice6) // -> [1 2 3 4 5 6 7 8 9]
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
    fmt.Println(mySlice)    // -> [1 2 3 4]
    fmt.Println(novoSlice)  // -> [1 2 3 4 5]
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
    fmt.Println(mySlice) // -> [1 2 3 4 5 6 7]
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
    fmt.Println(mySlice3) // -> [1 2 3 10 20 30]
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
    fmt.Println(mySlice) // -> [1 2 4 5]
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
    fmt.Println(newSlice) // -> [1 3 4 5]
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

    /* ->
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
    // -> [[1 2 3] [4 5 6] [7 8 9]]
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
    // -> [[1 2 3] [4 5 6] [7 8 9]]
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
        fmt.Println(myIntSlice) // -> [1 2 3 4 5]
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
        fmt.Println(myFloatSlice) // -> [5.1 5.2 5.3 5.4 5.5]
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
        fmt.Println(myStrSlice) // -> [C++ Go Python Ruby]
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

        fmt.Println(ordenado) // -> true
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

        fmt.Println(ordenado) // -> true
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

        fmt.Println(ordenado) // -> true
    }
    ```

## Estruturas de Repetição

Em Go, **`for`** é o único loop, podendo ser usado em diferentes casos.

**Sintaxe:**

``` go
for variavelInicial; condicao; incremento
```

* **'`variavelInicial`'**: Inicia uma variável.
* **'`condicao`'**: Avalia uma condição em toda iteração do loop, encerrando o loop quando se torna falsa.
* **'`incremento`'**: Incrementa a variável iniciada a cada iteração do loop.

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    for x := 0; x < 10; x++ {
        fmt.Printf("%d ", x)
    }
    // Output final: 0 1 2 3 4 5 6 7 8 9
}
```

### Loop Condicional

Um loop condicional executa enquando uma dada condição se mantiver verdadeira.

**Sintaxe:**

``` go
for condicao {
    // Executa enquando `condicao` for verdadeira
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    x := 0
    for x < 10 {
        fmt.Printf("%d ", x)
        x++
    }
    // Output final: 0 1 2 3 4 5 6 7 8 9
}
```

### Controle de Fluxo em Loops

Para controlar o fluxo em loops, existem as palavras-chaves **`break`** e **`continue`**.

* **'`break`'**: Interrompe o loop.
* **'`continue`'**: Pula para a próxima iteração do loop.

**Exemplo com `break`:**

``` go
package main

import "fmt"

func main() {
    for x := 0; x < 10; x++ {
        if x > 5 {
            break
        }
        fmt.Printf("%d ", x)
    }
    // Output final: 0 1 2 3 4 5
}
```

**Exemplo com `continue`:**

``` go
package main

import "fmt"

func main() {
    for x := 0; x < 10; x++ {
        if x % 2 != 0 {
            continue
        }
        fmt.Printf("%d ", x)
    }
    // Output final: 0 2 4 6 8
}
```

### Loop Infinito

Um `for` sem nenhuma declaração irá executar seu bloco continuamente até encontrar a palavra-chave `break`.

**Sintaxe:**

``` go
for {
    // Executará infinitamente
}
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x int
    for {
        fmt.Printf("%d ", x)
        x++
        if x > 9 {
            break
        }
    }
    // Output final: 0 1 2 3 4 5 6 7 8 9
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
    // -> Olá, Mundo!
}
```

A função acima imprime "Olá, Mundo!".

### Regras para Nomes de Funções

* São case-sensitive.
* Devem se iniciar com um letra.
* Podem conter apenas caracteres alfanuméricos e `_`.
* Geralmente são escritas em *PascalCase*.

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
    // -> Olá, Mundo!
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
    // -> A soma entre 5 e 2 é 7
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
    // -> Resultado da multiplicação: 10
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
    // -> Resultado da multiplicação: 10
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
    // -> Resultado da multiplicação: 7
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
    // -> Resultado da multiplicação: 10
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
    // -> Resultado da multiplicação: 10
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
    // -> 5! = 120
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
    fmt.Println("Soma:", Sum(1, 2, 3, 4, 5)) // -> 15
    fmt.Println("Soma:", Sum(5, 2, 4)) // -> 11
    fmt.Println("Soma:", Sum()) // -> 0
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
        fmt.Println("Olá, Mundo!") // -> Olá, Mundo!
    }()

    // Função anônima em uma variável
    myFunc := func() {
        fmt.Println("Olá, Go!")
    }

    // Chama a variável (que é uma função)
    myFunc() // -> Olá, Go!
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

    fmt.Println(contador()) // -> 1
    fmt.Println(contador()) // -> 2
    fmt.Println(contador()) // -> 3
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
    // -> A raiz quadrada de 25.0 é 5.0
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
    // -> A raiz quadrada de 25.0 é 5.0
}
```

### Funções Genéricas

São funções que podem receber argumentos genéricos, ou seja, de qualquer tipo. Nessas funções, o tipo genérico será definido em tempo de compilação, de acordo com o argumento passado.

**Sintaxe:**

``` go
func Foo[T any](x T) {
    // Bloco da função
}
```

Aqui, `T` é do tipo `any`, que pode ser qualquer outro tipo, e por conta disso, o parâmetro `x` pode receber um argumento de qualquer tipo.

**Exemplo:**

``` go
package main

import "fmt"

func Tipo[T any](x T) string {
    return fmt.Sprintf("%T", x)
}

func main() {
    fmt.Println(Tipo("Hello"))        // -> string
    fmt.Println(Tipo(5))              // -> int
    fmt.Println(Tipo(23.7))           // -> float64
    fmt.Println(Tipo(true))           // -> bool
    fmt.Println(Tipo([]int{1, 2, 3})) // -> []int
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
    // -> map[a:Exemplo2 c:Exemplo3 z:Exemplo1]

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
    // -> map[num1:5 num3:9]
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
    fmt.Println(val1, exist1) // -> 5 true
    fmt.Println(val2, exist2) // -> 7 true
    fmt.Println(val3, exist3) // -> 9 true
    fmt.Println(val4, exist4) // -> 0 false
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
    fmt.Println(exist1) // -> true
    fmt.Println(exist2) // -> true
    fmt.Println(exist3) // -> true
    fmt.Println(exist4) // -> false
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
    fmt.Println(map1) // -> map[num1:11 num2:7 num3:9]
    fmt.Println(map2) // -> map[num1:11 num2:7 num3:9]
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
    fmt.Println(myMap)   // -> map[num1:5 num2:7 num3:9]
    fmt.Println(copyMap) // -> map[num1:11 num2:7 num3:9]
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
    MyStruct.OlaMundo(MyStruct{}) // -> Olá, Mundo!

    // Usa a função Soma() e imprime o resultado dela
    resultadoSoma := MyStruct.Soma(MyStruct{}, 5, 2)
    fmt.Println(resultadoSoma) // -> 7
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
    instanceStruct.OlaMundo() // -> Olá, Mundo!

    // Usa a função Soma() e imprime o resultado dela
    resultadoSoma := instanceStruct.Soma(5, 2)
    fmt.Println(resultadoSoma) // -> 7
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
    fmt.Println("Soma:", soma) // -> 7
    fmt.Println("Subtração:", subtracao) // -> 3
    fmt.Println("Multiplicação:", multiplicacao) // -> 10
    fmt.Println("Divisão:", divisao) // -> 2.5
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
    fmt.Println(valorGenerico) // -> 23

    // Atribui uma string à variável
    valorGenerico = "Olá, Mundo!"
    fmt.Println(valorGenerico) // -> "Olá, Mundo!"
}
```

> **PITFALLS:** O uso excessivo de interfaces vazias pode tornar o código menos seguro e legível, pois a verificação de tipos é adiada para tempo de execução. O uso consciente e apropriado são essenciais para evitar potenciais armadilhas.

#### Reflection

Geralmente as interfaces vazias são usadas em conjunto com o pacote **`reflect`** para realizar operações de reflexão em tempo de execução, permitindo inspecionar tipos de valores de maneira dinâmica.

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
    fmt.Println(Tipo(5)) // -> int
    fmt.Println(Tipo(2.3)) // -> float64
    fmt.Println(Tipo("Olá")) // -> string
    fmt.Println(Tipo(false)) // -> bool
}
```

No exemplo acima, a função `Tipo()` retorna o tipo do argumento que for passado.

### Type Assertions

Afirmações de tipo se referem a ação de verificar se uma `interface{}` é de um determinado tipo.

**Sintaxe:**

``` go
valor, ok := variavel.(tipo)
```

**Exemplo:**

``` go
package main

import "fmt"

func main() {
    var x interface{} = "Olá, Mundo!"
    s, ok := x.(string)

    fmt.Printf("%v | %v\n", s, ok)
    // -> Olá, Mundo! | true
}
```

Além disso, se combinado com a estrutura **`switch`**, pode ser útil para verificar o tipo de uma interface.

``` go
package main

import "fmt"

func Foo(i interface{}) {
    // Imprime uma mensagem dependendo do tipo da interface
    switch v := i.(type) {
    // Inteiros
    case int, int8, int16, int32, int64, uint, uint8, uint16, uint32, uint64:
        fmt.Printf("O valor %d é um número inteiro.\n", v)
    // Strings
    case string:
        fmt.Printf("\"%s\" é uma string.\n", v)
    // Reais
    case float32, float64:
        fmt.Printf("O valor %.1f é um número real.\n", v)
    // Booleanos
    case bool:
        fmt.Printf("O valor %v é booleano.\n", v)
    // Qualquer outro tipo
    default:
        fmt.Printf("Desconheço o tipo %T.\n", v)
    }
}

func main() {
    Foo("Olá, Mundo!")          // -> "Olá, Mundo!" é uma string.
    Foo(10)                     // -> O valor 10 é um número inteiro.
    Foo(2.5)                    // -> O valor 2.5 é um número real.
    Foo(true)                   // -> O valor true é booleano.
    Foo([]int{0, 1, 2})         // -> Desconheço o tipo []int.
}
```

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
    fmt.Println(*ponteiroInteiro) // -> 23
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
    fmt.Println(ponteiroInteiro) // -> <nil>
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
    fmt.Println(valor) // -> 5
}
```
