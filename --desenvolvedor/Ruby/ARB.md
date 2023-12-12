# Ruby

## Impressão de Valores

As funções `puts`, `print`, `printf` e `p` permitem imprimir algum valor no terminal.

### `puts`

Imprime uma mensagem ou valor adicionando uma quebra de linha ao final.

``` rb
puts 'Olá, Mundo!'
# Imprime "Olá, Mundo!"
```

### `print`

Semelhante ao `puts`, porém sem a quebra de linha ao final.

Exemplo `print`:

``` rb
print 'Olá, '
print 'Mundo!'
# Imprime "Olá, Mundo!"
```

### `printf`

Formata a mensagem ou valor antes de imprimí-la. É bem semelhante a função `format`.

``` rb
printf 'Valor recebido é de R$%.2f', 100.5231
# Imprime a mensagem, substituindo a formatação pelo valor formatado
```

Assim como a função `print`, a função `printf` não cria uma quebra de linha ao final.

### `p`

Imprime e ao mesmo tempo retorna o valor imprimido.

``` rb
p 22
# => 22
```

## Variáveis

Em Ruby, normalmente os identificadores das variáveis são declaradas em *snake_case*, e os valores são atribuídos após o operador **`=`**.

**Sintaxe:**

``` rb
nome_variavel = valor_variavel
```

## Tipos Primitivos

Em Ruby, os tipos primitivos são:

* **`String`**: Caracteres.
* **`Integer`**: Números inteiros.
* **`Float`**: Números de ponto flutuante.
* **`Symbol`**: Identificadores imutáveis e únicos.
* **`Boolean`**: Valores verdadeiro e falso.
* **`Nil`**: Representa nulo ou a ausência de um valor.

### `String`

Em Ruby, tudo entre aspas simples ou duplas são considerados strings.

**Exemplo:**

``` c
str1 = 'Olá, Mundo!'
str2 = "Olá, Mundo!'
```

#### Métodos de String

* **`upcase`**: Transformatodas as letras da string em maiúsculas.

  ``` rb
  str = 'Olá, Mundo!'
  str.upcase
  # => "OLÁ, MUNDO!"
  ```

* **`downcase`**: Transforma todas as letras da string em minúsculas.

  ``` rb
  str = 'Olá, Mundo!'
  str.downcase
  # => "olá, mundo!"
  ```

* **`capitalize`**: Transforma a primeira letra da string em maiúscula e o resto em minúsculas.

  ``` rb
  str = 'mundo!'
  str.capitalize
  # => "Mundo!"
  ```

* **`reverse`**: Inverte o texto da string.

  ``` rb
  str = 'Olá, Mundo!'
  str.reverse
  # => "!odnuM ,álO"
  ```

* **`length`**, **`.size`**: Retorna a quantidade de caracteres que a string possui.

  ``` rb
  str = 'Olá, Mundo!'
  str.length
  # => 11
  ```

  Ou:

  ``` rb
  str = 'Olá, Mundo!'
  str.size
  # => 11
  ```

* **`strip`**: Remove os espaços em branco no início e no fim da string.

    ``` rb
    str = '     Olá, Mundo!     '
    str.strip
    # => "Olá, Mundo!"
    ```

* **`concat`**, **`+`**: Concatena duas ou mais strings.

    ``` rb
    str1 = 'Olá, '
    str2 = 'Mundo!'

    str1.concat str2
    # => "Olá, Mundo!"
    ```

    Ou:

    ``` rb
    str1 = 'Olá, '
    str2 = 'Mundo!'

    str1 + str2
    # => "Olá, Mundo!"
    ```

* **`index`**: Retorna a posição da primeira ocorrência de uma substring.

    ``` rb
    str = 'Olá, Mundo!'
    str.index 'Mundo!'
    # => 5
    ```

* **`count`**: Retorna quantas vezes uma substring ocorreu na string.

    ``` rb
    str = 'Olá, Mundo! Olá, Todos!'
    str.count 'O' # => 2
    str.count 'o' # => 3
    ```

* **`sub`**: Substitui a primeira ocorrência de uma substring por outra.

    ``` rb
    str = 'Adeus, Mundo!'
    str.sub 'Adeus', 'Olá'
    # => "Olá, MUndo!"
    ```

* **`gsub`**: Substitui todas as ocorrências de uma substring por outra.

    ``` rb
    str = 'dias e dias'
    str.gsub 'dias', 'noites'
    # => noites e noites
    ```

* **`include?`**: Retorna `true` ou `false` se uma substring existir ou não, respectivamente, dentro da string.

    ``` rb
    str = '1, 2, 3, 4, 5, 6, 7, 8'
    str.include? '5' => true
    str.include? '9' => false
    ```

* **`chomp`**: Remove a quebra de linha ao final da string.

    ``` rb
    str = "Olá, Mundo!\n"
    str.chomp
    # => "Olá, Mundo!"
    ```

* **`split`**: Divide a string em um array com base em um delimitador.

    ``` rb
    str = '1, 2, 3, 4, 5, 6, 7, 8'
    str.split ', '
    # => ["1", "2", "3", "4", "5", "6", "7", "8"]
    ```

