# Python

## Output de Valores

Para imprimir valores, é usada a função **`print()`**.

**Exemplo:**

``` py
print('Olá, Mundo!')
# Output => Olá, Mundo!
```

## Variáveis

Para declara uma variável, deve ser definido o nome dela, o operador de atribuição `=` e o valor da variável.

**Sintaxe:**

``` py
nome_variavel = valor_variavel
```

**Exemplo:**

``` py
minha_variavel = 'Olá, Mundo!'
```

## Tipos Primitivos

Os principais tipos são:

* **'`int`'**: Representa números inteiros.
* **'`float`'**: Representa número de ponto flutuante.
* **'`str`'**: Representa strings (cadeia de caracteres).
* **'`bool`'**: Representa valores booleanos (`True` e `False`).

É possível verificar o tipo de dado de uma variável com **`type()`**.

**Exemplo:**

``` py
print(type(23)) # Output => <class 'int'>
print(type('Olá, Mundo!')) # Output => <class 'str'>
print(type(5.2)) # Output => <class 'float'>
print(type(True)) # Output => <class 'bool'>
```

### Inteiros

A classe **`int`** representa números inteiros.

**Exemplo:**

``` py
num1 = 5 # => 5
num2 = 2 # => 2
```

### Números de Ponto Flutuante

A classe **`float`** representa números de ponto flutuante.

**Exemplo:**

``` py
num1 = 5.3
num2 = 21.6
```

### Strings

A classe **`str`** representa strings, que podem ser escritas dentro de aspas simples ou duplas.

**Exemplo:**

``` py
str1 = "Olá, Mundo!"
str2 = 'Olá, Python!'
```

#### Função `len()` para Strings

A função **`len()`** pode ser usada em strings. Ela retorna a quantidade de caracteres de uma dada string.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
countChars = len(str)
print(countChars) # Output => 11
```

#### Operador `in` para Strings

O operador **`in`** pode ser usado para verificar se uma dada string existe dentro de outra, e retorna `True` ou `False` dependendo dessa verificação.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
analise = 'Mundo' in str
print(analise) # Output => True
```

#### Fatiamentos em Strings

Fatiar uma string significa pegar uma parte específica dela a partir de um início e fim considerandos os índices.

**Sintaxe:**

``` py
novaStr = str[inicio:fim]
```

> **NOTA:** O `fim` é exclusivo.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
novaStr = str[5:8]
print(novaStr) # Output => Mun
```

Caso não definido o início, será considerado 0, e se não definido o fim, será considerado todo o resto da string.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
print(str[5:]) # Output => Mundo!
print(str[:3]) # Output => Olá
```

É possível saltar posições ao definir `inicio:fim:saltos`, onde o número final é a quantidade de saltos nos índices.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
print(str[5::2]) # Output => Mno
```

No exemplo acima, é considerado a string a partir do índice 5 até o fim, pulando os caracteres a cada 2 índices (inclusivo).

#### Interpolação

Pode ser feita de duas maneiras:

* Método `format()`
* *F Strings*

**Exemplo com `format()`:**

``` py
num1 = 5
num2 = 2
print("A soma entre {} e {} é {}".format(num1, num2, num1 + num2))
# Output => A soma entre 5 e 2 é 7
```

**Exemplo com *F string*:**

``` py
num1 = 5
num2 = 2
print(f"A soma entre {num1} e {num2} é {num1 + num2}")
# Output => A soma entre 5 e 2 é 7
```

##### Formatação na Interpolação

Para formatar uma string dentro de uma interpolação é utilizado `:`, seguido de:

1. Caractere para preencher espaços (se não definido, será apenas espaços em branco).
1. Indicador se a mensagem será no começo, fim ou no centro dos espaços (indicadores: `<`, `>`, `^`).
1. Números de espaços para se preencher.

**Exemplo com `format()`:**

``` py
str = 'Olá, Mundo!'
print("{:-^25}".format(str))
# Output => -------Olá, Mundo!-------
```

**Exemplo com *F String*:**

``` py
str = 'Olá, Mundo!'
print(f'{str:-^25}')
# Output => -------Olá, Mundo!-------
```

Em ambos os exemplos é impresso `"Olá, Mundo!"` entre os caracteres `"-"`, que preenchem o espaço até a string inteira ocupar 25 caracteres.

#### Métodos para Strings

* **'`upper()`'**: Retorna `self` com todos os caracteres em maiúsculo.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.upper()
    print(newStr) # Output => OLÁ, MUNDO!
    ```

* **'`lower()`'**: Retorna `self` com todos os caracteres em minúsculo.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.lower()
    print(newStr) # Output => olá, mundo!
    ```

* **'`capitalize()`'**: Retorna `self` com o primeiro caractere em maiúsculo e o resto em minúsculo.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.capitalize()
    print(newStr) # Output => Olá, mundo!
    ```

* **'`title()`'**: Retorna `self` com o primeiro caractere de todas as palavras em maiúsculo e o resto em minúsculo.

    ``` py
    str = 'oLá, mUndO!'
    newStr = str.title()
    print(newStr) # Output => Olá, Mundo!
    ```

