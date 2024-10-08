# Ruby

Ruby é uma linguagem de programação dinâmica, de alto nível e orientada a objetos. Foi criada no Japão por Yukihiro "Matz" Matsumoto na década de 1990, com o objetivo de combinar a simplicidade com a praticidade do Perl com a orientação a objetos do Smalltalk.

Ruby é uma linguagem interpretada, o que significa que o código é executado pelo interpretador Ruby, em vez de ser compilado para código de máquina. Isso torna Ruby mais rápido para aprender e usar, mas também significa que o código Ruby é mais lento do que o código compilado.

Ruby é uma linguagem popular, usada para desenvolver uma variedade de aplicações, incluindo aplicações web, móveis, de servidor e de desktop.

Além disso, Ruby possui diversas gems, que são bibliotecas de código reutilizáveis que podem ser adicionados ao código.

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

Imprime e ao mesmo tempo retorna o valor imprimido como uma string.

``` rb
str = p "Olá, Mundo!\n"
puts str
# Output:
# "Olá, Mundo!\n"
# Olá, Mundo!
```

## Variáveis

Em Ruby, normalmente os identificadores das variáveis são declaradas em *snake_case*, e os valores são atribuídos após o operador **`=`**.

**Sintaxe:**

``` rb
nome_variavel = valor_variavel
```

## Tipos Primitivos

Em Ruby, os principais tipos primitivos são:

* **`String`**: Caracteres.
* **`Integer`**: Números inteiros.
* **`Float`**: Números de ponto flutuante.
* **`Symbol`**: Identificadores imutáveis e únicos.
* **`Boolean`**: Valores verdadeiro e falso.
* **`Nil`**: Representa nulo ou a ausência de um valor.

### Tipo `String`

Strings podem ser declaradas de duas maneiras:

* **String literal:**

  ``` rb
  str1 = 'Olá, Mundo!'
  str2 = 'Olá, Ruby!'
  ```

* **Com `String.new`:**

  ``` rb
  str1 = String.new 'Olá, Mundo!'
  str2 = String.new 'Olá, Ruby!'
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

### Tipo `Integer`

São números inteiros, e com eles é possível fazer operações matemáticas simples.

``` rb
inteiro1 = 5
inteiro2 = -5
inteiro3 = 0
```

#### Operações Matemáticas

São feitas utilizando os operadores aritméticos.

* **'`+`'**: Soma.
* **'`-`'**: Subtração.
* **'`*`'**: Multiplicação.
* **'`/`'**: Divisão.
* **'`%`'**: Resto da Divisão.
* **'`**`'**: Exponenciação.

**Exemplo:**

``` rb
5 + 2     # => 7
5 - 2     # => 3
5 * 2     # => 10
5 / 2     # => 2
5 % 2     # => 1
5 ** 2    # => 25
```

Perceba que a divisão entre 5 e 2 resulta em 2 ao invés de 2.5. Isso acontece porque a operação é feita com dois inteiros, dando a entender que o resultado também deve ser um número inteiro. Para resolver isso, você pode tornar um dos operandos um número real (de ponto flutuante).

**Exemplo:**

``` rb
5 / 2.0    # => 2.5
15.0 / 2   # => 7.5
```

#### Métodos para Inteiros

* **'`abs`'**: Retorna o número valor absoludo do número.

  ``` rb
  5.abs      # => 5
  -51.abs    # => 51
  0.abs      # => 0
  ```

* **'`chr`'**: Retorna uma string contendo o caractere que tal número corresponde.

  ``` rb
  puts 82.chr   # => R
  puts 117.chr  # => u
  puts 98.chr   # => b
  puts 121.chr  # => y
  ```

  É possível especificar o *enconding* como argumento.

* **'`digits`'**: Retorna um array contendo os algarismos da conversão do número inteiro para uma base específica.

  ``` rb
  10.digits 2   # => [0, 1, 0, 1]
  10.digits 8   # => [2, 1]
  10.digits 16  # => [10]
  ```

  No exemplo acima, o número 10 é convertido para a base 2, 8 e 16, e para cada uma das conversões é gerado um array que armazena cada algarismo do valor já na base convertida.

* **'`div`'**: Retorna o resultado da divisão inteira do número inteiro por um número passado como argumento.

  ``` rb
  10.div 2    # => 5
  22.div 11   # => 2
  5.div 2     # => 2
  ```

* **'`fdiv`'**: Retorna o resultado da divisão real do número inteiro pelo número passado como argumento.

  ``` rb
  puts 10.fdiv 2    # => 5.0
  puts 22.fdiv 11   # => 2.0
  puts 5.fdiv 2     # => 2.5
  ```

* **'`remainder`'**: Retorna o resto da divisão do inteiro com o número passado como argumento.

  ``` rb
  5.remainder 2    # => 1
  25.remainder 7   # => 4
  2.remainder 1    # => 0
  ```

* **'`divmod`'**: Retorna um array que contém o resultado da divisão e o resto da divisão do número inteiro pelo número passado como argumento.

  ``` rb
  10.divmod 2    # => [5, 0]
  22.divmod 11   # => [2, 0]
  5.divmod 2     # => [2, 1]
  ```

  O primeiro elemento do array é o resultado da divisão inteira, e o segundo é o resto da divisão.

* **'`pow`'**: Eleva o inteiro pelo número passado como argumento.

  ``` rb
  5.pow 2     # => 25
  2.pow 3     # => 8
  7.pow 1     # => 7
  3.pow 0     # => 1
  ```

* **'`pred`'**: Retorna o predecessor do número.

  ``` rb
  5.pred   # => 4
  10.pred  # => 9
  7.pred   # => 6
  ```

* **'`succ`', '`next`'**: Retorna o sucessor do número.

  ``` rb
  # Com `succ`
  5.succ   # => 6
  10.succ  # => 11
  7.succ   # => 8

  # Com `next`
  5.next   # => 6
  10.next  # => 11
  7.next   # => 8
  ```

* **'`gcd`'**: Retorna o maior divisor comum de dois inteiros.

  ``` rb
  25.gcd 60    # => 5
  21.gcd 84    # => 21
  92.gcd 6     # => 2
  ```

  O resultado é sempre o valor absoluto, e por isso é sempre positivo.

* **'`lcm`'**: Retorna o menor múltiplo comum de dois inteiros.

  ``` rb
  25.lcm 60    # => 300
  21.lcm 84    # => 84
  92.lcm 6     # => 276
  ```

* **'`gcdlcm`'**: Retorna um array de dois elementos:

  1. O maior divisor comum dos dois inteiros.
  1. O menor múltiplo comum dos dois inteiros.

  ``` rb
  25.gcdlcm 60    # => [5, 300]
  21.gcdlcm 84    # => [21, 84]
  92.gcdlcm 6     # => [2, 276]
  ```

* **'`even?`'**: Retorna verdadeiro se o número for par.

  ``` rb
  20.even?    # => true
  31.even?    # => false
  0.even?     # => true
  ```

* **'`odd?`'**: Retorna verdadeiro se o número for ímpar.

  ``` rb
  15.odd?    # => true
  22.odd?    # => false
  0.odd?     # => false
  ```

* **'`zero?`'**: Retorna verdadeiro se o número for igual a zero.

  ``` rb
  0.zero?   # => true
  21.zero?  # => false
  13.zero?  # => false
  ```

* **'`positive?`'**: Retorna verdadeiro se o número for positivo.

  ``` rb
  x = 5
  y = -3
  z = 0

  x.positive?  # => true
  y.positive?  # => false
  z.positive?  # => false
  ```

* **'`negative?`'**: Retorna verdadeiro se o número for negativo.

  ``` rb
  x = 5
  y = -3
  z = 0

  x.negative?  # => false
  y.negative?  # => true
  z.negative?  # => false
  ```

* **'`size`'**: Retorna a quantidade de bytes que o número ocupa na memória.

  ``` rb
  15.size
  (-221**3).size
  (210**10).size
  ```

  O resultado pode variar, mas normalmente ocupa 4 ou 8 bytes.

##### Métodos de `Integer`

* **'`Integer.sqrt`'**: Retorna a raiz quadrada de um número inteiro.

  ``` rb
  Integer.sqrt 25  # => 5
  Integer.sqrt 100 # => 10
  ```

* **'`Integer.try_convert`'**: Se o argumento recebido for um inteiro, retorna o próprio objeto. Se não for um inteiro, tenta fazer a conversão com `to_int`, e se a conversão for bem-sucedida, retorna o resultado da conversão, caso contrário, retorna `nil`.

  ``` rb
  Integer.try_convert 5    # => 5
  Integer.try_convert 2.4  # => 2
  Integer.try_convert 'A'  # => nil
  ```

### Tipo `Float`

Representa números de reais (de ponto flutuante), e permite realizar operações matemáticas simples.

**Exemplo:**

``` rb
x = 5.1
y = -1.0
z = 4.91
```

#### Operações Matemáticas com Float

Para realizar operações matemáticas são utilizados os operadores aritméticos.

**Exemplo:**

``` rb
12151.21.5 + 3        # => 24.5
42.1 - 21.9     # => 20.200000000000003
30 * 2.1        # => 63.0
99.4 / 21.3     # => 4.666666666666667
9 % 2.0         # => 1.0
22.99 ** 3      # => 12151.136898999997
```

#### Métodos para Números Reais

* **`zero?`**: Retorna verdadeiro se o número for igual a zero.

  ``` rb
  x = 5.23
  y = 0.0
  z = 0.1

  x.zero?  # => false
  y.zero?  # => true
  z.zero?  # => false
  ```

* **'`positive?`'**: Retorna verdadeiro se o número for positivo.

  ``` rb
  x = 5.3
  y = -21.4
  z = 0

  x.positive?  # => true
  y.positive?  # => false
  z.positive?  # => false
  ```

* **'`negative?`'** Retorna verdadeiro se o número for negativo.

  ``` rb
  x = 5.3
  y = -21.4
  z = 0

  x.negative?  # => false
  y.negative?  # => true
  z.negative?  # => false
  ```

* **'`finite?`'**: Retorna verdadeiro se o número for finito.

  ``` rb
  x = 21.5
  y = Float::INFINITY

  x.finite?    # => true
  y.finite?    # => false
  ```

* **'`infinity?`'**: Retorna `1` se o número for infinito, `-1` se o número for infinito negativo e `nil` se o número não for infinito.

  ``` rb
  x = Float::INFINITY
  y = -Float::INFINITY
  z = 123.20183912

  x.infinite?    # => true
  y.infinite?    # => false
  z.infinite?    # => nil
  ```

* **'`nan?`'**: Retorna verdadeiro se o número for `NaN` (Not-a-Number).

  ``` rb
  x = 0.0 / 0.0
  y = Float::NAN
  z = 45.23

  x.nan?    # => true
  y.nan?    # => true
  z.nan?    # => false
  ```

* **'`abs`'**: Retorna o valor absoluto do número.

  ``` rb
  x = 21.3
  y = -4.4
  z = 0.3

  x.abs  # => 21.3
  y.abs  # => 4.4
  z.abs  # => 0.3
  ```

* **'`eql`', `==`, `===`**: Retorna verdadeiro se o valor for igual ao outro.

  ``` rb
  x = 1.2
  y = 5.2
  z = 3.3

  # Com `eql?`
  x.eql? 1.2   # => true
  y.eql? 5.22  # => false
  z.eql? 3     # => false

  # Com `==`
  x == 1.2     # => true
  y == 5.22    # => false
  z == 3       # => false

  # Com `===`
  x === 1.2    # => true
  y === 5.22   # => false
  z === 3      # => false
  ```

  > **OBS.:** Comparação entre valores de ponto flutuantes não é confiável, podendo ser imprecisa.

* **'`ceil`'**: Arredonda para cima.

  ``` rb
  x = 5.2
  y = 7.5
  z = 9.7

  x.ceil  # => 6
  y.ceil  # => 8
  z.ceil  # => 10
  ```

* **'`floor`'**: Arredonda o número para baixo.

  ``` rb
  x = 5.2
  y = 7.5
  z = 9.7

  x.floor  # => 5
  y.floor  # => 7
  z.floor  # => 9
  ```

* **'`round`'**: Arredonda para o número inteiro mais próximo.

  ``` rb
  x = 5.2
  y = 7.5
  z = 9.7

  x.round  # => 5
  y.round  # => 8
  z.round  # => 10
  ```

* **'`truncate`'**: Trunca o número pelo valor fornecido.

  ``` rb
  x = 21.52135
  y = 9.213215123
  z = 357.9902133

  x.truncate 2  # => 21.52
  y.truncate 3  # => 9.213
  z.truncate 4  # => 357.9902
  ```

* **'`coerce`'**: Retorna um array que contém um dado valor convertido para Float e o número em que este método foi aplicado.

  ``` rb
  x = 7.1
  y = 9.23
  z = 4.56

  x.coerce 2                 # => [2.0, 7.1]
  y.coerce '21.3'            # => [21.3, 9.23]
  z.coerce Float::INFINITY   # => [Infinity, 4.56]
  ```

* **'`fdiv`'**: Divide o número por um dado valor.

  ``` rb
  x = 7.5
  y = 21.3
  z = 45.5

  x.fdiv 2    # => 3.75
  y.fdiv 3    # => 7.1000000000000005
  z.fdiv 22   # => 2.0681818181818183
  ```

* **'`divmod`'**: Retorna um array que contém o resultado da divisão e resto da divisão entre o número em que este método foi aplicado e um dado valor.

  ``` rb
  x = 7.5
  y = 77.0
  z = 21.5

  x.divmod 2    # => [3, 1.5]
  y.divmod 11   # => [7, 0.0]
  z.divmod 3    # => [7. 0.5]
  ```

* **'`quo`'**: Retorna o quociente da divisão do número em que este método foi aplicado pelo valor fornecido.

  ``` rb
  x = 5.0
  y = 6.3
  z = 25.5

  x.quo 2   # => 2.5
  y.quo 3   # => 2.1
  z.quo 5   # => 5.1
  ```

  Se aplicado em um inteiro, será retornado um número racional.

  ``` rb
  x = 5
  y = 6
  z = 25

  x.quo 2   # => 5/2
  y.quo 3   # => 2/1
  z.quo 5   # => 5/1
  ```

* **'`next_float`'**: Retorna o próximo Float representável.

  ``` rb
  x = 30.1
  y = 23.92
  z = 12.003

  x.next_float # => 30.100000000000005
  y.next_float # => 23.920000000000005
  z.next_float # => 12.003000000000002
  ```

* **'`prev_float`'**: Retorna o Float representável anterior.

  ``` rb
  x = 30.1
  y = 23.92
  z = 12.003

  x.prev_float # => 30.099999999999998
  y.prev_float # => 23.919999999999998
  z.prev_float # => 12.002999999999998
  ```

* **'`rationalize`'**: Retorna `self` como um número racional.

  ``` rb
  f1 = 3.14
  f2 = 5.0
  f3 = 5.231

  f1.rationalize # => (157/50)
  f2.rationalize # => (5/1)
  f3.rationalize # => (5231/1000)
  ```

#### Constantes de Float

* **'`DIG`'**: O número mínimo de dígitos decimais significativos em um ponto flutuante de precisão dupla.

  ``` rb
  Float::DIG  # => 15
  ```

* **'EPSILON`'**: A diferença entre 1 e o maior ponto flutuante de precisão dupla maior que 1.

  ``` rb
  Float::EPSILON  # => 2.220446049250313e-16
  ```