* **`slice`**, **`[]`**: Formam uma nova string a partir de um índice e, se especificada, quantidade de caracteres contando com esses índices.

    ``` rb
    str = 'Olá, Mundo!'
    str.slice 5, 6
    # => "Mundo!"

    # Ou

    str[5, 6]
    # => "Mundo!"
    ```

  É possível utilizar também com intervalo de índices, que retorna uma substring que começa no índice de início e vai até o índice de fim.

    ``` rb
    str = 'Olá, Mundo!'
    str.slice 5..10
    # => "Mundo!"

    # Ou

    str[5..10]
    # => "Mundo!"
    ```

    Neste caso, é possível omitir o índice de fim, já que vai do índice `5` até o fim da string, ficando `5..`.
    Índices negativos contam da direita para a esquerda, ou seja, `-1` é igual ao último caractere da string.

* **`delete`**: Remove um trecho da string.

    ``` rb
    str = 'Olá, Mundo!'
    str.delete 'Olá, '
    # => "Mundo!"
    ```

* **`casecmp`**: Retorna `-1` caso a primeira string seja menor que a segunda(a primeira string vem antes da segunda em ordem alfabética), `0` se as duas strings forem iguais em termos de ordenação (desconsidera diferenças de maiúsculas e minúsculas), ou `1` se a primeira string for maior que a segunda string(a primeira string vem depois da segunda na ordem alfabética).

    ``` rb
    str = 'Olá'
    str.casecmp 'oLÁ' # =>  1
    str.casecmp 'Olá' # =>  0
    str.casecmp 'olá' # =>  0
    str.casecmp 'álo' # => -1
    ```

#### Interpolação

A interpolação permite adicionar variáveis ou expressões dentro de uma string.

Em Ruby, a interpolação é feita por meio de chaves após o caractere hash (`#{}`). A interpolação pode ser feita somente com o uso de aspas duplas.

``` rb
n1 = 13
n2 = 5
str = "A soma entre #{n1} e #{n2} é #{n1 + n2}."
# => "A soma entre 13 e 5 é 18."
```

### `Integer`

São números inteiros, e com eles é possível fazer operações matemáticas simples.

``` rb
inteiro1 = 5
inteiro2 = -5
inteiro3 = 0
```

### `Float`

### `Symbol`

Símbolos são identificadores imutáveis, geralmente utilizados para representar chaves em hashes.

Não devem estar envoltos em aspas, mas sim possuir `:` no início do nome.

``` rb
my_sym = :simbolo
```

### Símbolo como Chave Hash

Os símbolos podem ser usados como chave em hashes. Nesse caso, a sintaxe se torna bem mais simples:

**Exemplo:**

``` rb
my_hash = {
  nome: 'Paula',
  idade: 19,
  sexo: 'feminino'
}
```

Perceba que não é mais necessário `=>` para atribuir o valor à chave, pois o mesmo é substituído por `:` ao fim do nome.

### Boolean

### Nil

### Conversão de Tipos

Primeiramente, devemos saber como verificar o tipo de um objeto específico. Para isso, existe o método `.class`.

``` rb
str = 'Olá, Mundo!'
num = 13
num_f = 2.2
sym = :abc

str.class   # => String
num.class   # => Integer
num_f.class # => Float
sym.class   # => Symbol
```

#### Conversões

* **`to_i`**, **`.to_int`**: Converte para `Integer`.
* **`to_f`**: Converte para `Float`.
* **`to_s`**: Converte para `String`.
* **`to_sym`**, **`.intern`**: Converte para `Symbol`.
* **`to_c`**: Converte para `Complex`.
* **`to_enum`**: Converte para `Enumerator`.
* **`to_a`**: Converte para `Array`.
* **`to_h`**: Converte para `Hash`

## Atribuição de Método à Variável

Em Ruby, é possível atribuir o valor de retorno de um método ao objeto em que o método está sendo aplicado. Para isso, é utilizado **`!`** ao fim do nome do método.

``` rb
str = 'Olá, Mundo!'
str.upcase!
puts str # Output: OLÁ, MUNDO!
```

> OBS.: Dessa forma o objeto original é substituído.

## Entrada do Usuário

Para que o usuário possa interagir por meio de uma entrada, existe a função `gets`.

``` rb
input = gets
# A variável 'input' vai receber o que o usuário digitou
```

Para criar uma entrada na mesma linha de um texto, você pode fazer o seguinte:

``` rb
print 'Digite alguma coisa: '
input = gets.chomp
puts "Você digitou: #{input}"
```

O método **`chomp`** é utilizado para remover a quebra de linha no final.

## Estruturas Condicionais

Em Ruby, são: `if` / `unless`, `else` e `elsif`.

**Sintaxe:**

``` rb
if (condicao1)
  # Bloco a ser executado caso a condição seja verdadeira
elsif (condicao2)
  # Bloco a ser executado caso a condição seja verdadeira
else
  # Bloco a ser executado se nenhuma condição acima for verdadeira
end
```