* **'`count()`'**: Retorna a quantidade de ocorrência de uma dada substring em `self`.

    ``` py
    str = 'Olá, Mundo!!!'
    contador = str.count('!')
    print(contador) # Output => 3
    ```

* **'`find()`'**: Retorna o índice em que uma dada substring se inicia em `self`.

    ``` py
    str = 'Olá, Mundo!'
    indice = str.find('Mundo!')
    print(indice) # Output => 5
    ```

* **'`replace()`'**: Substitui uma substring de `self` por uma nova substring.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.replace('Mundo', 'Python')
    print(newStr) # Output => Olá, Python!
    ```

    É possível passar um terceiro argumento, e esse argumento define a quantidade de substituições que serão feitas.

    ``` py
    str = 'Olá, Mundo! Olá, Mundo!'
    newStr = str.replace('Mundo', 'Python', 1)
    print(newStr) # Output => Olá, Python! Olá, Mundo!
    ```

    O valor padrão para esse terceiro padrão é `-1`, que define que serão feitas todas as substituições.

* **'`strip()`'**: Retorna `self` sem espaços em branco no início e no fim.

    ``` py
    str = '     Olá, Mundo!     '
    newStr = str.strip()
    print(newStr) # Output => Olá, Mundo!
    ```

    Os métodos **`lstrip()`** e **`rstrip()`** removem apenas os espaços em branco na esquerda e direita, respectivamente.

* **'`split()`'**: Retorna uma lista a partir de `self` e um separador (se não especificado, será os espaços).

    ``` py
    str = 'Eu amo Python'
    lista = str.split()
    print(lista) # Output => ['Eu', 'amo', 'Python']
    ```

    Exemplo com um seperador definido:

    ``` py
    str = 'Eu-amo-Python'
    lista = str.split('-')
    print(lista) # Output => ['Eu', 'amo', 'Python']
    ```

    É possível passar um segundo argumento, que define o limite de elementos que a lista terá.

    ``` py
    str = 'Eu-amo-Python'
    lista = str.split('-', 1)
    print(lista) # Output => ['Eu', 'amo-Python']
    ```

    `-1` é o valor padrão, onde serão separadados todos os elementos possívels.

    > **NOTA.:** A quantidade é relativa aos índices, ou seja, `0` será 1, `1` será 2, e assim por diante.

## Operadores

Os principais operadores são:

* Operadores aritméticos
* Operadores de comparação
* Operadores lógicos
* Operadores bitwise
* Operadores de atribuição

### Operadores Aritméticos

* **'`+`'**: Adição.
* **'`-`'**: Subtração.
* **'`*`'**: Multiplicação.
* **'`/`'**: Divisão.
* **'`//`'**: Divisão inteira.
* **'`%`'**: Módulo (resto da divisão).
* **'`**`'**: Potência.

**Exemplo:**

``` py
# Operandos
x = 5
y = 2

# Imprime as operações
print(x + y)    # Output => 7
print(x - y)    # Output => 3
print(x * y)    # Output => 10
print(x / y)    # Output => 2.5
print(x // y)   # Output => 2
print(x % y)    # Output => 1
print(x ** y)   # Output => 25
```

### Operadores de Comparação

* **'`==`' (Igual)**: Verdadeiro se ambos os operandos forem iguais.

    ``` py
    print(1 == 1)       # Output => True
    print('Py' == "Py") # Output => True
    print('5' == 5)     # Output => False
    ```

* **'`!=`' (Diferente)**: Verdadeiro se os operandos forem diferentes um do outro.

    ``` py
    print(2 != 5)        # Output => True
    print(5.0 != 5)      # Output => False
    print('Oi' != 'Olá') # Output => True
    ```

* **'`<`' (Menor)**: Verdadeiro se o operando à esquerda for menor.

    ``` py
    print(1 < 5)        # Output => True
    print(7 < 6)        # Output => False
    print('Oi' < 'Olá') # Output => True
    ```

* **'`>`' (Maior)**: Verdadeiro se o operando da esquerda for maior.

    ``` py
    print(7 > 2)        # Output => True
    print(2 > 4)        # Output => False
    print('Oi' > 'Olá') # Output => False
    ```

* **'`<=`' (Menor ou igual)**: Verdadeiro se o operando à esquerda for menor ou igual ao da direita.

    ``` py
    print(0 <= 2) # Output => True
    print(5 <= 5) # Output => True
    print(2 <= 1) # Output => False
    ```

* **'`>=`' (Maior ou igual)**: Verdadeiro se o operando à esquerda for maior ou igual ao da direita.

    ``` py
    print(1 >= -1) # Output => True
    print(4 >= 4)  # Output => True
    print(2 >= 3)  # Output => False
    ```

### Operadores Lógicos

* **'`and`'**: Verdadeiro quando ambos os operandos forem verdadeiro.

    ``` py
    print(True and True)    # Output => True
    print(True and False)   # Output => False
    print(False and True)   # Output => False
    print(False and False)  # Output => False
    ```