* **'`INFINITY`'**: Representa um positivo ou negativo infinito

  ``` rb
  # Positivo infinito
  Float::INFINITY # => Infinity

  # Negativo Infinito
  -Float::INFINITY  # => -Infinity
  ```

* **'`MANT_DIG`'**: O número de dígitos base para o tipo de dados duplo.

  ``` rb
  Float::MANT_DIG # => 53
  ```

* **'`MAX`'**: O maior número inteiro possível em dupla precisão.

  ``` rb
  Float::MAX  # => 1.7976931348623157e+308
  ```

* **'`MAX_EXP`'**: O maior valor de expoente possível em um ponto flutuante de precisão dupla.

  ``` rb
  Float::MAX_EXP  # => 1024
  ```

* **'`MAX_10_EXP`'**: O maior valor de expoente positivo em um ponto flutuante de precisão dupla, onde 10 elevado a esta potência menos 1.

  ``` rb
  Float::MAX_10_EXP # => 308
  ```

* **'`MIN`'**: O menor número inteiro possível em dupla precisão.

  ``` rb
  Float::MIN  # => 2.2250738585072014e-308
  ```

* **'`MIN_EXP`'**: O menor valor de expoente possível em um ponto flutuante de precisão dupla.

  ``` rb
  Float::MIN_EXP  # => -1021
  ```

* **'`MIN_10_EXP`'**: O menor valor de expoente positivo em um ponto flutuante de precisão dupla, onde 10 elevado a esta potência menos 1.

  ``` rb
  Float::MIN_10_EXP # => -307
  ```

* **'`NAN`'**: Representa um valor "Not-a-Number".

  ``` rb
  Float::NAN  # => NaN
  ```

* **'`RADIX`'**: A base do ponto flutuante ou número de dígitos exclusivos usados ​​para representar o número.

  ``` rb
  Float::RADIX  # => 2
  ```

### Tipo `Symbol`

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

#### Métodos para Símbolos

* **'`capitalize`'**: Torna a primeira letra maiúscula e o resto minúsculas.

  ``` rb
  sym = :ruby
  sym.capitalize # => :Ruby
  ```

* **'`downcase`'**: Todos os caracteres do símbolo são convertidos para minúsculo.

  ``` rb
  sym = :RUBY
  sym.downcase  # => :ruby
  ```

* **'`upcase`'**: Todos os caracteres do símbolo são convertidos para maiúsculo.

  ``` rb
  sym = :ruby
  sym.upcase  # => :RUBY
  ```

* **'`name`'**: Retorna uma string congelada que corresponde ao símbolo.

  ``` rb
  sym = :ruby
  sym.name  # => "ruby"
  ```

* **'`succ`', '`next`'**: Retorna o símbolo sucessor do símbolo.

  ``` rb
  sym = :ruby

  # Com `succ`
  sym.succ # => :rubz

  # Com `next`
  sym.next # => :rubz
  ```

* **'`swapcase`'**: Retorna o símbolo com as letras maiúsculas em minúsculas e vice-versa.

  ``` rb
  sym = :rUbY
  sym.swapcase  # => :RuBy
  ```

* **'`slice`', '`[]`'**: Retorna uma substring a partir de um fatiamento.

  ``` rb
  sym = :olamundo

  # Com `slice`
  sym.slice 0, 3  # => "ola"

  # Com `[]`
  sym[0, 3]       # => "ola"
  ```

* **'`length`', '`size`'**: Retorna o número de caracteres do símbolo.

  ``` rb
  sym = :ruby

  # Com `length`
  sym.length  # => 4

  # Com `size`
  sym.size    # => 4
  ```

* **'`start_with?`'**: Retorna verdadeiro se o símbolo se inicia com a string fornecida.

  ``` rb
  sym = :ruby

  sym.start_with? 'ru'  # => true
  sym.start_with? 'py'  # => false
  ```

* **'`end_with`'**: Retorna verdadeiro se o símbolo termina com a string fornecida.

  ``` rb
  sym = :ruby

  sym.end_with? 'by'  # => true
  sym.end_with? 'on'  # => false
  ```

### Tipos Booleanos

Não há uma classe para representar valores booleanos, porém há classes para representar os valores `true` (`TrueClass`) e `false`(`FalseClass`).

Os valores **`true`** e **`false`** são valores lógicos utilizados em expressões booleanas.

**Exemplo com `true`:**

``` rb
var = true

if var
  puts 'Olá, Mundo!'
else
  puts 'Olá, Ruby!'
end

# Output: "Olá, Mundo!"
```

**Exemplo com `false`:**

``` rb
var = false

if var
  puts 'Olá, Mundo!'
else
  puts 'Olá, Ruby!'
end

# Output: "Olá, Ruby!"
```

### Tipo `nil`

Representa a ausência de um valor ou nulo, e quando utilizado em condições equivale a `false`.

**Exemplo:**

``` rb
var = nil

if var
  puts 'Olá, Mundo!'
else
  puts 'Olá, Ruby!'
end

# Output: "Olá, Ruby!"
```

#### Método `nil?`