**Exemplo:**

``` rb
num = 10
if num > 10
  puts "#{num} é MAIOR que 10"
elsif num == 10
  puts "#{num} é IGUAL a 10"
else
  puts "#{num} é MENOR que 10"
end
```

### `unless`

O `unless` é o oposto do `if`, ou seja, ele executa o bloco abaixo caso sua condição seja falsa.

``` rb
condicao = false
unless condicao
  puts 'A condição é FALSA'
else
  puts 'A condição é VERDADEIRA'
end
```

> OBS.: Não pode haver nenhum `elsif` em estruturas `unless`.

## Operadores

Em Ruby, os principais operadores são:

* Operadores Aritméticos
* Operadores de Comparação
* Operadores Lógicos
* Operador Ternário
* Operadores de Atribuição
* Operador de Concatenação
* Operadores Bitwise

### Operadores Aritméticos

* **`+`**: Operador de adição.
* **`-`**: Operador de subtração.
* **`*`**: Operador de multiplicação.
* **`/`**: Operador de divisão.
* **`%`**: Operador de divisão inteira.
* **`**`**: Operador de potencia.

#### Precedência Aritmética

A ordem de precedência dos operadores aritméticos é feita na seguinte ordem:

1. `()`
1. `**`
1. `+`, `-`
1. `*`, `/`
1. `%`

### Operadores de Comparação

* **`>`**:      Maior.
* **`<`**:      Menor.
* **`==`**:     Igual.
* **`>=`**:     Maior ou igual.
* **`<=`**:     Menor ou igual.

#### Operador de Comparação Combinada

O operador de comparação combinada, representado por **`<=>`**, retorna:

* **`1`**: Caso o valor da esquerda seja maior que o valor da direita.

* **`-1`**: Caso o valor da direita seja maior que o valor da esquerda.

* **`0`**: Caso os valores sejam iguais.

### Operadores Lógicos

Os operadores lógicos são:

* **`&&`**: Todas as expressões devem ser verdadeiras. Lê-se como *and*.

* **`||`**: Pelo menos uma das expressões deve ser verdadeira. Lê-se como *or*.

* **`!`**: Se a expressão for verdadeira, ela se torna falsa, e caso a expressão seja falsa, ela se torna verdadeira. Lê-se como *not*.

### Operador Ternário

O operador ternário permite criar estruturas condicionais simples de maneira mais compacta, onde a declaração é feita em apenas uma linha. Os operadores são **`: ?`**.

**Exemplo:**

``` rb
condicao = true
puts condicao ? 'Verdadeiro' : 'Falso'
# Output: Verdadeiro
```

Primeiro o valor **booleano**, em seguida, **`?`** para `if` e **`:`** para `else`.

## Arrays

Existem duas formas de declarar um array:

1. Declaração literal:

  ``` rb
  my_array = []
  ```

1. `Array.new`:

  ``` rb
  my_array = Array.new
  ```

Exemplo de array:

``` rb
my_array = [22, 'Olá, Mundo!', true, 1.3]
# => [22, "Olá, Mundo!", true, 1.3]
```

### Acesso aos Elementos do Array

É usada a Notação de Colchetes com o índice de uma elemento específico.

``` rb
my_array = [2, 22, 13]
my_array[0] # => 2
my_array[1] # => 22
my_array[2] # => 13
```

Índices negativos referenciam os elementos da direita para a esquerda.

``` rb
my_array = [2, 22, 13]
my_array[-1] # => 13
my_array[-2] # => 22
my_array[-3] # => 2
```

### Array Multidimensional

Assim é chamado um array que tem como elementos internos outros arrays. Por exemplo:

``` rb
my_array = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]
```

Para acessar um elemento dentro de um array interno, deve ser passado dois índices dentro de colchetes.

``` rb
my_array[0][1] # => 2
my_array[1][1] # => 5
my_array[2][2] # => 9
```

### Array de Palavras

Um array composto apenas de palavras pode ser escrito com `%w` ou `%W`, podendo ser omitidos as aspas e as vírgulas.

Sendo assim, o array:

``` rb
my_array = ['Ruby', 'JavaScript', 'Python', 'PHP', 'Go']
```

Pode ser escrito:

``` rb
my_array = %w[Ruby JavaScript Python PHP Go]
```

Ambos os exemplos acima correspondem ao mesmo array.

### Métodos de Array

#### Adicionar/Remover Elementos

* **`push`**: Adiciona um ou mais elementos ao final do array.

  ``` rb
  my_array = ['a', 'b', 'c']
  my_array.push 'd'
  # => ["a", "b", "c", "d"]
  ```

* **`unshift`**: Adiciona um ou mais elementos ao início do array.

  ``` rb
  my_array = [3, 4, 5]
  my_array.unshift 1, 2
  # => [1, 2, 3, 4, 5]
  ```

