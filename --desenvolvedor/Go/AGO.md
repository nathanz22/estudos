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
/* Output:
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