Este método retorna verdadeiro se o objeto em o foi aplicada for `nil`.

**Exemplo:**

``` rb
var = nil

if var.nil?
  puts 'Olá, Mundo!'
else
  puts 'Olá, Ruby!'
end

# Output: "Olá, Mundo!"
```

### `Rational`

Representa números racionais. Um número racional é um número que pode ser expresso como uma fração de dois números, onde o denominador é diferente de zero.

A classe `Rational` não utiliza `new` para criar instâncias, funcionando ela mesma como uma função geradora de racionais.

**Para criar um racional:**

``` rb
# Com classe `Rational`
Rational numerador, denominador

# Declaração literal
numerador/denominadorr
```

**Exemplo:**

``` rb
# Com classe `Rational`
Rational 1, 2 # => (1/2)
Rational 5    # => (5/1)
Rational 0, 1 # => (0/1)

# Declaração literal
1/2r # => (1/2)
5r   # => (5/1)
0/1r # => (0/1)
```

**Pode ser usado o método **`rationalize`** em números para convertê-los para racional.**

``` rb
x = 3.14
y = 5
z = 5.231

x.rationalize # => (157/50)
y.rationalize # => (5/1)
z.rationalize # => (5231/1000)
```

**Operações matemáticas com racionais:**

``` rb
r1 = Rational 5 / 1
r2 = Rational 4 / 2

r1 + r2  # => (7/1)
r1 - r2  # => (3/1)
r1 * r2  # => (10/1)
r1 / r2  # => (5/2)
r1 % r2  # => (1/1)
r1 ** r2 # => (25/1)
```

#### Métodos para Racionais

* **'`abs`'**: Retorna o valor absoluto de `self`.

  ``` rb
  (1/2r).abs   # => (1/2)
  (-1/2r).abs  # => (1/2)
  ```

* **'`numerator`'**: Retorna o numerador de `self`.

  ``` rb
  (5/2r).numerator # => 5
  (2/3r).numerator # => 2
  (7/5r).numerator # => 7
  ```

* **'`denominator`'**: Retorna o denominador de `self`.

  ``` rb
  (5/2r).denominator # => 2
  (2/3r).denominator # => 3
  (7/5r).denominator # => 5
  ```

* **'`ceil`'**: Retorna o maior inteiro mais próximo de `self`.

  ``` rb
  (3/4r).ceil # => 1
  (5/2r).ceil # => 3
  (1/3r).ceil # => 1
  ```

* **'`floor`'**: Retorna o menor inteiro mais próximo de `self`.

  ``` rb
  (3/4r).floor # => 0
  (5/2r).floor # => 2
  (1/3r).floor # => 0
  ```

* **'`round`'**: Retorna o inteiro mais próximo de `self`.

  ``` rb
  (3/4r).round # => 1
  (5/2r).round # => 3
  (1/3r).round # => 0
  ```

* **'`truncate`'**: Trunca `self` por um dado valor e retorna o resultado.

  ``` rb
  (1/2r).truncate 1 # => (1/2)
  (2/3r).truncate 2 # => (33/50)
  (3/5r).truncate 3 # => (3/5)
  ```

* **'`positive?`'**: Retorna `true` se `self` for positivo, ou `false` caso contrário.

  ``` rb
  (2/5r).positive?  # => true
  (-1/7r).positive? # => false
  (3/6r).positive?  # => true
  ```

* **'`negative?`'**: Retorna `true` se `self` for negativo, ou `false` caso contrário.

  ``` rb
  (-3/5r).negative?  # => true
  (-4/2r).negative?  # => true
  (3/9r).negative?   # => false
  ```

* **'`quo`'**: Retorna o resultado da divisão entre `self` e um dado valor. O resultado será um número racional.

  ``` rb
  (10/5r).quo 1  # => (2/1)
  (4/3r).quo 2   # => (2/3)
  (-3/9r).quo 3  # => (-1/9)
  ```

* **'`fdiv`'**: Retorna o resultado da divisão entre `self` e um dado valor. O resultado será um número de ponto flutuante.

  ``` rb
  (10/5r).fdiv 1  # => 2.0
  (4/3r).fdiv 2   # => 0.6666666666666666
  (-3/9r).fdiv 3  # => -0.1111111111111111
  ```

### Conversão de Tipos

Primeiramente, devemos saber como verificar o tipo de um objeto específico. Para isso, existe o método **`class`**.

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

* **'`to_i`'**, **`.to_int`**: Converte para `Integer`.
* **'`to_f`'**: Converte para `Float`.
* **'`to_s`'**: Converte para `String`.
* **'`to_sym`'**, **`.intern`**: Converte para `Symbol`.
* **'`to_c`'**: Converte para `Complex`.
* **'`to_enum`'**: Converte para `Enumerator`.
* **'`to_a`'**: Converte para `Array`.
* **'`to_h`'**: Converte para `Hash`
* **'`to_r`'**: Converte para `Rational`.

## Atribuição de Método à Variável

Em Ruby, é possível atribuir o valor de retorno de um método ao objeto em que o método está sendo aplicado. Para isso, é utilizado **`!`** ao fim do nome do método.

``` rb
str = 'Olá, Mundo!'
str.upcase!
puts str # Output: OLÁ, MUNDO!
```

> OBS.: Dessa forma o objeto original é substituído.

## Módulo `Math`

`Math` é um módulo que fornece métodos básicos para trigonometria, extração de raízes e outros.

### Constantes de `Math`

* **'`PI`'**: Valor de pi.

  ``` rb
  Math::PI # => 3.141592653589793
  ```

* **'`E`'**: Número de Euler.

  ``` rb
  Math::E # => 2.718281828459045
  ```

### Métodos de `Math`

* **'`sin`'**: Retorna o seno de um dado valor em radianos.

  ``` rb
  angulo_em_radianos = 30 * Math::PI / 180
  Math.sin angulo_em_radianos
  # => 0.49999999999999994
  ```

* **'`cos`'**: Retorna o cosseno de um dado valor em radianos.

  ``` rb
  angulo_em_radianos = 30 * Math::PI / 180
  Math.cos angulo_em_radianos
  # => 0.8660254037844387
  ```

* **'`tan`'**: Retorna a tangente de um dado valor em radianos.

  ``` rb
  angulo_em_radianos = 30 * Math::PI / 180
  Math.tan angulo_em_radianos
  # => 0.5773502691896257
  ```

* **'`sqrt`'**: Retorna a raíz quadrada de um dado valor.

  ``` rb
  Math.sqrt 4    # => 2.0
  Math.sqrt 25   # => 5.0
  Math.sqrt 100  # => 10.0
  ```

* **'`cbrt`'**: Retorna a raíz cúbica de um dado valor.

  ``` rb
  puts Math.sqrt 4    # => 2.0
  puts Math.sqrt 25   # => 5.0
  puts Math.sqrt 100  # => 10.0
  ```

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
if condicao1
  # Bloco a ser executado caso a condição seja verdadeira
elsif condicao2
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

### Declaração `case`

Permite executar um bloco específico de acordo com o valor de uma variável ou expressão. Estruturas `case` são compostas de **`when`**, que definem o bloco que será executado de acordo com um valor, e um `else` no fim, que executa quando nenhum `when` corresponde ao valor da variável/expressão. O bloco `else` é opcional.

**Sintaxe:**

``` rb
case expressao
when valor1
  # Bloco que executa se `expressao` for igual a `valor1`
when valor1
  # Bloco que executa se `expressao` for igual a `valor2`
...
when valor10
  # Bloco que executa se `expressao` for igual a `valor10`
else
  # Bloco que executa quando nenhum `when` executar
end
```

**Exemplo:**

``` rb
print 'Escolha uma opção entre 1 e 3: '
escolha = Integer(gets.chomp)

case escolha
when 1
  puts 'Você escolheu 1!'
when 2
  puts 'Você escolheu 2!'
when 3
  puts 'Você escolheu 3!'
else
  puts 'Escolha inválida!'
end
```

#### Palavra-chave `then`

Permite escrever uma declaração `when` em apenas uma linha.

**Exemplo:**

``` rb
case valor
when 1 then puts 'Número 1'
when 2 then puts 'Número 2'
when 3 then puts 'Número 3'
else puts 'Valor diferente de 1, 2 e 3'
end
```

## Operadores

Em Ruby, os principais operadores são:

* Operadores Aritméticos
* Operadores de Comparação
* Operadores Lógicos
* Operador Ternário
* Operadores de Atribuição
* Operadores de Concatenação
* Operadores Bitwise

### Operadores Aritméticos

* **'`+`'**: Operador de adição.
* **'`-`'**: Operador de subtração.
* **'`*`'**: Operador de multiplicação.
* **'`/`'**: Operador de divisão.
* **'`%`'**: Operador de divisão inteira.
* **'`**`'**: Operador de potencia.

#### Precedência Aritmética

A ordem de precedência dos operadores aritméticos é feita na seguinte ordem:

1. `()`
1. `**`
1. `+`, `-`
1. `*`, `/`
1. `%`

### Operadores de Comparação

* **`>`**: Maior.
* **`<`**: Menor.
* **`==`**: Igual.
* **`>=`**: Maior ou igual.
* **`<=`**: Menor ou igual.

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

### Operadores de Atribuição

São usados para atribuir um valor a uma variável.

* **'`=`'**: Atribui um valor a uma variável.

  ``` rb
  x = 10
  ```

* **'`+=`'**: Soma à variável.

  ``` rb
  x = 10
  x += 5 # Mesmo que `x = x + 5`
  # => 15
  ```

* **'`-=`'**: Subtrai à variável.

  ``` rb
  x = 10
  x -= 5 # Mesmo que `x = x - 5`
  # => 5
  ```

* **'`*=`'**: Multiplica à variável.

  ``` rb
  x = 10
  x *= 5 # Mesmo que `x = x * 5`
  # => 50
  ```

* **'`/=`'**: Divide à variável.

  ``` rb
  x = 10
  x /= 5 # Mesmo que `x = x / 5`
  # => 2
  ```

* **'`%=`'**: Atribui à variável o valor do resto da divisão dela por um outro valor.

  ``` rb
  x = 10
  x %= 5 # Mesmo que `x = x % 5`
  # => 0
  ```

* **'`**=`'**: Eleva o valor da variável a um outro valor.

  ``` rb
  x = 10
  x **= 5 # Mesmo que `x = x ** 5`
  # => 100000
  ```