* **`pop`**: Exclui o último elemento do array e o retorna.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  del = my_array.pop # => 5
  # [1, 2, 3, 4]
  ```

* **`shift`**: Exclui o primeiro elemento do array e o retorna.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  del = my_array.shift # => 1
  # [2, 3, 4, 5]
  ```

* **'`delete_at`'**: Exclui o elemento de um índice específico e o retorna.

  ``` rb
  my_array = %w[A B C D E]
  my_array.delete_at 2 # => C
  my_array # => ["A", "B", "D", "E"]
  ```

* **'`delete`'**: Exclui todas as ocorrências de um elemento específico.

  ``` rb
  my_array = [3, 2, 5, 1, 5, 6]
  my_array.delete 5 # => 5
  my_array # => [3, 2, 1, 6]
  ```

* **'`delete_if`'**: Exclui todos os elementos do array que testarem verdadeiro para uma expressão.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.delete_if(&:even?)
  my_array # => [1, 3, 5]
  ```

* **'`keep_if`'**: Mantém no array apenas os elementos que testarem verdadeiro para uma expressão.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.keep_if(&:even?) # => [2, 4]
  ```

* **'`insert`'**: Adiciona um ou mais elementos a partir de um índice específico do array.

  ``` rb
  my_array = [3, 5]
  my_array.insert 1, 7, 9, 11
  my_array # => [3, 1, 7, 9, 11, 5]
  ```

  O primeiro argumento (`1`) é o índice o qual os elementos irão ser adicionados.

> Todos esses métodos alteram o array original.

#### Captura de Elementos

* **'`first`'**: Retorna o primeiro elemento do array (como `array[0]`).

  ``` rb
  my_array = [2, 3, 4, 5, 6, 7]
  my_array.first # => 2
  ```

* **'`last`'**: Retorna o último elemento do array (como `array[-1]`).

  ``` rb
  my_array = [2, 3, 4, 5, 6, 7]
  my_array.last # => 7
  ```

* **'`take`'**: Retorna um array com os primeiros n elementos.

  ``` rb
  my_array = [5, 10, 15, 20, 25]
  my_array.take 3 # => [5, 10, 15]
  ```

* **'`drop`'**: Retorna um array com todos os elementos, menos os n primeiros.

  ``` rb
  my_array = [5, 10, 15, 20, 25]
  my_array.drop 3 # => [20, 25]
  ```

* **`concat`**, **`+`**: Concatena dois ou mais arrays e um novo array.

  ``` rb
  array1 = [1, 2, 3]
  array2 = ['a', 'b', 'c']
  array3 = array1.concat array2
  # => [1, 2, 3, "a", "b", "c"]
  ```

  Ou:

  ``` rb
  array1 = [1, 2, 3]
  array2 = ['a', 'b', 'c']
  array3 = array1 + array2
  # => [1, 2, 3, "a", "b", "c"]
  ```

#### Pesquisa de Elementos

* **`include?`**: Verifica se um elemento está presente dentro do array. Se presente, retorna `true`, em caso contrário, retorna `false`.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.include? 2 # => true
  my_array.include? 7 # => false
  ```

* **`index`**: Retorna o índice do elemento especificado dentro do array. Caso o elemento não exista dentro do array, retorna `nil`.

  ``` rb
  my_array = ['a', 'b', 'c', 'd']
  my_array.index 'b' # => 1
  my_array.index 'e' # => nil
  ```

* **`count`**: Retorna a quantidade de aparições de um elemento dentro de um array.

  ``` rb
  my_array = [2, 5, 2, 3, 1, 2]
  my_array.count 2 # => 3
  ```

#### Organização de Elementos

* **`uniq`**: Retorna um array com elementos únicos.

  ``` rb
  my_array = [1, 2, 2, 3, 3, 1]
  my_array.uniq # => [1, 2, 3]
  ```

* **'`sort`'**: Retorna um array organizado em ordem alfabética ou numérica.

  No caso de número:

  ``` rb
  my_array = [5, 6, 2, 3, 1, 4, 7, 9, 8]
  my_array.sort
  # => [1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```

  No caso de strings:

  ``` rb
  my_array = %w[e u o a i]
  my_array.sort
  # => ["a", "e", "i", "o", "u"]
  ```

  > Se no array que foi aplicado o método `sort` exista strings e números ocorrerá o erro (**`ArgumentError`**).

#### Iteradores de Array

* **'`each`'**: Itera sobre cada elemento do array.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.each { |e| puts e * 2 }
  # Output:
  # 2
  # 4
  # 6
  # 8
  # 10
  ```

* **`collect`**, **`map`**: Aplica a expressão de um bloco a cada elemento de um array.

  ``` rb
  array = [1, 2, 3, 4, 5]
  array.collect { |i| i * 2 }
  # => [2, 4, 6, 8, 10]
  ```

#### Seleção de Elementos

* **`select`**: Cria um novo array apenas com os elementos que testam verdadeiro para uma expressão.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.select { |n| n.odd? }
  # => [1, 3, 5]
  ```

  Seria o mesmo que:

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.select(&:odd?)
  # => [1, 3, 5]
  ```

* **'`reject`'**: Cria um novo array apenas com os elementos que testam falso para uma expressão.

  ``` rb
  my_array = [1, 2, 3, 4, 5]
  my_array.reject(&:even?)
  # => [1, 3, 5]
  ```

## Estruturas de Repetição e Iteradores

### `for`

Repete um bloco em uma quantidade específica de vezes, baseado em um intervalo.

``` rb
for num in 0...10
  puts num