* **'`or`'**: Verdadeiro se pelo menos um dos operandos for verdadeiro.

    ``` py
    print(True or True)    # Output => True
    print(True or False)   # Output => True
    print(False or True)   # Output => True
    print(False or False)  # Output => False
    ```

* **'`not`'**: Inverte o valor (verdadeiro se torna falso e falso se torna verdadeiro).

    ``` py
    print(not True)    # Output => False
    print(not False)   # Output => True
    ```

### Operadores Bitwise

* **'`&`' (AND)**: Retorna 1 para cada posição de bit em que ambos os operadores têm o bit 1.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x & y # 0001 (1 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # Output => Binário: 0b1 | Decimal: 1
    ```

* **'`|`' (OR)**: Retorna 1 para cada posição de bit em que pelo menos um dos operandos tem o bit 1.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x | y # 0111 (7 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # Output => Binário: 0b111 | Decimal: 7
    ```

* **'`^`' (XOR)**: Retorna 1 para cada posição de bit em que apenas um dos operandos tem um bit 1.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x ^ y # 0110 (6 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # Output => Binário: 0b110 | Decimal: 6
    ```

* **'`<<`' (Deslocamento à Esquerda)**: Move os bits dos números para a esquerda.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x << y # 101000 (40 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # Output => Binário: 0b101000 | Decimal: 40
    ```

* **'`>>`' (Deslocamento à Direita)**: Move os bits dos números para a direta.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x >> y # 0000 (0 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # Output => Binário: 0b0 | Decimal: 0
    ```

### Operadores de Atribuição

O operador de atribuição mais comum é **`=`**, mas também há outros operadores que realizam uma operação e armazenam o resultado na variável.

**Os operadores de atribuição são:**

* **'`=`'**: Atribui o valor à variavel.
* **'`+=`'**: Soma um valor à variável.

    ``` py
    x = 5
    x += 2
    print(x) # Output => 7
    ```

* **'`-=`'**: Subtrai um valor da variável.

    ``` py
    x = 5
    x -= 2
    print(x) # Output => 3
    ```

* **'`*=`'**: Multiplica a variável por um valor.

    ``` py
    x = 5
    x *= 2
    print(x) # Output => 10
    ```

* **'`/=`'**: Divide a variável por um valor.

    ``` py
    x = 5
    x /= 2
    print(x) # Output => 2.5
    ```

* **'`//=`'**: Calcula a divisão inteira da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x //= 2
    print(x) # Output => 2
    ```

* **'`%=`'**: Calcula o resto da divisão da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x %= 2
    print(x) # Output => 1
    ```

* **'`**=`'**: Calcula a potência da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x **= 2
    print(x) # Output => 25
    ```

* **'`&=`'**: Realiza a operação bit a bit AND com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x &= 3
    print(x) # Output => 1
    ```

* **'`|=`'**: Realiza a operação bit a bit OR com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x |= 3
    print(x) # Output => 7
    ```

* **'`^=`'**: Realiza a operação bit a bit XOR com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x ^= 3
    print(x) # Output => 6
    ```

* **'`<<=`'**: Desloca os bits da variável para a esquerda na mesma quantidade de vezes do valor.

    ``` py
    x = 5
    x <<= 3
    print(x) # Output => 40
    ```

* **'`>>=`'**: Desloca os bits da variável para a direita na mesma quantidade do valor.

    ``` py
    x = 5
    x >>= 3
    print(x) # Output => 0
    ```

## Tuplas

Permitem armazenar vários elementos em uma única variável, sem permitir alteração desses elementos (tuplas são imutáveis).

**Sintaxe:**

``` py
nomeTupla = (elemento1, elemento2, ..., elementoN)
```

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python')
print(languages) # Output => ('JavaScript', 'PHP', 'Python')
```

A função **`tuple()`** ou simplesmente **`()`** criam uma tupla vazia.

**Exemplo:**

``` py
tuplaVazia = ()

# Ou

tuplaVazia = tuple()
```

É possível criar uma tupla numérica com um range.

**Exemplo:**

``` py
tupla = tuple(range(0, 11, 2))
print(tupla) # Output => (0, 2, 4, 6, 8, 10)
```

### Acesso aos Elementos de uma Tupla

Cada elemento da tupla é numerado com índices começando do 0, podendo ser acessados por notação de colchetes.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python')
print(languages[0]) # Output => JavaScript
print(languages[1]) # Output => PHP
print(languages[2]) # Output => Python
```

### Fatiamento de Tuplas

O fatiamento de tuplas funciona da mesma maneira que em strings e listas.

**Exemplo:**

``` py
tupla = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
print(tupla[3:6]) # Output => (4, 5, 6)
```

Também é possível fatiar pulando elementos com `inicio:fim:saltos`.

**Exemplo:**

``` py
tupla = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
print(tupla[1:8:2]) # Output => (2, 4, 6, 8)
```

### Ordenar Tupla para Impressão

Mesmo que as tuplas sejam imutáveis, é possível organizá-las numericamente ou alfabeticamente para impressão utilizando a função `sorted()`.