* **'`&=`'**: Realiza a operação bit a bit AND e atribui o resultado à variável da esquerda.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x & y # 1
  ```

* **'`|=`'**: Realiza a operação bit a bit OR e atribui o resultado à variável da esquerda.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x |= y # => 7
  ```

* **'`^=`'**: Realiza a operação bit a bit XOR e atribui o resultado à variável da esquerda.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x ^= y # => 6
  ```

* **'`<<=`'**: Realiza uma operação de deslocamento à esquerda e atribui o resultado à variável.

  ``` rb
  x = 5 # 0101 em binário
  puts x <<= 2 # => 10100
  ```

* **'`>>=`'**: Realiza uma operação de deslocamento à direita e atribui o resultado à variável.

  ``` rb
  x = 5 # 0101 em binário
  x >>= 2 # => 0001
  ```

* **'`||=`'**: Faz a atribuição apenas se o valor for nulo ou falso.

  ``` rb
  valor = nil
  valor ||= 5 # => 5
  ```

* **'`&&=`'**: Faz a atribuição apenas se o valor não for nulo ou falso.

  ``` rb
  valor = 2
  valor &&= 5 # => 5
  ```

### Operadores de Concatenação

Há dois operadores de concatenação, um geralmente usado para strings e outro para arrays.

* **'`+`'**: Quando ambos os operandos são strings, é feita a concatenação ao invés da soma.

  ``` rb
  str1 = 'Olá, '
  str2 = 'Mundo!'
  resultado = str1 + str2
  # => Olá, Mundo!
  ```

  O mesmo também pode ser usado para concatenar arrays.

  ``` rb
  [1, 2, 3] + [4, 5, 6] # => [1, 2, 3, 4, 5, 6]
  [1, 2, 3] + []        # => [1, 2, 3]
  ```

* **'`<<`'**: Concatena duas strings. Se algum dos operandos for um número inteiro, será tratado como uma concatenação normal, não havendo conversão automática para caracteres ASCII.

  ``` rb
  str1 = 'Olá, '
  str2 = 'Mundo!'
  resultado = str1 << str2
  # => Olá, Mundo!
  ```

  O mesmo também pode ser usado para adicionar um elemento ao fim de um array:

  ``` rb
  my_array = [1, 2, 3]  # => [1, 2, 3]
  my_array << 4         # => [1, 2, 3, 4]
  ```

  No caso de arrays, este operador funciona da mesma maneira que o método `push`.

### Operadores Bitwise

São utilizados para realizar operações a nível de bits em números inteiros. Os operadores bitwise atuam em cada bit individual de dois números e executam operações como deslocamento, AND, OR, XOR, entre outros.

**Os principais operadores bitwise são:**

* **'`&`' (AND)**: Retorna 1 para cada posição de bit em que ambos os operadores têm o bit 1.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x & y # 0001 (1 em decimal)
  ```

* **'`|`' (OR)**: Retorna 1 para cada posição de bit em que pelo menos um dos operandos tem o bit 1.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x | y # 0111 (7 em decimal)
  ```

* **'`^`' (XOR)**: Retorna 1 para cada posição de bit em que apenas um dos operandos tem um bit 1.

  ``` rb
  x = 5 # 0101 em binário
  y = 3 # 0011 em binário

  x ^ y # 0110 (6 em decimal)
  ```

* **'`~`' (NOT)**: Inverte cada bit de um número.

  ``` rb
  x = 5 # 0101 em binário
  ~x # 1010 (-6 em decimal) ou -110
  ```

* **'`<<`' (Deslocamento à Esquerda)**: Move os bits dos números para a esquerda.

  ``` rb
  x = 5 # 0101 em binário
  x << 2 # 10100 (20 em decimal)
  ```

* **'`>>`' (Deslocamento à Direita)**: Move os bits dos números para a direta.

  ``` rb
  x = 5 # 0101 em binário
  x >> 2 # 0001 (1 em decimal)
  ```

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

**Este array:**

``` rb
my_array = ['Ruby', 'JavaScript', 'Python', 'PHP', 'Go']
```

**Pode ser declarado assim:**

``` rb
my_array = %w[Ruby JavaScript Python PHP Go]
```

Ambos os exemplos acima correspondem ao mesmo array.

### Métodos de Array

#### Adicionar/Remover Elementos Array

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

#### Captura de Elementos Array

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

#### Pesquisa de Elementos Array

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

#### Organização de Elementos Array

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

## Ranges

Um range representa uma coleção de valores entre dois valores específicos.

São representados com **`..`** (range inclusivo) e **`...`** (range exclusivo).

* **Range inclusivo**: Inclui o último valor.
* **Range exclusivo**: Exclui o último valor.

**Exemplo:**

``` rb
# Range inclusivo
(1..5).to_a   # => [1, 2, 3, 4, 5]

# Range exclusivo
(1...5).to_a  # => [1, 2, 3, 4]
```

Além de números, podem ser criados ranges com letras.

**Exemplo:**

``` rb
# Range inclusivo
('a'..'f').to_a   # => ["a", "b", "c", "d", "e", "f"]

# Range exclusivo
('a'...'f').to_a  # => ["a", "b", "c", "d", "e"]
```

### Ranges sem Início ou Fim

São ranges em que o valor de início ou fim são iguais a `nil`.

#### Ranges sem Início

É possível declarar ranges sem um valor de início. Quando não especificado, o valor de início é `nil`.

**Declaração:**

``` rb
my_range = (nil..5)
# Ou
my_range = (..5)
```

Ranges sem início são compostos de todos os valores até o valor final. São geralmente usados para fatiar arrays.

**Exemplo:**

``` rb
# Array que será fatiado
my_array = [1, 2, 3, 4, 5]

# Range
r = (...3)

# Fatia o array
my_array[r] # => [1, 2, 3]
```

> **OBS.:** É lançada uma exceção se aplicado o método `each`.

#### Ranges sem Fim

São ranges que possuem o valor final igual a `nil`.

**Exemplo:**

``` rb
my_range = (1..)
# Ou
my_range = (1..nil)
```

Ranges sem fim são ranges infinitos que iniciam a partir de um valor específico. É geralmente usado para capturar um intervalo de números até um certo limite.

**Exemplo:**

``` rb
my_array = []
(1..).each do |num|
  my_array << num

  # Para quando o array se tornar [1, 2, 3, 4, 5]
  break if num > 5
end

my_array # => [1, 2, 3, 4, 5]
```

### Métodos para Ranges

#### Métodos de Pesquisa em Ranges

* **'`begin`'**: Retorna o primeiro valor do range.

  ``` rb
  r = (1..5)
  r.begin # => 1
  ```

* **'`end`'**: Retorna o último valor do range.

  ``` rb
  r = (1..5)
  r.end # => 5
  ```

* **'`bsearch`'**: Realiza uma busca binária em um array ordenado ou range. A busca binária é um algoritmo eficiente para encontrar um valor específico em uma coleção ordenada, reduzindo pela metade o espaço de busca a cada iteração.

  ``` rb
  # Range inclusivo 1-10
  r = (1..10)

  # Busca por valores dentro do range
  r.bsearch { |x| x == 5 }   # => 5
  r.bsearch { |x| x == 11 }  # => nil
  ```

* **'`count`'**: Retorna o número de elementos dentro do range.

  ``` rb
  r = (1..10)
  r.count # => 10
  ```

* **'`first`'**: Retorna o primeiro elemento do range.

  ``` rb
  r = (1..10)
  r.first # => 1
  ```

* **'`last`'** Retorna o último elemento do range.

  ``` rb
  r = (1..10)
  r.last # => 10
  ```

* **'`exclude_end?`'**: Retorna verdadeiro se o range é exclusivo.

  ``` rb
  # Range inclusivo
  inclusive_range = (1..10)
  inclusive_range.exclude_end? # => false

  # Range exclusivo
  exclusive_range = (1...10)
  exclusive_range.exclude_end? # => true
  ```

* **'`max`'**: Retorna o elemento com maior valor do range.

  ``` rb
  # Range inclusivo
  inclusive_range = (1..10)
  inclusive_range.max # => 10

  # Range exclusivo
  exclusive_range = (1...10)
  exclusive_range.max # => 9
  ```

* **'`min`'**: Retorna o elemento com menor valor do range.

  ``` rb
  r = (1..10)
  r.min # => 1
  ```

* **'`minmax`'**: Retorna um array com os elementos de valor mínimo e máximo do range.

  ``` rb
  # Range inclusivo
  inclusive_range = (1..10)
  print inclusive_range.minmax # => [1, 10]

  # Range exclusivo
  exclusive_range = (1...10)
  print exclusive_range.minmax # => [1, 9]
  ```

* **'`size`'**: Retorna o tamanho do range.

  ``` rb
  # Range inclusivo
  inclusive_range = (1..10)
  inclusive_range.size # => 10

  # Range exclusivo
  exclusive_range = (1...10)
  exclusive_range.size # => 9
  ```

#### Métodos de Comparação Range em Ranges

* **'`cover?`', '`===`', '`include?`', '`member?`'**: Retorna verdadeiro se um dado está dentro do range.

  ``` rb
  # Range
  r = (1..10)

  # Com `cover?`
  r.cover? 5      # => true
  r.cover? 11     # => false

  # Com `===`
  r === 5         # => true
  r === 11        # => false

  # Com `include?`
  r.include? 5    # => true
  r.include? 11   # => false

  # Com `member?`
  r.member? 5     # => true
  r.member? 11    # => false
  ```

* **'`eql?`', '`==`'**: Retorna verdadeiro se um dado objeto é igual ao range.

  ``` rb
  # Range
  r = (1..10)

  # Com `eql?`
  r.eql? 1..10    # => true
  r.eql? 5..10    # => false

  # Ou com `==`
  r == (1..10)      # => true
  r == (5..10)      # => false
  ```

#### Métodos para Iteração em Ranges

* **'`each`'**: Chama um bloco para cada elemento dentro do range.

  ``` rb
  # Range
  r = (1..10)

  # Array para armazenar os valores pares
  even_values = []

  # Itera sobre o range e preenche o array
  r.each { |num| even_values << num if num.even? }

  print even_values # => [2, 4, 6, 8, 10]
  ```

* **'`step`'**: Itera sobre os valores do range com base em um intervalo específico. Se não passado um argumento, o mesmo será 1.

  ``` rb
  # Range
  r = (1..5)

  # Intervalo 1
  elements = []
  r.step { |num| elements << num }
  print elements # => [1, 2, 3, 4, 5]
  puts

  # Intervalo 2
  elements = []
  r.step(2) { |num| elements << num }
  print elements # => [1, 3, 5]
  ```

## Estruturas de Repetição e Iteradores

### `for`

Repete um bloco em uma quantidade específica de vezes, baseado em um intervalo ou coleção.

**Baseando-se em um range:**

``` rb
for num in 0...10
  puts num