end
# Imprime de 0 a 9
```

Este é um intervalo exclusivo, onde é considerado o primeiro valor (0) e desconsiderado o último (10).

Para um intervalo inclusivo, ou seja, considerando o último valor, use **`..`** ao invés de `...`.

``` rb
for num in 0..10
  puts num
end
# Imprime de 0 a 10
```

### `while`

Repete um bloco enquanto sua condição for verdadeira.

``` rb
c = 0
while c <= 10
  puts c
  c += 1
end
# Imprime de 0 a 10
```

### `until`

É como o `while`, só que ao contrário, pois repete um bloco enquanto sua condição for falsa.

``` rb
c = 0
until c > 10
  puts c
  c += 1
end
# Imprime de 0 a 10
```

### `loop`

A função `loop` repete um bloco infinitamente, interrompendo apenas com `break` ou `return`(caso esteja dentor de uma função).
A função `loop` aceita um bloco como repetição.

``` rb
c = 0
loop do
  break if c > 10
  puts c
  c += 1
end
# Imprime de 0 a 10
```

Aqui também um exemplo de `loop` infinito.

``` rb
loop { puts 'Olá, Mundo!' }
```

### Controle de Fluxo

#### `break`

A palavra-chave `break` interrompe uma repetição.

``` rb
for c in (0..30)
  puts c
  break if c == 10
end
# Imprime de 0 a 10
```

#### `next`

A palavra-chave `next` pula para a próxima repetição.

``` rb
for c in (0..20)
  next if c.odd?
  puts c
end
# Imprime os números pares entre 0 e 20
```

### Iteradores

#### `each`

Repete um bloco em uma quantidade de vezes que a quantidade de elementos dentro do objeto. Se aplicado a uma string, repetirá na mesma quantidade de caracteres.

``` rb
nums = [1, 2, 3, 4, 5]
num.each { |num| puts num }
# Imprime cada número do array
```

O mesmo seria:

``` rb
nums = [1, 2, 3, 4, 5]
num.each do |num|
  puts num
end
# Imprime cada número do array
```

#### `times`

Executa um bloco em uma quantidade específica de vezes. É como um `for`, porém mais simples e compacto.

``` rb
15.times { |n| puts n }
# Imprime os números de 0 a 14
# => 15
```

Este método retorna a quantidade de repetições.

#### `upto` e `downto`

Permitem iterar sobre valores específicos em um sequência, sendo `upto` para iterar de forma crescente e `downto` para decrescente.

``` rb
50.upto(55) { |n| puts n }
# Imprime de 50 a 55

50.downto(45) { |n| puts n }
# Imprime de 50 a 45
```

Dessa forma, é possível iterar até mesmo sobre letras.

``` rb
'a'.upto('z') { |v| puts v }
# Imprime as letras de "a" a "z".
```

## Funções

Em Ruby, as função são criadas a partir da palavra-chave **`def`**, e após ela deve vir o nome e parâmetros (opcional) da função.

**Sintaxe:**

``` rb
def nome_funcao(param1, param2, ..., param5)
  declaraçao
end
```

Exemplo de função:

``` rb
def dobro(num)
  puts "O dobro de #{num} é #{num * 2}."
end
```

### Chamada de Funções

Simplesmente escrever o nome da função já a chama.

``` rb
def saudacao(nome)
  puts "Olá, #{nome}!"
end

saudacao 'Mundo'
# Imprime "Olá, Mundo!"
```

> **OBS.:** Em Ruby, não há a necessidade de parênteses após o nome da função, a não ser para as funções que recebem um bloco entre chaves, nesse caso é obrigatório o uso de parênteses.

### Múltiplos Argumentos

Caso o número de argumento seja indefinido, podendo não ser a mesma quantidade em diferentes execuções da função, é possível fazer com que esses argumentos se agrupem dentro de um array. Para isso, é adicionado um asterisco (**`*`**) antes do nome do parâmetro.

``` rb
def multi_dobro(*num)
  num.each { |n| print "#{n * 2} " }
end

multi_dobro 5, 2, 4, 3, 13
# Imprime: 10, 4, 8, 6, 26
```

### Retorno

A palavra-chave **`return`** retorna algum valor, encerrando a função no mesmo momento.

``` rb
def saudacao(nome)
  return "Olá, #{nome}!"
end

saudacao 'Mundo'
# => "Olá, Mundo!"
```

Caso não haja nenhum retorno em uma função, ela retorna **`nil`**.

#### Retorno Implícito

Em Ruby, é retornado automaticamente o valor da última expressão calculada dentro da função.

``` rb
def soma_nums(num1, num2)
  num1 + num2
end