**Exemplo:**

``` py
numeros = (2, 4, 1, 5, 3)
letras = ('c', 'a', 'e', 'b', 'd')

print(sorted(numeros)) # Output => [1, 2, 3, 4, 5]
print(sorted(letras)) # Output => ['a', 'b', 'c', 'd', 'e']
```

> **NOTA:** A função `sorted()` retorna uma lista ao invés de uma nova tupla.

Para organizá-las ao contrários, define `True` para o parâmetro **`reverse`**.

**Exemplo:**

``` py
numeros = (2, 4, 1, 5, 3)
letras = ('c', 'a', 'e', 'b', 'd')

print(sorted(numeros, reverse=True)) # Output => [5, 4, 3, 2, 1]
print(sorted(letras, reverse=True)) # Output => ['e', 'd', 'c', 'b', 'a']
```

## Listas

Assim como as tuplas, as listas podem ser usadas para armazenar vários elementos em uma única variável, mas em contraste, as listas são mutáveis.

**Sintaxe:**

``` py
nomeLista = [elemento1, elemento2, ..., elementoN]
```

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python']
print(languages) # Output => ['JavaScript', 'PHP', 'Python']
```

A função **`list()`** ou simplesmente **`[]`** criam uma lista vazia.

**Exemplo:**

``` py
listaVazia = []

# Ou

listaVazia = list()
```

Assim como em tuplas, é possível criar uma lista numérica com um range.

**Exemplo:**

``` py
lista = list(range(0, 11, 2))
print(lista) # Output => [0, 2, 4, 6, 8, 10]
```

### Acesso aos Elementos de uma Lista

Assim como nas tuplas, os elementos nas listas são acessados por notação de colchetes por meio de seus índices numerados.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python']
print(languages[0]) # Output => JavaScript
print(languages[1]) # Output => PHP
print(languages[2]) # Output => Python
```

### Operador `del` para Remover Elementos em Listas

Com o operador **`del`** é possível remover um elemento de uma lista a partir de seu índice.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5]
del lista[2]
print(lista) # Output => [1, 2, 4, 5]
```

### Funções `max()` e `min()` em Listas

As funções `max()` e `min()`, quando recebem listas como argumento, retornam o maior e menor valor dessa lista, respectivamente.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5]
maior = max(lista)
menor = min(lista)

print(maior) # Output => 5
print(menor) # Output => 1
```

### Fatiamento de Listas

O fatiamento de listas funciona da mesma maneira que em strings e tuplas.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(lista[3:6]) # Output => [4, 5, 6]
```

Também é possível fatiar pulando elementos com `inicio:fim:saltos`.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(lista[1:8:2]) # Output => [2, 4, 6, 8]
```

### Métodos para Listas

* **'`append()`'**: Adiciona um dado elemento ao fim de `self`.

    ``` py
    lista = [1, 2, 3, 4]
    lista.append(5)
    print(lista) # Output => [1, 2, 3, 4, 5]
    ```

* **'`insert()`'**: Insere um elemento dentro de `self` em índice específico.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.insert(2, 10)
    print(lista) # Output => [1, 2, 10, 3, 4, 5]
    ```

* **'`remove()`'**: Remove um elemento de `self` pelo valor.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.remove(3)
    print(lista) # Output => [1, 2, 4, 5]
    ```

    Este método remove apenas o primeiro elemento com esse valor.

    ``` py
    lista = [3, 1, 2, 3, 4, 5]
    lista.remove(3)
    print(lista) # Output => [1, 2, 3, 4, 5]
    ```

* **'`pop()`'**: Remove o elemento em um dado índice.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.pop(2)
    print(lista) # Output => [1, 2, 4, 5]
    ```

    Se não passado um argumento, será removido o último elemento da lista.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.pop()
    print(lista) # Output => [1, 2, 3, 4]
    ```

* **'`clear()`'**: Limpa `self`, tornando-a uma lista vazia.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.clear()
    print(lista) # Output => []
    ```

* **'`sort()`'**: Organiza `self` numericamente ou alfabeticamente.

    ``` py
    lista = [3, 1, 2, 5, 4]
    lista.sort()
    print(lista) # Output => [1, 2, 3, 4, 5]
    ```

    Para organizar em ordem contrária, defina o parâmetro `reverse` para `True`.

    ``` py
    lista = [3, 1, 2, 5, 4]
    lista.sort(reverse=True)
    print(lista) # Output => [5, 4, 3, 2, 1]
    ```

* **'`reverse()`'**: Inverte a ordem dos elementos em `self`.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.reverse()
    print(lista) # Output => [5, 4, 3, 2, 1]
    ```

* **'`index()`'**: Retorna o índice de um dado elemento de `self`.

    ``` py
    lista = ['Python', 'Ruby', 'Go']
    indice = lista.index('Ruby')
    print(indice) # Output => 1
    ```