end
# Imprime de 0 a 9
```

**Baseando-se em um array:**

``` rb
my_array = ['a', 'b', 'c', 'd', 'e']
for elemento in my_array
  puts elemento
end
# Imprimirá todos os elementos do array
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

Permitem iterar sobre valores específicos em um sequência, sendo `upto` para iterar de forma crescente e `downto` de forma decrescente.

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
# => {"nome"=>"João", "idade"=>18, "sexo"=>"masculino"}
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

**Exemplo:**

``` rb
array = ['1', '2', '3']

array.map!(&:to_i)
# => [1, 2, 3]

# O mesmo porém sem símbolos:

array.map! { |e| e.to_i }
# => [1, 2, 3]
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

Este método é executado sempre que uma nova instância de uma class for criada usando o método **`new`**. Geralmente, é onde são definidas as variáveis de instância. **O método `initialize` é opcional**.

Os parâmetros deste método devem ser recebidos assim que criada uma nova instância de uma classe.

**Exemplo:**

``` rb
class Pessoa
  def initialize(nome)
    puts "Olá, #{nome}!"
  end
end

Pessoa.new 'Mundo'
# Output: "Olá, Mundo!"
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

Um método se torna privado ao definir `private` uma linha antes de definir o método.

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
obj.metodo_privado
# Ocorrerá um erro
```

É possível passar todos os métodos que serão privados em qualquer lugar da classe, escrevendo-os com `private` em forma de símbolos.

**Exemplo:**

``` rb
# Classe
class MinhaClasse
  private :ola_mundo, :ola_ruby

  def ola_mundo
    puts 'Olá, Mundo!'
  end

  def ola_ruby
    puts 'Olá, Ruby!'
  end
end
```

No exemplo acima, os métodos `ola_mundo` e `ola_ruby` são privados e não podem ser acessados de fora da classe em que foram definidos.

#### *Protected Methods*

Métodos protegidos são como métodos privados, porém eles podem ser acessados normalmente por classes filhas.

**Exemplo:**

``` rb
# Classe pai
class ClassePai
  protected

  def ola_mundo
    'Olá, Mundo!'
  end
end

# Classe filha
class ClasseFilha < ClassePai
  def print_ola_mundo
    puts ola_mundo
  end
end

obj = ClasseFilha.new
obj.print_ola_mundo # Output: "Olá, Mundo!"
```

> **OBS.:** Atualmente, métodos privados podem ser acessados por subclasses como métodos protegidos, o que significa que não há diferença entre métodos privados e protegidos. É importante lembrar que isso vale apenas para versões recentes, e versões como 2.7.0 ou inferior não suportaria métodos privados em subclasses.

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

### Sobrecarga de Operadores

É alterar a funcionalidade de um operador existente dentro de uma classe, fazendo com que instâncias dessa classe permitam usar este operador no contexto definido.

**Exemplo:**

``` rb
# Classe
class MinhaClasse
  attr_accessor :valor

  def initialize(valor)
    @valor = valor
  end

  def +(other)
    MinhaClasse.new(@valor * other.valor)
  end
end

obj1 = MinhaClasse.new 5
obj2 = MinhaClasse.new 2

resultado = obj1 + obj2
puts resultado.valor # Output: 10
```

No exemplo acima, foi definido na classe `MinhaClasse` que o operador `+` fará a multiplicação ao invés da adição. No contexto em que foi aplicado acima, só funcionará sem ambos os operando são instâncias da mesma classe, já que na definição `def +(other)` é feita a multiplicação a partir de `other.valor` e não apenas de `other`.

## Métodos `instance_of?` e `is_a?`

Ambos retornam verdadeiro se `self` for uma instância de um objeto específico.

**Exemplo `instance_of?`:**

``` rb
class MeuObjeto; end

int = 23
str = 'Olá, Mundo!'
obj = MeuObjeto.new

int.instance_of? Integer    # => true
str.instance_of? String     # => true
obj.instance_of? MeuObjeto  # => true
```

**Exemplo `is_a?`:**

``` rb
class MeuObjeto; end

int = 23
str = 'Olá, Mundo!'
obj = MeuObjeto.new

puts int.is_a? Integer    # => true
puts str.is_a? String     # => true
puts obj.is_a? MeuObjeto  # => true
```

### `instance_of?` vs. `is_a?`

Há uma diferença entre eles: **`instance_of?`** retorna verdadeiro apenas se `self` for uma instância exata da classe, sem considerar heranças.

**Exemplo:**

``` rb
class ClassePai; end
class ClasseFilha < ClassePai; end

obj = ClasseFilha.new
obj.instance_of? ClasseFilha   # => true
obj.instance_of? ClassePai     # => false
```

Por outro lado, o método **`is_a?`** retorna verdadeiro mesmo se a classe passada for a classe pai da exata.

``` rb
class ClassePai; end
class ClasseFilha < ClassePai; end

obj = ClasseFilha.new
obj.is_a? ClasseFilha   # => true
obj.is_a? ClassePai     # => true
```

#### Método `kind_of?`

O método **`kind_of`** é um alias para `is_a?`.

**Exemplo:**

``` rb
class ClassePai; end
class ClasseFilha < ClassePai; end

obj = ClasseFilha.new
obj.kind_of? ClasseFilha   # => true
obj.kind_of? ClassePai     # => true
```

## Método `respond.to?`

Retorna verdadeiro se o método passado como argumento puder ser aplicado em `self`.

**Exemplo:**

``` rb
num = 22

num.respond_to? :next     # => true
num.respond_to? :length   # => false
```

O método deve ser escrito em forma de símbolo, ou seja, '`:next`' ao invés de '`.next`'.

## Módulos

É uma estrutura usada para agrupar métodos, classes e constantes. São semelhantes às classes, mas eles não podem ser instanciados.

São usados principalmente para encapsular funcionalidades e fornecer reutilização de código.

**Exemplo:**

``` rb
module MeuModulo
  # Método que soma dois valores
  def self.somar(num1, num2)
    num1 + num2
  end

  # Método que retorna a raiz quadrada de dois valores
  def self.raiz_quadrada(num)
    num ** 0.5
  end

  # Classe
  class Pessoa
    def initialize(nome)
      @nome = nome
    end

    # Imprime uma mensagem de saudacao
    def saudacao
      puts "Olá, #{@nome}!"
    end
  end
end

# Uso dos métodos
MeuModulo.somar 5, 2        # => 7
MeuModulo.raiz_quadrada 25  # => 5.0

# Uso da classe
obj = MeuModulo::Pessoa.new 'Mundo'
obj.saudacao  # => Output: "Olá, Mundo!"
```

### Inclusão de Módulo à Classe

É possível incluir módulos a uma classe para que essa classe possa utilizar as ferramentas desse módulo. Para isso, é utilizada a palavra-chave **`include`** seguida do nome do módulo.

A inclusão de módulos em classes sem criar uma relação de herança é chamado de ***mixin***.

**Sintaxe:**

``` rb
class Classe
  include NomeModulo
  # ...
end
```

**Exemplo:**

``` rb
module MeuModulo
  def self.ola_mundo
    puts 'Olá, Mundo!'
  end
end

class MinhaClasse
  # Inclui o módulo `MeuModulo`
  include MeuModulo

  # Imprime "Olá, Mundo!" assim que criada uma instância
  def initialize
    MeuModulo.ola_mundo
  end
end

MinhaClasse.new   # => Output: "Olá, Mundo!"
```

### Extensão de Objetos

O método **`extend`** permite extender classes ou uma instância de uma classe com os recursos de módulos.

**Extendendo uma Instância:**

``` rb
# Módulo que contém um método
module ModuloExemplo
  #  Método que imprime "Olá, Mundo!"
  def ola_mundo
    puts 'Olá, Mundo!'
  end
end

# Classe que não possui métodos
class ClasseExemplo; end

# Extendendo a instância da classe
obj = ClasseExemplo.new
obj.extend ModuloExemplo

obj.ola_mundo # Output: "Olá, Mundo!"
```

**Extendendo uma Classe:**

``` rb
# Módulo que contém um método
module ModuloExemplo
  #  Método que imprime "Olá, Mundo!"
  def ola_mundo
    puts 'Olá, Mundo!'
  end
end

# Classe que não possui métodos
class ClasseExemplo; end

# Extendendo a classe
ClasseExemplo.extend ModuloExemplo

ClasseExemplo.ola_mundo # Output: "Olá, Mundo!"
```

#### Extender Objetos Padrão

É possível extender classes já existentes, como `String` e `Integer` com novos métodos. Para isso, é necessário declarar essas funções com os métodos desejados.

**Exemplo:**

``` rb
# Adicionando um método à classe `String`
class String
  def sub_o
    self.gsub! 'o', '0'
    self.gsub 'O', '0'
  end
end

# Adicionando um método à classe `Integer`
class Integer
  def mais_10
    self + 10
  end
end

# Exemplos de uso
str = 'Olá, Mundo!'
num = 12

str.sub_o    # => "0lá, Mund0!"
num.mais_10  # => 22
```

## Carregamento de Recursos

### Palavra-chave `require`

A palavra-chave **`require`** é usada para importar bibliotecas, importar arquivos locais ou remotos, e importar gems.

**Sintaxe:**

``` rb
require 'arquivo/biblioteca'
```

Resumindo, a palavra-chave `require` permite usar no arquivo atual todo o conteúdo de outro arquivo.

#### Importar Bibliotecas

Para importar bibliotecas, deve ser especificado o nome da biblioteca entre aspas.

**Sintaxe:**

``` rb
require 'nome_biblioteca'
```

**Exemplo:**

``` rb
require 'net/http'
require 'open_uri'
require 'socket'
```

#### Importar Arquivos Locais

Para importar arquivos, é necessário especificar o diretório do arquivo entre aspas, e se o diretório for o mesmo do arquivo que importará, deve ser usado **`require_relative`**.

**Exemplo:**

``` rb
# Arquivo que contém o módulo
module ExemploModulo
  def self.ola_mundo
    puts 'Olá, Mundo!'
  end