soma_nums 13, 22
# => 35
```

> Caso o valor a ser retornado esteja dentro de um laço de repetição, o retorno precisa ser explícito (`return`).

## Hashes

Existem duas formas de declarar um hash:

1. Declaração literal:

  ``` rb
  my_hash = {}
  ```

1. `Hash.new`:

  ``` rb
  my_hash = Hash.new
  ```

Exemplo de hash:

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}
# => => {"nome"=>"João", "idade"=>18, "sexo"=>"masculino"}
```

Em um hash, existem as chaves(*keys*) e os valores(*values*).
No exemplo acima, as chaves são: `'nome'`, `'idade'` e `'sexo'`.
E os valores são: `'João'`, `18` e `'masculino'`.

### Acesso aos Dados do Hash

É usado uma chave para referenciar um valor por meio de Notação de Colchetes.

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}

my_hash['nome']
# => "João"
```

### Adicionar/Substituir Dados

Para **adicionar dados a um hash**, é necessário atribuir o valor desejado à chave desejada.

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}

my_hash['altura'] = 1.79
# 'my_hash' será: {"nome"=>"João", "idade"=>18, "sexo"=>"masculino", "altura"=>1.79}
```

Para **substituir o valor** de uma chave já existente, basta atribuir um novo valor a essa chave.

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}

my_hash['idade'] = 29
# 'my_hash' será: {"nome"=>"João", "idade"=>29, "sexo"=>"masculino"}
```

### Iterando Sobre o Hash

Utilizando o método **`each`** e passando os nomes para as variáveis relativas às chaves e ao valores, podemos iterar sobre um hash.

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}

my_hash.each { |k, v| puts "#{k}: #{v}"}
# Imprime: nome: João
#          idade: 18
#          sexo: masculino
```

Para iterar apenas sobre as chaves ou apenas sobre os valores, você pode usar os métodos **`each_key`** e **`each_value`**.

``` rb
my_hash = {
  'nome' => 'João',
  'idade' => 18,
  'sexo' => 'masculino'
}

my_hash.each_key { |k| puts k }
# Imprime: nome
#          idade
#          sexo

my_hash.each_value { |v| puts v }
# Imprime: João
#          18
#          masculino
```

### Valor Padrão Para Chaves

Caso haja uma solicitação para uma chave inexistente, será retornado **`nil`**, mas caso queira um valor padrão nesses casos, você pode especificar na declaração do hash.

``` rb
my_hash = Hash.new 'Nada aqui!'
# => {}

my_hash['chave1']
# => "Nada aqui!"
```

## Método `respond_to?`

Verifica se algum método pode ser aplicado a um objeto específico, retornando **`true`**, se sim, ou **`false`**, em caso contrário. O método deve ser passado em forma de símbolo.

**Exemplo:**

``` rb
num = 22
num.respond_to? :next   # => true
num.respond_to? :length # => false
```

## Métodos *Yield*

Assim são chamados os métodos que aceitam um bloco. Esses métodos usam esses blocos para transferir o controle da chamada para o bloco e vice-versa.

Exemplos de blocos *yield's* são `each` e `map`, mas também é possível criar métodos desse tipo.

``` rb
def abc(nome)
  yield nome
end

abc('Luana') { |n| puts "Olá, #{n}!" }
```

## Procs e Lambdas

### Procs

São blocos reutilizáveis salvos em uma variável.

``` rb
par = proc do |n|
  n.even?
end

(0..10).to_a.select(&par)
# => [0, 2, 4, 6, 8, 10]
```

O **`&`** converte o proc em um bloco, e deve ser usado sempre que um método espera um bloco como argumento.

### Lambdas

Assim como um proc, uma lambda é um bloco armazenado dentro de uma variável, e sua sintaxe é inclusive a mesma, trocando apenas `proc` por `lambda` (ou `->`).

``` rb
nums = [1, 2, 3, 4, 5]
quadrado = lambda { |n| n * 2 }

nums.map(&quadrado)
# => [2, 4, 6, 8, 10]
```

Podemos substituir `lambda` por **`->`** e passar o elemento entre parênteses. O resultado será o mesmo.

``` rb
nums = [1, 2, 3, 4, 5]
quadrado = ->(n) { n * 2 }
nums.map(&quadrado)
# => [2, 4, 6, 8, 10]
```

### Procs vs. Lambdas

Procs e Lambdas possuem duas diferenças:

1. As lambdas verificam o número de argumentos passados a ela, ou seja, uma lambda lançará um erro caso passado o número errado de argumentos, enquanto um proc ignora argumentos inesperados, atribuindo `nil` a qualquer um que estiver faltando.

1. Ao retornar um valor (`return`), as lambdas não interromper o método, ao contrário dos procs.

``` rb
def lambda_ex
  l = -> { return 'Retorno da lambda' }
  l.call
  'Retorno ao fim da lambda'
end

def proc_ex
  p = proc { return 'Retorno do proc' }
  p.call
  'Retorno ao fim do proc'
end

lambda_ex # => "Retorno ao fim da lambda"
proc_ex   # => "Retorno do proc"
```