* **'`copy()`'**: Retorna `self` como uma cópia.

    ``` py
    # Declara uma lista
    lista = [1, 2, 3, 4, 5]

    # Cria uma cópia de `lista` e altera o primeiro elemento
    novaLista = lista.copy()
    novaLista[0] = 10

    # Imprime as listas
    print(lista) # Output => [1, 2, 3, 4, 5]
    print(novaLista) # Output => [10, 2, 3, 4, 5]
    ```

## Estruturas Condicionais

Uma estrutura condicional é sempre iniciada com **`if`**, podendo conter nenhum ou vários **`elif`** e terminando ou não com um **`else`**.

**Sintaxe:**

``` py
if condicao1:
    # Bloco se `condicao1` for verdadeira
elif condicao2:
    # Bloco se `condicao2` for verdadeira
else:
    # Bloco se nenhuma das condições for verdadeira
```

**Exemplo:**

``` py
if num > 5:
    print(f'{num} é maior que 5')
elif num < 5:
    print(f'{num} é menor que 5')
else:
    print('O valor é igual a 5')
```

No exemplo acima, dependendo se a variável `num` for maior, menor ou igual a 5 é impresso uma mensagem diferente.

> **NOTA:** Em uma estrutura condicional podem haver vários ou nenhum `elif`. Estruturas condicionais devem ser iniciadas com `if`, e não `elif`.

## Estruturas de Repetição

### Loop `for`

#### `for in range()`

Repete um número específico de vezes a partir de um range.

**Exemplo:**

``` py
for c in range(5):
    print(c, end=' ')
print()
# Output => 0 1 2 3 4
```

> **NOTA:** O valor final é descartado (exclusivo).

É possível criar um range com início, fim e incremento.

**Sintaxe:**

``` py
for variavelDeControle in range(inicio, fim, incremento):
    # Bloco que será repetido
```

Se não definido, o incremento será 1.

> **NOTA:** O `fim` é exclusivo.

**Exemplo:**

``` py
for c in range(0, 11, 2):
    print(c, end=' ')
print()
# Output => 0 2 4 6 8 10
```

#### `for` como Iterador

Com o loop `for` é possível iterar sobre tuplas e listas.

**Sintaxe:**

``` py
for variavelDeControle in tupla/lista:
    # Bloco que será repetido
```

**Exemplo:**

``` py
lista = [2, 4, 6, 8, 10]
for e in lista:
    print(e, end=' ')
print()
# Output => 2 4 6 8 10
```

Para iterar sobre os índices e elementos de uma tupla/lista, use **`for in enumerate()`**.

**Sintaxe:**

``` py
for indice, valor in enumerate(tupla/lista):
    # Bloco que será repetido
```

**Exemplo:**

``` py
lista = ['Go', 'Ruby', 'C', 'Python', 'PHP','JavaScript']
for i, v in enumerate(lista):
    print(f'{i}: {v}')
# Output:
# 0: Go
# 1: Ruby
# 2: C
# 3: Python
# 4: PHP
# 5: JavaScript
```

### Loop `while`

Repete um bloco até que uma dada condição se torne falsa.

**Sintaxe:**

``` py
while condicao:
    # Bloco que será repetido
```

**Exemplo:**

``` py
contador = 0
while contador < 5:
    contador += 1
    print(contador, end=' ')
print()
# Output => 1 2 3 4 5
```

### Controle de Fluxo

As palavras-chave `break` e `continue` são usadas para controlar o fluxo de loops.

* **'`break`'**: Interrompe o loop.
* **'`continue`'**: Pula para a próxima repetição.

**Exemplo com `break`:**

``` py
contador = 0
while True:
    contador += 1
    print(contador, end=' ')
    if contador == 5:
        break
print()
# Output => 1 2 3 4 5
```

No exemplo acima, `while True` cria um loop infinito que só pode ser parado com `break`. O loop é interrompido apenas quando o contador chega a 5.

**Exemplo com `continue`:**

``` py
for c in range(11):
    if c % 2 != 0:
        continue
    print(c, end=' ')
print()
# Output => 0 2 4 6 8 10
```

No exemplo acima, é pulada para a próxima repetição sempre que `c` for ímpar, imprimindo apenas os valores pares.

## Dicionários

Os dicionários são estruturas compostas de pares chave-valor. Cada par chave-valor é um item dentro de um dicionário. Os dicionários permitem como qualquer tipo como valor, tornando-os flexíveis.

**Há duas maneiras de declarar um dicionário:**

``` py
# Com `dict()`
dicionario = dict()

# Com `{}`
dicionario = {}
```

Acima, as duas maneiras declaram um dicionário vazio.

> **OBS.:** É preferível declarar um dicionário vazio com `{}` para facilitar a leitura.

**Sintaxe:**

``` py
dicionario = {
    chave1: valor1,
    chave2: valor2,
    ...
    chaveN: valorN
}
```

**Exemplo:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Imprime os itens do dicionário
print(dicionario['nome'])   # Output => Luana
print(dicionario['idade'])  # Output => 22
```

Como visto no exemplo acima, os valores são acessados por meio de suas chaves.

### Alterar e Criar Chaves

Para **alterar o valor de uma chave**, basta atribuir um novo valor com o operador `=`.

**Exemplo:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Altera os valores das chaves
dicionario['nome'] = 'John'
dicionario['idade'] = 32

# Imprime o dicionário
print(dicionario) # Output => {'nome': 'John', 'idade': 32}
```