end
```

``` rb
# Arquivo principal
require_relative 'modulo'

ExemploModulo.ola_mundo   # => Output: "Olá, Mundo!"
```

No exemplo acima, o módulo do arquivo `modulo.rb` é importado no arquivo principal, permitindo-o usar o módulo normalmente.

## Bases Numéricas

Para representar as principais bases numéricas em Ruby, é usado um prefixo específico para cada uma delas, com exceção da base 10 (decimal), que é a base padrão.

* **Decimal**: É a base padrão.

  ``` rb
  x = 23
  ```

* **Binário**: Números na base 2 são representados com o prefixo **`0b`**.

  ``` rb
  x = 0b10111 # 23 em decimal
  ```

* **Octal**: Números na base 8 são representados com o prefixo **`0o`**.

  ``` rb
  x = 0o27 # 23 em decimal
  ```

* **Hexadecimal**: Números na base 16 são representados com o prefixo **`0x`**.

  ``` rb
  x = 0x17 # 23 em decimal
  ```

### Conversão entre Bases

Para converter números entre as bases, é usado o método **`to_s`**, que converte um valor para uma string. Neste método, deve ser passado como argumento a base de conversão.

**Conversão para Decimal:**

``` rb
# 45 (decimal) em outras bases
bin = 0b101101
oct = 0o55
hex = 0x2D

# Conversão para decimal
bin.to_s 10 # => 45
oct.to_s 10 # => 45
hex.to_s 10 # => 45
```

Outra forma de converter outras bases para decimal, é utilizando o método **`to_i`**, e passando como argumento a base em que o número que será convertido está.

``` rb
# 45 (decimal) em outras bases
bin = '0b101101'
oct = '0o55'
hex = '0x2D'

# Conversão para decimal
bin.to_i 2  # => 45
oct.to_i 8  # => 45
hex.to_i 16 # => 45
```

**Conversão para Binário:**

``` rb
# 11001 (binário) em outras bases
dec = 25
oct = 0o31
hex = 0x19

# Conversão para binário
dec.to_s 2 # => 11001
oct.to_s 2 # => 11001
hex.to_s 2 # => 11001
```

**Conversão para Octal**:

``` rb
# 73 (octal) em outras bases
dec = 59
bin = 0b111011
hex = 0x3B

# Conversão para octal
dec.to_s 8 # => 73
bin.to_s 8 # => 73
hex.to_s 8 # => 73
```

**Conversão para Hexadecimal**:

``` rb
# 2C (hexadecimal) em outras bases
dec = 44
bin = 0b101100
oct = 0o54

# Conversão para hexadecimal
puts dec.to_s 16 # => 2C
puts bin.to_s 16 # => 2C
puts oct.to_s 16 # => 2C
```

## Arquivos

Arquivos são manipulados por meio de métodos da classe **`File`**, que em nenhuma situação precisa ser instanciada.

### Abrir Arquivos

O método **`open`** recebe dois argumentos:

1. Nome do arquivo.
1. Modo de abertura.

**Sintaxe:**

``` rb
arquivo = File.open 'nome_arquivo.formato', 'modo_abertura'
# ...
arquivo.close # Fecha o arquivo quando não for mais necessário
```

**Exemplo:**

``` rb
arquivo = File.open 'arquivo.txt', 'r'
# ...
arquivo.close # Fecha o arquivo quando não for mais necessário
```

Os modos de abertura são:

* **'`r`'**: Abre o arquivo para leitura.

* **'`w`'**: Abre o arquivo para escrita. Se o arquivo não existir, ele será criado. Se o arquivo existir, ele será sobrescrito.

* **'`a`'**: Abre o arquivo para adição. Se o arquivo não existir, ele será criado. Se o arquivo existir, ele será sobrescrito.

* **'`r+`'**: Abre o arquivo para leitura e escrita.

* **'`w+`'**: Abre o arquivo para leitura e escrita. Se o arquivo não existir, ele será criado. Se o arquivo existir, ele será sobrescrito.

* **'`a+`'**: Abre o arquivo para leitura e adição. Se o arquivo não existir, ele será criado. Se o arquivo existir, o novo conteúdo será anexado ao final do arquivo existente.

### Leitura Arquivos

Para ler arquivos, é necessário especificar o modo **`'r'`** ao abrí-los.

``` rb
arquivo = File.open 'arquivo.txt', 'r'
# ...
arquivo.close
```

Para ler o conteúdo de um arquivo, é usado o módulo **`read`**. É uma boa prática especificar a codificação ao abrir arquivos que podem conter caracteres especiais. Para isso, é necessário definir `'UTF-8'` para o parâmetro `enconding`.

**Exemplo:**

Arquivo de texto:

``` txt
Olá, Mundo!
```

Arquivo Ruby:

``` rb
# Abre o arquivo `arquivo.txt` em modo de leitura
File.open 'arquivo.txt', 'r', encoding: 'UTF-8' do |file|
  conteudo = file.read # Lê e armazena o conteúdo do arquivo
  puts conteudo # Imprime o conteúdo do arquivo
end
# Output: "Olá, Mundo!"
```

**Para ler cada linha do arquivo separadamente:**

Arquivo de texto:

``` txt
Olá, Mundo!
Olá, Ruby!
```

Arquivo Ruby:

``` rb
# Abre o arquivo `arquivo.txt` em modo de leitura
File.open 'arquivo.txt', 'r', encoding: 'UTF-8' do |file|
  cont = 0 # Contador de linhas
  file.each_line do |line| # Itera sobre cada linha do arquivo
    cont += 1
    puts "Linha #{cont}: #{line}"
  end
end
# Output:
# Linha 1: Olá, Mundo!
# Linha 2: Olá, Ruby!
```

### Arquivos em Variáveis e Blocos

Abrir arquivos em variáveis cria a necessidade de fechá-los quando os mesmos não forem mais necessários. Para fechar arquivo, use o método **`close`**.

``` rb
# Abre o arquivo `arquivo.txt` em modo de leitura
arquivo = File.open 'arquivo.txt', 'r', encoding: 'UTF-8'
conteudo = arquivo.read # Lê e armazena o conteúdo do arquivo
puts conteudo # Imprime o conteúdo do arquivo
arquivo.close # Fecha o arquivo
```

Abrir um arquivo em um bloco dispensa a necessidade de fechá-lo quando o arquivo não for mais necessário.

**Exemplo:**

``` rb
# Abre o arquivo `arquivo.txt` em modo de leitura
File.open 'arquivo.txt', 'r', encoding: 'UTF-8' do |file|
  conteudo = file.read # Lê e armazena o conteúdo do arquivo
  puts conteudo # Imprime o conteúdo do arquivo
end
```

Se feito dessa forma - sem criar uma variável para o arquivo - ele será fechado automaticamente assim que o bloco encerrar.

### Escrever em Arquivos

Para escrever em arquivos, é necessário que ele seja aberto em modo de escrita (`'w'`). Ao abrir um arquivo com modo de escrita, ele será sobrescrito, e se não existir, ele será criado.

**Exemplo:**

``` rb
arquivo = File.open 'arquivo.txt', 'w', encoding: 'UTF-8'
# ...
arquivo.close
```

Para escrever no arquivo aberto, você pode usar os métodos **`puts`**, **`write`**, **`print`**, e **`printf`**.

* **'`puts`'**: Cria uma quebra de linha ao fim da string.

  Arquivo Ruby:

  ``` rb
  # Abre/cria o arquivo `arquivo.txt` em modo escrita
  File.open 'arquivo.txt', 'w', encoding: 'UTF-8' do |file|
    file.puts 'Olá, Mundo!'
    file.puts 'Olá, Ruby!'
  end
  ```

  Arquivo de texto:

  ``` txt
  Olá, Mundo!
  Olá, Ruby!

  ```

* **'`write`', '`printf`'**: Escreve no arquivo sem quebrar de linha. Para quebrar de linha é necessário escrever `\n`.

  Arquivo Ruby:

  ``` rb
  # Abre/cria o arquivo `arquivo.txt` em modo escrita
  File.open 'arquivo.txt', 'w', encoding: 'UTF-8' do |file|
    file.write "Olá, Mundo!\n"
    file.print 'Olá, Ruby!'
  end
  ```

  Arquivo de texto:

  ``` txt
  Olá, Mundo!
  Olá, Ruby!
  ```

* **'`printf`'**: O mesmo que os métodos `write` e `print`, porém permite formatadores.

  Arquivo Ruby:

  ``` rb
  # Strings que serão escritas no arquivo
  str1 = 'Olá, Mundo!'
  str2 = 'Olá, Ruby!'

  # Abre/cria o arquivo `arquivo.txt` em modo escrita
  File.open 'arquivo.txt', 'w', encoding: 'UTF-8' do |file|
    file.printf "%s\n", str1
    file.printf '%s', str2
  end
  ```

  Arquivo de texto:

  ``` txt
  Olá, Mundo!
  Olá, Ruby!
  ```

### Anexar à Arquivos

Para adicionar textos a um arquivo já existente, é necessário que ele seja aberto no modo de adição **`'a'`**. Se o arquivo não existir, ele será criado.

**Exemplo:**

``` rb
arquivo = File.open 'arquivo.txt', 'a', encoding: 'UTF-8'
# ...
arquivo.close
```

Para adicionar ao arquivo aberto, você pode usar os métodos **`puts`**, **`write`**, **`print`**, e **`printf`**.

* **'`puts`'**: Cria uma quebra de linha ao fim da string.

  Arquivo de texto:

  ``` txt
  Texto exemplo
  ```

  Arquivo Ruby:

  ``` rb
  # Abre o arquivo `arquivo.txt` em modo de adição
  File.open 'arquivo.txt', 'a', encoding: 'UTF-8' do |file|
    file.puts "\nOlá, Mundo!"
    file.puts 'Olá, Ruby!'
  end
  ```

  Arquivo de texto após adição:

  ``` txt
  Texto exemplo
  Olá, Mundo!
  Olá, Ruby!

  ```

* **'`write`', '`printf`'**: Escreve no arquivo sem quebrar de linha. Para quebrar de linha é necessário escrever `\n`.

  Arquivo de texto:

  ``` txt
  Texto exemplo
  ```

  Arquivo Ruby:

  ``` rb
  # Abre/cria o arquivo `arquivo.txt` em modo escrita
  File.open 'arquivo.txt', 'w', encoding: 'UTF-8' do |file|
    file.write "Olá, Mundo!\n"
    file.print 'Olá, Ruby!'
  end
  ```

  Arquivo de texto após adição:

  ``` txt
  Texto exemplo
  Olá, Mundo!
  Olá, Ruby!
  ```

* **'`printf`'**: O mesmo que os métodos `write` e `print`, porém permite formatadores.

  Arquivo de texto:

  ``` txt
  Exemplo texto
  ```

  Arquivo Ruby:

  ``` rb
  File.open 'arquivo.txt', 'w', encoding: 'UTF-8' do |file|
    file.printf 'Texto exemplo'
  end

  # Strings que serão escritas no arquivo
  str1 = 'Olá, Mundo!'
  str2 = 'Olá, Ruby!'

  # Abre o arquivo `arquivo.txt` em modo de adição
  File.open 'arquivo.txt', 'a', encoding: 'UTF-8' do |file|
    file.printf "\n%s\n", str1
    file.printf '%s', str2
  end
  ```

  Arquivo de texto após adição:

  ``` txt
  Texto exemplo
  Olá, Mundo!
  Olá, Ruby!
  ```

### Leitura e Escrita nos Arquivos

#### Modo `r+`

Abrir um arquivo com o modo **`r+`** indica que o mesmo pode ser usado para leitura e escrita. Escrever no arquivo irá sobrescrevê-lo, e se o novo conteúdo for menor que o anterior poderá ficar resquíscios do conteúdo anterior.

> **OBS.:** Se o arquivo não existir, ocorrerá um erro ao tentar abrí-lo.

**Exemplo:**

``` rb
# Abre o arquivo `arquivo.txt` no modo de leitura e escrita
File.open 'arquivo.txt', 'r+', encoding: 'UTF-8' do |file|
  # Escreve no arquivo
  file.write 'Olá, Mundo!'

  # Lê o arquivo e armazena seu conteúdo
  file.rewind
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo

  # Sobrescreve o arquivo
  file.rewind
  file.write 'Olá, Ruby!'

  # Trunca o arquivo para a posição atual do cursor
  file.truncate(file.pos)

  # Lê o arquivo e armazena seu conteúdo
  file.rewind
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo
end