### Método `call`

O método **`call`** permite chamar procs e lambdas de forma simples.

``` rb
oi = proc { puts "Olá!" }
oi.call
# Imprime "Olá!"
```

### Métodos Para Blocos

Usando o nome de um método e adicionando **`:`** ao início, fará com que se torne um símbolo. Adicionar **`&`** antes desse símbolo, fará com que se torne um bloco. Então fica: **`&:metodo`**.

``` rb
array = ['1', '2', '3']
array.map!(&:to_i)
# => [1, 2, 3]

# Forma simplificada comparada com:

array.map! { |e| e.to_i }
```

## Tratamento de Erros

Para tratar erros, são usadas as estruturas **`begin`** (caso já não esteja dentro de uma estrutura), **`rescue`**, **`else`** e **`ensure`**.

1. **`begin`**: Contém o trecho de código que pode ocorrer uma exceção (erro).
  É apenas necessário caso o bloco em que pode ocorrer a exceção já não esteja dentro de uma estrutura

1. **`rescue`**: Executa um bloco ao capturar uma exceção.

1. **`else`**: Executa um bloco caso não ocorra nenhuma exceção.

1. **`ensure`**: Executa independentemente de ter ou não ocorrido alguma exceção.

``` rb
begin
  # Código com possibilidade de erro
rescue ExcecaoTipo1
  # Executado caso ocorra a 'ExcecaoTipo1'
rescue ExcecaoTipo2
  # Executado caso ocorra a 'ExcecaoTipo2'
else
  # Executado caso não ocorra exceções
ensure
  # Será executado não importa o que aconteça
end
```

Abaixo um exemplo que verifica se um valor é par ou ímpar. É lançado uma exceção caso o valor passado pelo usuário não seja um número inteiro.

``` rb
loop do
  print 'Digite um número: '
  num = Integer(gets.chomp)
  puts num.even? ? "O número #{num} é PAR" : "O número #{num} é ÍMPAR!"
  break
rescue ArgumentError
  puts 'ERRO | O valor digitado deve ser um número inteiro.'
  # Quando 'num' não receber um valor válido
rescue Interrupt
  puts "\nINTERRUPÇÃO | O usuário preferiu encerrar o programa."
  break
  # Caso o usuário force a interrupção do programa
end
```

Perceba que `loop do` substitui `begin`, pois o código com potencial de erro já está dentro de uma estrutura.

A primeira exceção tratada foi `ArgumentError`, que é lançada quando o valor é diferente de um número inteiro neste caso.

A segunda exceção tratada foi `Interrupt`, que é lançada quando o usuário encerra o script.

### Método `raise`

É usado para lançar uma exceção explicitamente, inclusive com uma mensagem personalizada se desejado.

A sintaxe é a seguinte:

``` rb
raise TipoExcecao, 'Mensagem de erro(opcional)'
```

Exemplo:

``` rb
def divide(x, y)
  raise ZeroDivisionError, 'Não pode dividir por zero'
  x / y
end
```

A mensagem não deve conter acentos e alguns caracteres, ou não será exibida.

Caso `raise` seja escrito sozinho, irá relançar a exceção capturada.

## Classes

Ruby é uma linguagem de programação orientada a objetos, o que significa que ela manipula objetos.

Uma classe é construída a partir da palavra-chave **`class`**, e após isso, o nome da classe.

A sintaxe é a seguinte:

``` rb
class NomeClasse
  # Conteúdo da class
end
```

### Método `initialize`

Este método é executado sempre que uma nova instância de uma class for criada usando o método **`new`**. Geralmente, é onde são dafinidas as variáveis de instância. **O método `initialize` é opcional**.

Os parâmetros deste método devem ser recebidos assim que criada uma nova instância de uma classe.

``` rb
class Pessoa
  def initialize(nome)
    puts "Olá, #{nome}!"
  end
end

Pessoa.new 'Mundo'
# Imprime "Olá, Mundo!"
```

### Variáveis de Instância

Variáveis de instância são variáveis que pertencem a uma instância específica de uma classe, ou seja, podem existir dois objetos com a mesma classe com variáveis de instância com valores diferentes.

Variáveis de instância são declaradas com **`@`** no início do nome da variável.

``` rb
class Pessoa
  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end

  def apresentacao
    puts "Olá! Meu nome é #{@nome} e eu tenho #{@idade} anos."
  end
end

pessoa1 = Pessoa.new 'Matheus', 23
pessoa1.apresentacao
```

A função `apresentacao` utilizada essas variáveis de instância para imprimir uma mensagem.

### Variáveis de Classe

São variáveis que, ao definir ou alterar seu valor em uma instância, altera também em todas as outras instâncias. Ou seja, em todas as instâncias as variáveis de classe terão o mesmo valor.

Essas variáveis são declaradas com **`@@`** ao início do nome da variável.

``` rb
class NomeClasse
  @@var1 = 2
  @@var2 = 5
end
```

### Variáveis Globais

