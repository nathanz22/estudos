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

<!-- Já vai! -->