# Output:
# Olá, Mundo!
# Olá, Ruby!
```

Arquivo de texto após a adição:

``` txt
Olá, Mundo!
Olá, Ruby!
```

**Análise do Exemplo:**

1. O arquivo `arquivo.txt` é aberto para um bloco no modo de leitura e escrita.

1. É escrito no arquivo "Olá, Mundo!"

1. O ponteiro é redirecionado para o início do arquivo com `file.rewind`.

1. O conteúdo do arquivo, que atualmente é "Olá, Mundo!", é salvo dentro da variável `conteudo`.

1. É impresso com `puts` o conteúdo do arquivo ("Olá, Mundo!").

1. O ponteiro é novamente redirecionado para o início do arquivo com `file.rewind`.

1. O arquivo é sobrescrito para "Olá, Ruby!" com `file.write`.

1. Se o novo conteúdo escrito no arquivo for menor que o anterior, irá sobrar resquícios do conteúdo anterior, e por isso é usado o método `truncate` para truncar o arquivo para a posição atual do cursor(`file.pos`).

1. O ponteiro é mais uma vez redirecionado para o início do arquivo com `file.rewind`.

1. A variável conteúdo é atualizada para o conteúdo atual do arquivo, que é "Olá, Ruby!".

1. Por fim, é impresso o conteúdo do arquivo ("Olá, Ruby!").

#### Modo `w+`

O mesmo que `r+`, porém cria um novo arquivo quando o arquivo não existir.

**Exemplo:**

``` rb
# Abre o arquivo `arquivo.txt` no modo de leitura e escrita
File.open 'arquivo.txt', 'w+', encoding: 'UTF-8' do |file|
  # Escreve no arquivo
  file.write 'Olá, Mundo!'

  # Lê o arquivo e armazena seu conteúdo
  file.rewind
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo

  # Sobrescreve o arquivo
  file.rewind
  file.write 'Olá, Ruby!'

  # Trunca o arquivo para a posição atual do cursor
  file.truncate(file.pos)

  # Lê o arquivo e armazena seu conteúdo
  file.rewind
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo
end

# Output:
# Olá, Mundo!
# Olá, Ruby!
```

Arquivo de texto após a adição:

``` txt
Olá, Mundo!
Olá, Ruby!
```

#### Modo `a+`

Permite ler e anexar à arquivos, e se o arquivo não existir, será criado um novo. Novos conteúdos ao arquivo serão anexados sempre ao fim do arquivo.

**Exemplo:**

Arquivo de texto:

``` txt
Olá, Mundo!
```

Arquivo Ruby:

``` rb
# Abre o arquivo `arquivo.txt` no modo de leitura e anexação
File.open 'arquivo.txt', 'a+', encoding: 'UTF-8' do |file|
  # Lê o arquivo e armazena seu conteúdo
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo

  # Anexa ao arquivo
  file.write "\nOlá, Ruby!"

  # Lê o arquivo e armazena seu conteúdo
  file.rewind
  conteudo = file.read
  puts conteudo # Imprime o conteúdo do arquivo
end

# Output:
# Olá, Mundo!
# Olá, Mundo!
# Olá, Ruby!
```

Arquivo de texto após a adição:

``` txt
Olá, Mundo!
Olá, Ruby!
```

**Análise do Exemplo:**

1. Arquivo `arquivo.txt` possui "Olá, Mundo!" como conteúdo inicial.

1. É aberto o arquivo `arquivo.txt` no modo de leitura e anexação.

1. É armazenado o conteúdo do arquivo ("Olá, Mundo!") na variável `conteudo`.

1. É impresso o conteúdo do arquivo, que é apenas "Olá, Mundo!".

1. Ao final do arquivo, é adicionado o texto "Olá, Ruby!".

1. O ponteiro é redirecionado para o início do arquivo com `rewind` para que possa ser armazenado em `conteudo` e impresso, imprimindo assim o conteúdo anterior e o novo.

### Métodos de `File`

Existem vários métodos da classes `File`, todos usados para manipular arquivos.

* **'`basename`'**: Retorna o nome do arquivo que corresponde ao caminho fornecido.

  ``` rb
  File.basename 'caminho/do/arquivo.txt' # => "arquivo.txt"
  ```

* **'`dirname`'**: Retorna o diretório de um arquivo, com base no caminho do arquivo.

  ``` rb
  File.dirname 'caminho/do/arquivo.txt' # => "caminho/do"
  ```

* **'`extname`'**: Retorna a extensão do arquivo fornecido.

  ``` rb
  File.extname 'caminho/do/arquivo.txt' # => ".txt"
  ```

* **'`size`'**: Retorna o tamanho do arquivo fornecido em bytes.

  ``` rb
  File.size 'caminho/do/arquivo.txt' # => 0
  ```

  Foi retornado 0 porque o arquivo está vazio.

* **'`exist?`'**: Retorna verdadeiro se o arquivo existir, ou falso caso contrário.

  ``` rb
  File.exist? 'caminho/do/arquivo.txt'        # => true
  File.exist? 'outro_caminho/do/arquivo.txt'  # => false
  ```

* **'`rename`'**: Renomeia o arquivo fornecido.

  ``` rb
  File.rename 'caminho/do/arquivo.txt', 'caminho/do/novo_nome.txt' # => 0
  ```

* **'`delete`'**: Exclui o arquivo fornecido.

  ``` rb
  File.delete 'caminho/do/arquivo.txt' # => 1
  ```

* **'`read`'**: Retorna uma string com o conteúdo do arquivo.

  Arquivo de texto:

  ``` txt
  Olá, Mundo!
  Olá, Ruby!
  ```

  Arquivo Ruby:

  ``` rb
  content = File.read 'caminho/do/arquivo.txt', encoding: 'UTF-8'
  # => Olá Mundo!
  #    Olá, Ruby!
  ```

* **'`readlines`'**: Retorna um array, cujo cada elemento é uma linho do arquivo.

  ``` rb
  content = File.readlines 'caminho/do/arquivo.txt', encoding: 'UTF-8'
  # => ["Olá, Mundo!\n", "Olá, Ruby!"]
  ```

* **'`foreach`'**: Itera sobre cada linha do arquivo.

  Arquivo de texto:

  ``` txt
  Olá, Mundo!
  Olá, Ruby!
  ```

  Arquivo Ruby:

  ``` rb
  cont = 0
  File.foreach 'caminho/do/arquivo.txt', encoding: 'UTF-8' do |line|
    cont += 1
    puts "Linha #{cont}: #{line}"
  end
  # Output:
  # Linha 1: Olá, Mundo!
  # Linha 2: Olá, Ruby!
  ```

* **'`write`'**: Escreve no arquivo, substituindo seu conteúdo. Se o arquivo não existir, ele será criado.

  ``` rb
  File.write 'arquivoo.txt', 'Olá, Mundo!'
  ```

* **'`atime`'**: Retorna o tempo de acesso do arquivo.

  ``` rb
  File.atime 'arquivo.txt'
  ```

* **'`mtime`'**: Retorna o tempo de modificação do arquivo.

  ``` rb
  File.mtime 'arquivo.txt'
  ```

* **'`ctime`'**: Retorna o tempo de status do arquivo.

  ``` rb
  File.ctime 'arquivo.txt'
  ```

* **'`join`'**: Retorna um caminho com as strings fornecidas.

  ``` rb
  File.join 'caminho', 'do', 'arquivo.txt' # => "caminho/do/arquivo.txt"
  ```

### Boas Práticas de Manipulação de Arquivos

#### Nomear Variáveis de Arquivos

É uma boa prática nomear variáveis de arquivos com nomes descritivos.

**Exemplo:**

``` rb
arquivo_leitura = File.open 'arquivo.txt', 'r', encoding: 'UTF-8'
conteudo_leitura = arquivo_leitura.read
puts conteudo_leitura
arquivo_leitura.close
```

#### Fechamento de Arquivos

É essencial fechar os arquivos abertos quando eles não forem mais úteis. Isso é útil por vários motivos, entre eles:

* **Liberação de recursos**: Ao abrir um arquivo, o sistema operacional alocará recursos para manipular esse arquivo, como entrada/saída e buffers de memória. Se o arquivo não for fechado adequadamente, esses recursos podem não ser liberados, resultando em vazamento de recursos. Isso é acumulativo, o que leva a problemas de desempenho ou até mesmo esgotamento de recursos do sistema.

* **Consistência de Dados**: Gravar dados em um arquivo e não fechá-lo corretamente, os dados podem ser tornar inconsistentes, pois algumas alterações podem não ser refletidas no sistema de arquivos.

* **Prevenção contra Gravação Acidental**: Abrir um arquivo para leitura e acidentalmente tentar gravar nele poderá corromper o arquivo se ele não for fechado corretamente após a leitura.

**Para fechar arquivos abertos em variáveis:**

``` rb
arquivo = File.open 'arquivo.txt', 'r'
# ...
arquivo.close
```

**Para fechar arquivos abertos em blocos:**

Arquivos de blocos são fechados automaticamente ao fim do bloco, mesmo que ocorra uma exceção.

``` rb
File.open 'arquivo.txt', 'r' do |file|
  # ...