São variáveis que possuem o escopo global, ou seja, podem ser usadas e alteradas em qualquer lugar do código.

Elas são declaradas com **`$`** ao início do nome da variável.

``` rb
$global_var = 'Olá, Mundo!'

def mostrar_global_var
  puts $global_var
end

mostrar_global_var
# Imprime "Olá, Mundo!"
```

### *Inheritance* (Herança)

Herança é o processo pelo qual uma classe assume os atributos e métodos de uma outra classe. Essa relação de classes é feita por meio do caractere **`<`**, onde a classe da esquerda herdará da classe da direita.

``` rb
class Error
  def print_erro
    puts 'Error! Error!'
  end
end

class OtherError < Error
  ###
end

oe = OtherError.new
oe.print_erro
# Imprime "Error! Error!"
```

#### Substituição de Métodos

É possível substituir métodos da classe pai para a classe que está herdando. Para isso, deve ser recriado o método com o mesmo nome.

``` rb
class Error
  def print_erro
    puts 'Error! Error!'
  end
end

class OtherError < Error
  def print_erro
    puts 'Other Error!'
  end
end

oe = OtherError.new
oe.print_erro
# Imprime "Other Error!"
```

#### Execução do Método Original

Com o método **`super`** é possível executar a versão original do método.

``` rb
class Error
  def print_erro
    puts 'Error! Error!'
  end
end

class OtherError < Error
  def print_erro
    super
  end
end

oe = OtherError.new
oe.print_erro
# Imprime "Error! Error!"
```

Caso necessário, podem ser passados parâmetros para **`super`**.

### Restrições a Métodos

#### *Public Methods*

Não há restrições quanto aos métodos públicos. Eles podem ser chamados de dentro ou de fora da classe em que foram definidos.

Qualquer objeto ou instância da classe possuem permissão para acessar métodos públicos definidos a classe.

Ao definir um método, automaticamente ele se torna público ao menos que definido manualmente para privado. Mesmo assim você pode explicitamente dizer que é um método público, definindo **`public`** uma linha antes de definir o método.

``` rb
class MyClass

  public

  def metodo_publico
    'Isto é um método público!'
  end
end
```

#### *Private Methods*

Os métodos privados só podem ser chamados de dentro da própria classe em que foram definidos ou em subclasses (classes que herdam de uma outra classe).

Um método se torna privado ao definir ‘private’ uma linha antes de definir o método.

``` rb
# Classe
class MinhaClasse

  private

  def metodo_privado
    'Isto é um método privado!'
  end
end

# Subclasse
class SubClasse < MinhaClasse
  def print_metodo_privado
    puts metodo_privado
  end
end
```

Será lançado uma exceção quando é chamado um método privado.

``` rb
obj = MinhaClasse.new
obg.metodo_privado
# Ocorrerá um erro
```

### Métodos de Atributo

Os métodos de atributo são usados para definir automaticante um método para cada atributo em uma classe, criando ***getters***, ***setters*** ou ambos.

#### `attr_reader`

Define automaticamente um método de leitura para um ou mais atributos. Os atributos devem ser passados em forma de símbolo.

A sintaxe é a seguinte:

``` rb
attr_reader :atributo1, :atributo2
```

Então, ao invés de:

``` rb
class Pessoa
  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end

  def nome
    @nome
  end

  def idade
    @idade
  end
end
```

Podemos fazer:

``` rb
class Pessoa
  attr_reader :nome, :idade

  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end
end
```

Dessa forma, são criados automaticamente os métodos ***getters*** para `nome` e `idade` por meio do método **`attr_reader`**.

#### `attr-writer`

Define automaticamente um método para redefinição de um atributo.

A sintaxe é a seguinte:

``` rb
attr_writer :atributo1, :atributo2
```

Então, ao invés de:

``` rb
class Pessoa
  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end

  def name=(novo_nome)
    @nome = novo_nome
  end

  def idade=(nova_idade)
    @idade = nova_idade
  end
end
```

Podemos fazer o seguinte:

``` rb
class Pessoa
  attr_writer :nome, :idade

  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end
end
```

> É comum que os métodos de definição, como os gerados por `attr_writer` possuam o operador de atribuição ao final, indicando sua função.

#### `attr_accessor`

Este método é junção dos dois anteriores (`attr_reader` e `attr_writer`), ou seja, ele cria automaticamente os métodos ***getters*** e ***setters***.

``` rb
attr_accessor :nome, :idade

  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end
```

### Métodos de Classe

Métodos de classe são métodos para a própria classe, e não para uma instância dessa classe.

Um método de classe possui **`self`** e um ponto `.` antes do nome do método.

``` rb
class NomeClasse
  def self.metodo_de_classe
    'Eu sou um método de classe!'
  end
end
```

Além disso, métodos de classes podem ser chamados sem que haja uma instância, utilizando apenas o nome da classe e depois o método.

``` rb
class NomeClasse
  def self.metodo_de_classe
    'Eu sou um método de classe!'
  end
end

NomeClasse.metodo_de_classe
# => "Eu sou um método de classe!"
```