Para **criar uma nova chave**, basta selecioná-la como se ela já existesse e atribuir um valor a ela.

**Exemplo:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Cria a chave `sexo`
dicionario['sexo'] = 'feminino'

# Imprime o dicionário
print(dicionario) # Output => {'nome': 'Luana', 'idade': 22, 'sexo': 'feminino'}
```

### Excluir Itens

Para excluir itens em um dicionário, é usado o operador **`del`**, seguido do dicionário e a chave do item por notação de colchetes.

**Exemplo:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Exclui o item `idade`
del dicionario['idade']

# Imprime o dicionário
print(dicionario) # Output => {'nome': 'Luana'}
```

### Iterarão Sobre Dicionários

Com os métodos **`keys()`**, **`values()`** e **`items()`** é possível iterar sobre dicionário com base nas chaves, nos valores e nos itens, respectivamente.

Essas iterações são feitas utilzando o loop **`for`** e o operador **`in`**.

**Exemplo com `keys()`:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Imprime as chaves do dicionário
n = 0
for k in dicionario.keys():
    n += 1
    print(f'Chave {n}: {k}')

# Output:
# Chave 1: nome
# Chave 2: idade
```

**Exemplo com `values()`:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Imprime as chaves do dicionário
n = 0
for v in dicionario.values():
    n += 1
    print(f'Valor {n}: {v}')

# Output:
# Valor 1: Luana
# Valor 2: 22
```

**Exemplo com `items()`:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Imprime as chaves do dicionário
n = 0
for k, v in dicionario.items():
    n += 1
    print(f'{k}: {v}')

# Output:
# nome: Luana
# idade: 22
```

### Métodos para Dicionários

* **'`copy()`'**: Retorna uma cópia de `self`.

    ``` py
    # Dicionario que contém 2 itens
    dicionario = {
        'nome': 'Luana',
        'idade': 22
    }

    # Cria uma cópia do dicionário
    copiaDicionario = dicionario.copy()

    # Altera os valores das chaves
    copiaDicionario['nome'] = 'John'
    copiaDicionario['idade'] = '32'

    # Imprime os dicionários
    print(dicionario)       # Output => {'nome': 'Luana', 'idade': 22}
    print(copiaDicionario)  # Output => {'nome': 'John', 'idade': '32'}
    ```

* **'`clear()`'**: Limpa `self`, tornando-o um dicionário vazio.

    ``` py
    # Dicionario que contém 2 itens
    dicionario = {
        'nome': 'Luana',
        'idade': 22
    }

    # Limpa o dicionário
    dicionario.clear()

    # Imprime o dicionário
    print(dicionario) # Output => {}
    ```

* **'`keys()`'**: Retorna as chaves de `self`. Geralmente é usado para iterar sobre as chaves.

    ``` py
    # Dicionario que contém 2 itens
    dicionario = {
        'nome': 'Luana',
        'idade': 22
    }

    # Chaves do dicionário
    chaves = dicionario.keys()

    # Imprime as chaves do dicionário
    print(chaves) # Output => dict_keys(['nome', 'idade'])
    ```

* **'`values()`'**: Retorna os valores de `self`. Geralmente é usado para iterar sobre os valores.

    ``` py
    # Dicionario que contém 2 itens
    dicionario = {
        'nome': 'Luana',
        'idade': 22
    }

    # Valores do dicionário
    valores = dicionario.values()

    # Imprime as chaves do dicionário
    print(valores) # Output => dict_values(['Luana', 22])
    ```

* **'`items()`'**: Retorna as chaves e os valores de `self`. Geralmente é usado para iterar sobre as chaves e os valores.

    ``` py
    # Dicionario que contém 2 itens
    dicionario = {
        'nome': 'Luana',
        'idade': 22
    }

    # Itens do dicionário
    itens = dicionario.items()

    # Imprime as chaves do dicionário
    print(itens) # Output => dict_items([('nome', 'Luana'), ('idade', 22)])
    ```

## Funções

Funções são declaradas a partir da palavra-chave **`def`**, seguida do nome da função, parênteses com os parâmetros e `:` no final.

**Sintaxe:**

``` py
def nome_funcao(param1, param2, ..., paramN):
    # Bloco da função
```

> **NOTA:** Em Python, é uma convenção usar snake_case para nomes de funções.

**Exemplo:**

``` py
# Função que imprime "Olá, Mundo!"
def ola_mundo():
    print('Olá, Mundo!')

# Chama a função
ola_mundo() # Output => Olá, Mundo!
```

**Exemplo com parâmetros:**

``` py
# Função que imprime uma saudação
def saudacao(nome):
    print(f'Olá, {nome}!')