end
```

#### Verificar Existência do Arquivo

É importante verificar se o arquivo existe antes de trabalhar com ele. Isso evita erros inesperados e permite lidar com situações em que o arquivo não está presente no caminho especificado.

A existência de um arquivo pode ser verificada com o método **`File.exist?`**, que retorna `true` se o arquivo existir, ou `false` caso contrário.

**Exemplo:**

``` rb
# Caminho do arquivo
file_path = 'caminho/arquivo.txt'

if File.exist? file_path
  # Caso o arquivo exista
  File.open file_path, 'r', encoding: 'UTF-8' do |file|
    # ...
  end
else
  # Arquivo não existe
  puts 'O arquivo não existe'
end
```

#### Tratamento de Erros para Arquivos

É importante lidar com as possíveis exceções lançadas em certas situações. As exceções mais comuns ao trabalhar com arquivos são:

* **'`Errno::ENOENT`'**: Quando o arquivo ou diretório especificado não é encontrado.

  ``` rb
  begin
    File.open '/caminho/do/arquivo.txt', 'r' do |file|
      # ...
    end
  rescue Errno::ENOENT => e
    puts "Arquivo não encontrado: #{e.class}"
  end
  ```

* **'`Errno::EISDIR`'**: Quando é especificado um diretório como se fosse um arquivo.

  ``` rb
  begin
    File.open '/caminho/do/arquivo', 'r' do |file|
      # ...
    end
  rescue Errno::EISDIR => e
    puts "Não foi especificado um arquivo, e sim um diretório: #{e.class}"
  end
  ```

* **'`Errno::EACCES`'**: Quando não há permissão para acessar o arquivo.

  ``` rb
  begin
    File.open '/caminho/do/arquivo.txt', 'r' do |file|
      # ...
    end
  rescue Errno::EACCES => e
    puts "Não há permissão para acessar o arquivo: #{e.class}"
  end
  ```

* **'`IOError`'**: Exceção genérica que pode ocorrer durante operações de entrada e saída.

  ``` rb
  begin
    File.open '/caminho/do/arquivo.txt', 'r' do |file|
      # ...
    end
  rescue IOError => e
    puts "Erro na entrada/saída: #{e.class}"
  end
  ```

Essas são apenas algumas das várias exceções que podem ocorrer ao trabalhar com arquivos.

##### Função para Auxiliar nas Exceções em Arquivos

Para lidar com exceções, é uma boa práticar declarar uma função para promover reutilização e tornar o código mais limpo.

**Exemplo:**

``` rb
# Função genérica que lida com exceções em arquivos
def file_open(file_path, mode, &block)
  File.open file_path, mode, encoding: 'UTF-8', &block
rescue Errno, IOError => e
  puts "Erro ao manipular arquivo: #{e.class} - #{e.message}"
end

# Exemplo de uso
file_open 'arquivo.txt', 'r' do |file|
  content = file.read
  puts content
end
```

#### Especificar Codificação ao Abrir Arquivos

Para arquivos que podem conter caracteres especiais, é importante especificar o tipo de codificação adequada. Isso é feito passando o argumento **`'UTF-8'`** para o parâmetro **`encoding`**.

**Exemplo:**

``` rb
File.open 'arquivo.txt', 'r', encoding: 'UTF-8' do |file|
  # ...
end
```

#### Leitura de Arquivos Grandes

Ao abrir arquivos grandes para leitura, é uma boa prática ler o arquivo com o método **`each_line`**.

**Exemplo:**

``` rb
File.open 'arquivo.txt', 'r', encoding: 'UTF-8' do |file|
  file.each_line do |line|
    puts line
  end
end
```

O método `read` lê o arquivo inteiro de uma vez e retorna uma única string contendo todo o conteúdo. Se o arquivo for grande demais, isso pode consumir muita memória, podendo levar a problemas de desempenho e até mesmo falhar se o arquivo for muito grande para caber a memória disponível. Por outro lado, o método **`each_line`** lê o arquivo linha por linha, sendo mais eficiente em termos de consumo de memória, pois processa apenas uma linha por vês.

**Leitura Rápida:**

Se a necessidade for apenas ler o arquivo e fechá-lo, você pode usar o método **`File.foreach`** ao invés de `File.open`, fornecendo os mesmos argumentos.

``` rb
File.foreach 'arquivo.txt', 'r', encoding: 'UTF-8' do |line|
  puts line
end
```

## Data e Tempo

Há três classes para representar data e tempo:

* **`Date`**: Usada para representar datas específicas sem levar em consideração a hora do dia.

* **`Time`**: Usada para representar pontos específicos no tempo.

* **`DateTime`**: É a junção de **`Date`** e **`Time`**. Oferece funcionalidades para representar tanto a data quanto a hora com maior precisão que `Date`. É descontinuada, e por isso é recomendado o uso de `Time` ao invés de `DateTime`.

### Classe `Date`

Usada para representar datas de calendário. Normalmente, é necessário importar `Date` com `require`.

**Declarando uma data:**

``` rb
require 'date'

#        Ano/Mês/Dia
Date.new 2005, 2, 7
# => #<Date: 2005-02-07 ((2453409j,0s,0n),+0s,2299161j)>
```

#### Métodos de `Date`

* **'`today`'**: Retorna a data atual.

  ``` rb
  Date.today # Retorna a data de hoje
  ```

* **'`jd`'**: Retorna o dia referente a um valor Julian Day.

  ``` rb
  Date.jd 2453507
  # => #<Date: 2005-05-16 ((2453507j,0s,0n),+0s,2299161j)>
  ```

* **'`ordinal`'**: Retorna uma data a partir do ano e dia ordinal.

  ``` rb
  Date.ordinal 2005, 136
  # => #<Date: 2005-05-16 ((2453507j,0s,0n),+0s,2299161j)>
  ```

* **'`commercial`'**: Retorna uma data a partir de uma data comercial (ano, semana, dia da semana).

  ``` rb
  Date.commercial 2005, 20, 1
  # => #<Date: 2005-05-16 ((2453507j,0s,0n),+0s,2299161j)>
  ```

* **'`parse`'**: Retorna uma data a partir de uma dada string.

  ``` rb
  Date.parse '2005-05-16'
  # => #<Date: 2005-05-16 ((2453507j,0s,0n),+0s,2299161j)>
  ```

* **'`strptime`'**:Retorna uma data a partir de uma dada string e formato de string.

  ``` rb
  Date.strptime '2005-05-16', '%Y-%m-%d'
  # => #<Date: 2005-05-16 ((2453507j,0s,0n),+0s,2299161j)>
  ```

#### Constantes de `Date`

* **'`ABBR_DAYNAMES`'**: Array com as abreviações dos nomes dos dias em inglês.

  ``` rb
  Date::ABBR_DAYNAMES
  # => ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"]
  ```

* **'`ABBR_MONTHNAMES`'**: Array com as abreviações dos nomes dos dias em inglês.

  ``` rb
  Date::ABBR_MONTHNAMES
  # => [nil, "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
  ```

* **'`DAYNAMES`'**: Um array com os nomes completos dos dias em inglês.

  ``` rb
  Date::DAYNAMES
  # => ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]
  ```

* **'`MONTHNAMES`'**: Um array com os nomes completos dos meses em inglês.

  ``` rb
  Date::MONTHNAMES
  # => [nil, "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]
  ```

* **'`GREGORIAN`'**: O número do Julian Day da reforma do calendário para o calendário gregoriano proléptico.

  ``` rb
  Date::GREGORIAN
  # => -Infinity
  ```

* **'`JULIAN`'**: O número do Julian Day da reforma do calendário juliano proléptico.

  ``` rb
  Date::JULIAN
  # => Infinity
  ```

* **'`ITALY`'**: O número do Julian Day do dia da reforma do calendário para a Itália e alguns países católicos.

  ``` rb
  Date::ITALY
  # => 2299161
  ```

* **'`ENGLAND`'**: O número do Julian Day do dia da reforma do calendário para a Inglaterra e suas colônias.

  ``` rb
  Date::ENGLAND
  # => 2361222
  ```

### Classe `Time`

Usada para representar data e horário. É usado um objeto **`Time`** junto de **`new`**. `Time.new` recebe os seguintes argumentos:

1. Ano
1. Mês
1. Dia
1. Horas
1. Minutos
1. Segundos
1. Fuso horário

``` rb
#        Ano  Mês Dia Hor Min Sec
Time.new 2005, 5, 13, 12, 30, 35
# => 2005-05-13 12:30:35 -0300
```

Se todos os parâmetros forem omitidos, será gerada a **data e horário atual**:

``` rb
Time.new
# Retorna a data e o horário atual
```

Se não passado horas, minutos ou segundos eles serão `0`. Se não passado mês ou dia, eles serão `1`.

``` rb
Time.new 2000
# => 2000-01-01 00:00:00 -0300
```