# Chama a função
saudacao('Mundo') # Output => Olá, Mundo!
```

No exemplo acima, `nome` é um parâmetro da função `saudacao()`, enquanto a string `'Mundo'` passada para a função, é chamada de argumento.

> **NOTA:** Parâmetros podem ser de qualquer tipo de valor. Por causa disso, deve-se tomar cuidado para evitar erros ao passar um valor que não é válido.

É possível passar os argumentos numa ordem diferente na qual os parâmetros foram definidos, para isso, deve ser especificado qual o parâmetro irá receber o argumento, utilizando com `=`.

**Exemplo:**

``` py
# Função que imprime a soma entre dois valores
def soma(x, y):
    print(x + y)

# Chama a função várias vezes com diferentes argumentos
soma(y=2, x=5) # Output => 7
soma(x=1, y=5) # Output => 6
soma(2, y=3)   # Output => 5
```

### Empacotar Argumentos

Empacotar refere-se aos parâmetros que pode receber um ou mais argumentos. Esses parâmetros possuem **`*`** no início do nome, e cada função pode ter apenas um, e ele deve ser o último parâmetro definido.

**Sintaxe:**

``` py
def nome_funcao(param1, param2, *args):
    # Bloco da função
```

> **NOTA:** É uma comum nomear o parâmetro que recebe argumentos variádicos como **`args`**.

Esses parâmetros se tornam listas com os valores passados.

**Exemplo:**

``` py
# Função variádica que imprime a soma de valores
def soma(*args):
    soma = 0
    for i in args:
        soma += i
    print(f'Soma: {soma}')

# Chama a função várias vezes com diferentes argumentos
soma(2, 4)          # Output => 6
soma(5)             # Output => 5
soma(1, 2, 3, 4, 5) # Output => 15
```

Como dito anteriormente, se a função tiver mais de um parâmetro, o parâmetro variádico (que empacota) deve ser o último.

**Exemplo:**

``` py
# Função que imprime a soma da multiplicação de um valor por outros
def mult(x, *args):
    soma = 0
    for i in args:
        soma += x * i
    print(f'Soma: {soma}')

# Chama a função várias vezes com diferentes argumentos
mult(5, 2, 4)           # Output => 30
mult(2, 5)              # Output => 10
mult(0, 1, 2, 3, 4, 5)  # Output => 0
```

### Valor Padrão para Parâmetros

É possível definir um valor padrão para um parâmetro incluindo `=` e o valor padrão ao definir o parâmetro.

**Sintaxe:**

``` py
def nome_funcao(param = valor_padrao):
    # Bloco da função
```

**Exemplo:**

``` py
# Função que imprime a soma entre dois valores
def soma(x, y=5):
    print(x + y)

# Chama a função várias vezes com diferentes argumentos
soma(5, 2)  # Output => 7
soma(3)     # Output => 8
soma(0)     # Output => 5
```

### Retorno de Valores

A palavra-chave **`return`** é usada para retornar valores em funções, podendo esses valores serem de qualquer tipo.

**Sintaxe:**

``` py
def funcao(param1, param2, ..., paramN):
    return valor
```

**Exemplo:**

``` py
# Função que calcula o dobro de um valor
def dobro(x):
    return x * 2

# Armazena o resultado da função em uma variável
resultado = dobro(5)

# Imprime o resultado
print(resultado) # Output => 10
```

> **NOTA:** Uma função pode ter várias declarações `return`, e assim que alcança uma deles a função retorna o valor definido por ela e se encerra.

### Escopo de Variáveis

As variáveis declaradas dentro das funções têm **escopo local**. Variáveis de escopo local funcionam apenas dentro do escopo da função em que foram declaradas.

**Exemplo:**

``` py
def minha_funcao():
    variavel_local = 'Olá, Mundo!'

print(variavel_local) # Não pode acessar a variável
```

Por outro lado, **variáveis globais** funcionam em todo o escopo do código, podendo ser acessadas dentro e fora de qualquer função. Por padrão, todas as variáveis declaradas fora de qualquer função ou classe é global.

``` py
# Variável global
variavel_global = 'Olá, Mundo!'

# Função que acessa e imprime a variável global
def minha_funcao():
    # Imprime a variável global
    print(variavel_global)

# Chama a função
minha_funcao() # Output => Olá, Mundo!
```

É possível **declarar uma variável global dentro de uma função** utilizando a palavra-chave **`global`**, seguido do nome da variável (deve ser feito antes de declarar a variável).

**Exemplo:**

``` py
# Função que declara uma variável global
def minha_funcao():
    global variavel_global
    variavel_global = 'Olá, Mundo!'

# Chama a função
minha_funcao()

# Imprime a variável global
print(variavel_global)
```

> **NOTA:** É necessário chamar a função que declara a variável global antes de utilizá-la, afinal, ela não existirá se não for declarada.

## Tratamento de Erros

Os erros são chamados de exceções, e podem ocorrer de inúmeras maneiras, como erro de sintaxe, erro de valor - como passar uma string para uma função que aceita apenas valores inteiros - e diversos outros.

Exceções são tratadas a partir das estruturas **`try`**, **`except`**, **`else`** e **`finally`**.

* **'`try`'**: Recebe o bloco com potencial de erro(s).
* **'`except`'**: Se a exceção definida no `except` ocorrer no bloco `try`, é executado o bloco definido.
* **'`else`'**: Executa o bloco caso não tenha ocorrido nenhuma exceção (opcional).
* **'`finally`'**: Será executado independentemente de ter ou não ocorrido alguma exceção (opcional).

**Exemplo:**

``` py
# Função que calcula a raíz quadrada de um valor
def raiz_quadrada(x):
    try:
        resultado = x ** 0.5
    except Exception as erro:
        # Aqui, `erro` é um alias para a exceção ocorrida
        return erro.__class__
    else:
        return resultado

# Imprime o resultado
print(raiz_quadrada(25))  # Output => 5.0
print(raiz_quadrada(0))   # Output => 0.0
print(raiz_quadrada('4')) # Output => <class 'TypeError'>
```

No exemplo acima, há a função `raiz_quadrada()` que calcula a raíz quadrada do valor passado como argumento. Se não houver exceções, irá retornar normalmente a raíz quadrada do valor, mas se houver, irá retornar a classe do erro que ocorreu.

É possível tratar cada erro com **`except`**.

**Exemplo:**

``` py
# Função que divide `x` por `y`
def divisao(x, y):
    try:
        resultado = x / y
    except ZeroDivisionError: # Caso `y` seja 0
        return 'ERRO: Não é possível dividir por 0'
    except TypeError: # Caso algum valor passado não seja um número
        return 'ERRO: Valor passado é inválido'
    else:
        return resultado

# Imprime os resultados
print(divisao(5, 2))  # Output => 2.5
print(divisao(3, 0))  # Output => ERRO: Não é possível dividir por 0
print(divisao(9, -1)) # Output => -9.0
```

## Estilo de Texto no Terminal

Para imprimir mensagens coloridas no terminal é utilizao um código ANSI.

**Sintaxe:**

``` py
'\033[estilo;cor;cor_de_fundo'm'
```

**Estilo:**

Refere-se ao estilo da letra.

* **'`0`'**: Padrão
* **'`1`'**: Negrito
* **'`3`'**: Itálico
* **'`4`'**: Sublinhado
* **'`7`'**: Inverte as cores de fundo e texto uma com a outra
* **'`8`'**: Invisível
* **'`9`'**: Riscado

**Cor:**

Refere-se às cores do texto.

* **'`30`', '`90`'**: Cinza escuro
* **'`31`', '`91`'**: Vermelho
* **'`32`', '`92`'**: Verde
* **'`33`', '`93`'**: Amarelo
* **'`34`', '`94`'**: Azul
* **'`35`', '`95`'**: Roxo
* **'`36`', '`96`'**: Ciano
* **'`37`', '`97`'**: Branco
* **'`98`'**: Cinza

**Fundo:**

* **'`41`'**: Vermelho
* **'`42`'**: Verde
* **'`43`'**: Amarelo
* **'`44`'**: Azul
* **'`45`'**: Roxo
* **'`46`'**: Ciano
* **'`47`'**: Branco

**Voltar ao padrão:**

Para redefinir o texto ao padrão:

``` py
'\033[0m'
```

**Exemplo:**

``` py
# Todas as cores em negrito
print("\033[1;30;40mOlá, Mundo!\033[m")
print("\033[1;31;41mOlá, Mundo!\033[m")
print("\033[1;32;42mOlá, Mundo!\033[m")
print("\033[1;33;43mOlá, Mundo!\033[m")
print("\033[1;34;44mOlá, Mundo!\033[m")
print("\033[1;35;45mOlá, Mundo!\033[m")
print("\033[1;36;46mOlá, Mundo!\033[m")
print("\033[1;37;47mOlá, Mundo!\033[m")

# Todas as cores com itálico
print()
print("\033[3;30;40mOlá, Mundo!\033[m")
print("\033[3;31;41mOlá, Mundo!\033[m")
print("\033[3;32;42mOlá, Mundo!\033[m")
print("\033[3;33;43mOlá, Mundo!\033[m")
print("\033[3;34;44mOlá, Mundo!\033[m")
print("\033[3;35;45mOlá, Mundo!\033[m")
print("\033[3;36;46mOlá, Mundo!\033[m")
print("\033[3;37;47mOlá, Mundo!\033[m")

# Todas as cores com sublinhado
print()
print("\033[4;30;40mOlá, Mundo!\033[m")
print("\033[4;31;41mOlá, Mundo!\033[m")
print("\033[4;32;42mOlá, Mundo!\033[m")
print("\033[4;33;43mOlá, Mundo!\033[m")
print("\033[4;34;44mOlá, Mundo!\033[m")
print("\033[4;35;45mOlá, Mundo!\033[m")
print("\033[4;36;46mOlá, Mundo!\033[m")
print("\033[4;37;47mOlá, Mundo!\033[m")
```

**Além disso, é possível combinar estilos:**

``` py
# Negrito, itálico, sublinhado e vermelho
print('\033[1;3;4;31mOlá, Mundo!\033[m')
```
