# Python

## Sintaxe Básica

Uma declaração é terminada assim que acontece uma quebra de linha, ou por **`;`**.

**Com quebra de linha:**

``` py
print('Olá, Mundo!')
print('Olá, Python!')
# Output:
# Olá, Mundo!
# Olá, Python!
```

**Com ponto e vírgula:**

``` py
print('Olá, Mundo!');print('Olá, Python!')
# Output:
# Olá, Mundo!
# Olá, Python!
```

### Comentários

Tudo após **`#`** é considerado comentário, e não será executado como código.

**Exemplo:**

``` py
# Isso é um comentário
```

É especialmente útil para explicar partes do código.

**Exemplo:**

``` py
print('Olá, Mundo!') # Imprime "Olá, Mundo!"
```

#### Comentários de Múltiplas Linhas

Para comentar múltiplas linhas, você pode escrever `#` em cada uma delas, ou usar string multilinha.

Uma string multilinha, quando não atribuída a uma variável, é ignorada pelo interpretador.

**Exemplo:**

``` py
'''
Isso
é um
Comentário
Multilinha
'''

"""
Isso também
é um
Comentário multilinha
"""

# Isso também
# é um
# Comentário multilinha
```

> **OBS.:** Strings podem ser escritas com aspas simples ou duplas, e o mesmo vale para strings multiplinha.

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

### Atribuição Múltipla de Valores

É possível atribuir valores às variáveis em uma única linha.

**Exemplo:**

``` py
# Atribui valores às variáveis `x`, `y` e `z`
x, y, z = 5, 'Olá, Mundo', 10.2

# Imprime as variáveis
print(x) # Output => 5
print(y) # Output => Olá, Mundo!
print(z) # Output => 10.2
```

**Para atribuir um único valor à várias variáveis:**

``` py
# Atribui o valor 10 para `x`, `y` e `z`
x = y = z = 10

# Imprime as variáveis
print(x) # Output => 10
print(y) # Output => 10
print(z) # Output => 10
```

**Desempacotar:**

É chamado **desempacotar** o processo de extrair valores de uma tupla ou lista para variáveis.

**Exemplo:**

``` py
# Lista com nomes de linguagens
linguagens = ['Python', 'C', 'JavaScript']

# Atribui às variáveis `x`, `y` e `z` os elementos da lista
x, y, z = linguagens

# Impriem as variáveis
print(x) # Output => Python
print(y) # Output => C
print(z) # Output => JavaScript
```

### Nomes de Variáveis

* Devem começar com uma letra ou um `_`.
* Podem conter apenas caracteres alfanuméricos e underscores (underline). Seria: (A-z, 0-9 e `_`).
* Variáveis são case-sensitive, ou seja, `nome` é diferente de `NOME` e qualquer outra variação.
* Não pode ter o mesmo nome que uma palavra-chave Python, como `while`, `for`, `if`, `def`, etc.
* Normalmente, é usado snake_case para separar as palavras em nomes de variáveis. Em snake_case, as letras são todas escritas em minúsculo, e as palavras são separadas com underscore (Ex.: `nome_variavel`).

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

**Strings Multilinhas:**

Strings multilinhas são escritas com três aspas (simples ou duplas).

**Exemplo:**

``` py
str = '''Lorem ipsum dolor sit amet, consectetur
adipiscing elit. Aenean in mi scelerisque, sodales
turpis non, cursus odio.
Integer posuere quis est sed malesuada'''

# Imprime a string multilinha
print(str)
```

Na impressão, as quebras de linhas são inseridas assim como definidas na string.

> **NOTA:** Se não for atribuída a uma variável ou usada como argumento em uma função, será considerada um comentário multilinha.

#### Concatenação de Strings

O operador `+` pode ser usado para concatenar strings.

**Exemplo:**

``` py
str1 = 'Olá'
str2 = 'Mundo'
print(str1 + ' ' + str2) # Output => Olá Mundo
```

O operador `+` é também o operador de adição, e se tentar somar um número e uma string, ocorrerá um erro.

**Exemplo:**

``` py
x = 5
y = 'Olá'
print(x + y) # Ocorrerá um erro
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

Para verificar se não existe, poderá usar **`not in`**.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
analise = 'Mundo' not in str
print(analise) # Output => False
```

#### Índices em Strings

Cada caractere em uma string representa um índice, sendo o primeiro caractere o índice `0`, o segundo `1`, o terceiro `2` e assim por diante.

> **NOTA:** Strings são arrays (listas) de caracteres, e por isso podem ter seus elementos (caracteres) acessados por índices.

Esses índices são acessados por notação de colchete.

**Exemplo:**

``` py
str = 'Olá'
print(str[0]) # Output => O
print(str[1]) # Output => l
print(str[2]) # Output => á
```

**Índices negativos** representam os caracteres começando do final, ou seja, `-1` representa o último caractere, `-2` representa o penúltimo, e assim por diante.

**Exemplo:**

``` py
str = 'Olá'
print(str[-1]) # Output => á
print(str[-2]) # Output => l
print(str[-3]) # Output => O
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

Definir índices numéricos entre as chaves na string fará com que os argumentos de **`format()`** sejam formatados de acordo.

**Exemplo:**

``` py
num1 = 5
num2 = 2
print("A soma entre {1} e {0} é {2}".format(num2, num1, num1 + num2))
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

#### Caracteres de Escape

* **'`\'`'**: Aspa simples.
* **'`\"`'**: Aspa dupla.
* **'`\\`'**: Barra invertida.
* **'`\n`'**: Nova linha.
* **'`\r`'**: Retorno.
* **'`\t`'**: Tabulação.
* **'`\b`'**: Retrocesso.
* **'`\f`'**: Feed de formulário.
* **'`\ooo`'**: Valor octal.
* **'`\xhh`'**: Valor hex.

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

### Valores Booleanos

Os valores booleanos são **`True`** e **`False`**, que representam verdadeiro e falso, respectivamente.

**Exemplo:**

``` py
x = True
y = False
```

São usados principalmente como condições para estruturas condicionais, loops, ou como retorno de valores em funções.

### Valor `None`

Representa um valor vazio.

``` py
x = None
```

Geralmente é o que funções retornam em caso de erro, e em como condição, funciona como `False`.

### Conversão de Valores

Primeiramente, para verificar o tipo de um valor, você pode usar a função `type()` e passar o valor como argumento, ou você pode utilizar o método **`__class__`** diretamente no valor.

**Exemplo com `type()`:**

``` py
x = 5
y = 'Olá, Mundo!'
z = 10.2

print(type(x)) # Output => <class 'int'>
print(type(y)) # Output => <class 'str'>
print(type(z)) # Output => <class 'float'>
```

**Exemplo com `__class__`:**

``` py
x = 5
y = 'Olá, Mundo!'
z = 10.2

print(x.__class__) # Output => <class 'int'>
print(y.__class__) # Output => <class 'str'>
print(z.__class__) # Output => <class 'float'>
```

Para converter um valor para outro tipo (*casting*), é usada a função do tipo para qual o valor será convertido, e passar o valor que será convertido como argumento.

**Exemplo:**

``` py
x = str(5)
y = int('2')
z = float(10)

print(type(x)) # <class 'str'>
print(type(y)) # <class 'int'>
print(type(z)) # <class 'float'>
```

## Operadores

Os principais operadores são:

* Operadores aritméticos
* Operadores de comparação
* Operadores lógicos
* Operadores de Identidade
* Operadores de Afiliação
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

### Operadores de Identidade

* **'`is`'**: Verdadeiro se ambos os valores corresponderem aos mesmo endereço de memória.

    ``` py
    x = 5
    y = 5
    print(x is y) # Output => True

    x = [1, 2, 3]
    y = [1, 2, 3]
    print(x is y) # Output => False
    ```

* **'`is not`'**: Verdadeiro se ambos os valores não corresponderem ao mesmo endereço de memória.

    ``` py
    x = 5
    y = 5
    print(x is not y) # Output => False

    x = [1, 2, 3]
    y = [1, 2, 3]
    print(x is not y) # Output => True
    ```

> **NOTA:** O Python otimiza o uso da memória e reutiliza objetos imutáveis como inteiros de pequeno valor. Isso é conhecido como *int caching* (memorização de inteiros). Para valores pequenos, como pequenos inteiros, o Python reutiliza o mesmo objeto na memória.

### Operadores de Afiliação

* **'`in`'**: Verdadeiro se o primeiro operando estiver dentro do segundo.

    ``` py
    lista = [1, 2, 3, 4, 5]
    print(2 in lista) # Output => True
    ```

* **'`not in`'**: Verdadeiro se o primeiro operando não estiver dentro do segundo.

    ``` py
    lista = [1, 2, 3, 4, 5]
    print(2 not in lista) # Output => False
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

### Precedência de Operadores

1. **'`()`'**
1. **'`**`'**
1. **'`+x`', '`-x`', '`~x`'**
1. **'`*`', '`/`', '`//`', '`%`'**
1. **'`+`', '`-`'**
1. **'`<<`', '`>>`'**
1. **'`&`'**
1. **'`^`'**
1. **'`|`'**
1. **'`==`', '`!=`', '`>`', '`>=`', '`<`', '`<=`', '`is`', '`is not`', '`in`', '`not in`'**
1. **'`not`'**
1. **'`and`'**
1. **'`or`'**

Se dois operadores têm a mesma precedência, a expressão executa quem vier primeiro.

## Tuplas

Permitem armazenar vários elementos em uma única variável, sem permitir alteração desses elementos (tuplas são imutáveis).

**Sintaxe:**

``` py
nomeTupla = (elemento1, elemento2, ..., elementoN)
```

> **NOTA:** Os parênteses podem ser omitidos, mas é uma boa prática mantê-los para melhorar a legibilidade.

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

Índices negativos correspondem aos elementos do final, por exemplo: `-1` corresponde ao último elemento, `-2`, corresponde ao penúltimo elemento, etc.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python')
print(languages[-3]) # Output => JavaScript
print(languages[-2]) # Output => PHP
print(languages[-1]) # Output => Python
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

### Desempacotar Tupla

É chamado de ***unpacking*** a ação de atruibuir os elementos de uma tupla ou lista à variáveis.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python', 'Ruby')
a, b, c, d = languages
print(a) # Output => JavaScript
print(b) # Output => PHP
print(c) # Output => Python
print(d) # Output => Ruby
```

Se definido **`*`** no início do nome de uma das variáveis, ela será uma lista com os elementos que não têm variáveis definidas.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python', 'Ruby')
a, *b, c = languages
print(a) # Output => JavaScript
print(b) # Output => ['PHP', 'Python']
print(c) # Output => Ruby
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

Índices negativos, assim como em tuplas, referenciam os elementos do final da lista.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python']
print(languages[-3]) # Output => JavaScript
print(languages[-2]) # Output => PHP
print(languages[-1]) # Output => Python
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

### Desempacotar Lista

Assim como as tuplas, é possível atribuir os elementos de uma lista à variáveis.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
a, b, c, d = languages
print(a) # Output => JavaScript
print(b) # Output => PHP
print(c) # Output => Python
print(d) # Output => Ruby
```

**Exemplo com `*`:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
a, *b, c = languages
print(a) # Output => JavaScript
print(b) # Output => ['PHP', 'Python']
print(c) # Output => Ruby
```

### Compreensão de Lista

Uma ***list comprehension*** oferece uma sintaxe curta quando a necessidade é criar uma nova lista baseada nos valores de uma lista já existente.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
new_list = []

for i in languages:
    if "P" in i:
        new_list.append(i)

print(new_list) # Output => ['PHP', 'Python']
```

Com uma compreensão de lista, é possível fazer exatamente o mesmo que no exemplo acima, porém de maneira mais curta.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
new_list = [i for i in languages if "P" in i]

print(new_list) # Output => ['PHP', 'Python']
```

**A sintaxe é a seguinte:**

``` py
lista = [expressao for item in iterador if condicao]
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

* **'`extend()`'**: Atribui a `self` os elementos de uma dada lista ou tupla.

    ``` py
    lista1 = [1, 2, 3]
    lista2 = [4, 5, 6]

    lista1.extend(lista2)
    print(lista1) # Output => [1, 2, 3, 4, 5, 6]
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

#### `else` no loop `for`

O bloco **`else`** em conjunto com o loop `for` é executado quando o loop chega ao fim.

**Exemplo:**

``` py
for c in range(6):
    print(c, end=' ')
else:
    print('FIM!')
# Output => 0 1 2 3 4 5 FIM!
```

> **NOTA:** Se o loop `for` for parado com `break`, o bloco `else` não irá executar.

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

#### `else` no loop `while`

O bloco **`else`** em conjunto com o loop `while` é executado quando o loop chega ao fim.

**Exemplo:**

``` py
i = 0
while i < 5:
    i += 1
    print(i, end=' ')
else:
    print('FIM!')
# Output => 1 2 3 4 5 FIM!
```

> **NOTA:** Se o loop `while` for parado com `break`, o bloco `else` não irá executar.

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

## Conjuntos

Os conjuntos são usados para armazenar múltiplos itens em uma única variável.

Um conjunto é uma coleção não ordenada, não indexada e imutátal.

**Sintaxe:**

``` py
my_set = {'item1', 'item2', 'item3'}
```

Em um conjunto, os itens não são ordenados (não há uma ordem definida), são imutáveis - o que significa que após a criação, não é possível alterar os itens - e não podem ser duplicados.

Como não são permitidos itens duplicados, valores como `1` e `True` não são permitidos, já que ambos são tratados como o mesmo valor.

**Exemplo:**

``` py
my_set = {'Olá', True, 3, 2.5, 1}
print(my_set) # Output => {True, 2.5, 3, 'Olá'}
```

Perceba que o valor `1` não existe, já que antes dele foi declarado `True`.

### Tipos de Dados em um Conjunto

Um **set** permite qualquer tipo de dado, com exceção de tipos especiais, como listas, tuplas, dicionários e outros sets.

### Comprimento de um Conjunto

Para obter o comprimento de um conjunto, é usada a função **`len()`**.

**Exemplo:**

``` py
my_set = {'Olá', 3, 2.5, True}
print(len(my_set)) # Output => 4
```

### Acesso aos Elementos de um Conjunto

Como dito anteriormente, não é possível acessar os elementos de um set por índices. Para acessar os elementos, é usado um loop.

**Exemplo:**

``` py
my_set = {'Olá', 3, 2.5, True}

for i in my_set:
    print(i)

# Output:
# Olá
# True
# 2.5
# 3
```

### Adicionar Itens a um Conjunto

Quando um conjunto é criado, não é possível alterar seus itens, mas é possível adicionar novos itens.

A adição de novos itens é feita com o método **`add()`**.

**Exemplo:**

``` py
my_set = {'Olá', 3, 2.5, True}
my_set.add('Olá, Python!')

print(my_set)
# Output => {True, 2.5, 3, 'Olá, Python!', 'Olá'}
```

Há também o método **`update()`**, que permite **atualizar um set com outro set, tupla ou lista**.

**Exemplo:**

``` py
set1 = {3, 'Oi', False}
set2 = {True, 2.5, 'Olá'}

set1.update(set2)

print(set1)
# Output => {False, True, 2.5, 3, 'Olá', 'Oi'}
```

### Remover Itens de um Conjunto

Para remover um itens de um set, é usado o método **`remove()`** ou **`discard()`**.

**Exemplo:**

``` py
my_set = {3, 'Oi', False, 2.5, True}

my_set.remove('Oi')
my_set.discard(False)

print(my_set)
# Output => {True, 2.5, 3}
```

> **NOTA:** Será retornado um erro caso o argumento do método `remove()` não existir dentro do set. Por outro lado, o método `discard()` ignora caso o itens não exista dentro do set, prosseguindo como se tivesse excluído o item.

O método **`pop()`** irá excluir um item aleatório. Já que sets não possuem uma ordem definida, não há como esperar qual item será excluído.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

item = my_set.pop()

print(item)   # Output => False
print(my_set) # Output => {True, 2.5, 3, 'Oi'}
```

O método **`clear()`** irá excluir todos os itens do set.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

my_set.clear()

print(my_set) # Output => set()
```

A palavra-chave **`del`** exclui um set por completo.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

del my_set

# Ocorrerá um erro, já que `my_set` não existe mais
print(my_set) # Output => set()
```

### Unir Coleções

O método **`union()`** retorna um novo set, que é a junção de `self` com um dado set, lista ou tupla.

**Exemplo:**

``` py
set1 = {'Oi', 3, 2.5, True}
set2 = {5, 2, False, 'Olá'}
set3 = set1.union(set2)

print(set3)
# Output => {False, True, 2.5, 3, 'Oi', 2, 5, 'Olá'}
```

### Itens Duplicados em um Conjunto

O método **`intersection()`** retorna os itens que existem em ambos os sets.

**Exemplo:**

``` py
set1 = {'Oi', 5, 3, 2.5, True}
set2 = {5, 2, False, 'Olá', True}
set3 = set1.intersection(set2)

print(set3)
# Output => {True, 5}
```

Para manter apenas os itens que não são duplicados, há o método **`symmetric_difference()`**.

**Exemplo:**

``` py
set1 = {'Oi', 5, 3, 2.5, True}
set2 = {5, 2, False, 'Olá', True}
set3 = set1.symmetric_difference(set2)

print(set3)
# Output => {False, 2, 2.5, 3, 'Oi', 'Olá'}
```

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

Outra opção para excluir itens em um dicionário, é o método **`pop()`**, que recebe como argumento a chave do item que será excluído.

**Exemplo:**

``` py
# Dicionario que contém 2 itens
dicionario = {
    'nome': 'Luana',
    'idade': 22
}

# Exclui o item `nome`
item_excluido = dicionario.pop('nome')

# Imprime o dicionário
print(item_excluido) # Output => Luana
print(dicionario) # Output => {'idade': 22}
```

> **NOTA:** Há também o método **`popitem()`**, que exclui o último item do dicionário.

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

Definir **`/`** como argumento impede essa atribuição por parâmetro para todos os parâmetros antes de `/`.

**Exemplo:**

``` py
def soma(x, y, /):
    print(x + y)

soma(5, 2) # Output => 7
```

No exemplo acima, ocorrerá um erro se os argumentos forem passados por palavra-chave, como `soma(y = 2, x = 5)`.

Por outro lado, definir **`*`** como parâmetro irá permitir apenas que os argumentos sejam passados por palavra-chave. Isso vale para todos os argumentos após `*`.

**Exemplo:**

``` py
def soma(*, x, y):
    print(x + y)

soma(y = 5, x = 2) # Output => 7
```

No exemplo acima, ocorrerá um erro se os argumentos forem passados por posição, como `soma(5, 2)`.

É possível combinar `*` e `/` em uma mesma função, definindo os parâmetros que receberão argumentos por posição e os parâmetros que receberão os argumentos por palavra-chave.

**Exemplo:**

``` py
def soma(x, y, /, *, z):
    print(x + y + z)

soma(5, 2, z = 3) # Output => 10
```

No exemplo acima, os parâmetros `x` e `y` só podem receber argumentos por posição, enquanto o parâmetro `z` só pode receber argumento por palavra-chave.

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

#### Argumentos de Palavras-chave

Indicar dois asteriscos no início de um parâmetro, tornará ele um dicionário, e assim seus argumentos podem ser passados de maneira variádica.

**Exemplo:**

``` py
def my_function(**kwargs):
    print(kwargs)

my_function(name='Luana', idade='23')
# Output => {'name': 'Luana', 'idade': '23'}
```

> **NOTA:** Argumentos de Palavras-chaves arbitrárias são frequentemente abreviadas para **`**kwargs`**.

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

### Função Recursiva

Uma função recursiva é uma função que chama ela mesma.

**Exemplo:**

``` py
def somar(num):
    if num > 0:
        result = num + somar(num - 1)
        print(result)
    else:
        result = 0
    return result

somar(5)
# Output:
# 1
# 3
# 6
# 10
# 15
```

A função **`somar()`** no exemplo acima imprime a soma do valor dado pelo seus antecessores até chegar a 0.

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

## Manipulação de Arquivos

Para manipular arquivos, existem três tipos de operações básicas: leitura, escrita e anexação.

Ao terminar de usar o arquivo, é importante fechá-lo corretamente com o método `close()`, mas com o **`with`**, isso se torna desnecessário, já que ele fecha o arquivo no final.

**Exemplo sem `with`:**

``` py
# Abre o arquivo no modo de leitura
file = open('text.txt', 'r', encoding='UTF-8')

# Lê o arquivo
content = file.read()

# Imprime o conteúdo do arquivo
print(content)
# Output:
# Olá, Mundo!
# Olá, Python!

# Fecha o arquivo
file.close()
```

**Exemplo com `with`:**

``` py
# Abre o arquivo no modo leitura
with open('text.txt', 'r', encoding='UTF-8') as file:
    # Lê o conteúdo do arquivo
    content = file.read()

    # Imprime o conteúdo do arquivo
    print(content)

# Output:
# Olá, Mundo!
# Olá, Python!
```

### Leitura de Arquivos

Para ler arquivos, é usada a função **`open()`** no modo **`r`** para abrir o arquivo e **`read()`** para obter o conteúdo.

**Exemplo:**

Arquivo de texto:

``` txt
Olá, Mundo!
Olá, Python!
```

``` py
with open('text.txt', 'r', encoding='UTF-8') as file:
    content = file.read()
    print(content)
# Output:
# Olá, Mundo!
# Olá, Python!
```

O parâmetro **`encoding`** se refere ao formato, e nesse caso, ele é definido para `'UTF-8'` para ler corretamente os acentos nas letras.

**Ler linhas do arquivo:**

O método **`readlines()`** retorna uma lista onde cada elemento é uma linha do arquivo.

**Exemplo:**

Arquivo de texto:

``` txt
Olá, Mundo!
Olá, Python!
```

``` py
with open('text.txt', 'r', encoding='UTF-8') as file:
    content = file.readlines()
    print(content) # Output: ['Olá, Mundo!\n', 'Olá, Python!']
```

**Iterar sobre as linhas:**

É possível iterar sobre cada linha em um arquivo a partir do próprio arquivo em conjunto com o loop `for`.

**Sintaxe:**

``` py
for linha in arquivo:
    # Bloco de código
```

**Exemplo:**

Arquivo de `text.txt`:

``` txt
Olá, Mundo!
Olá, Python!
```

Arquivo `main.py`:

``` py
with open('text.txt', 'r', encoding='UTF-8') as file:
    c = 0
    for line in file:
        c += 1
        print(f'{c}: {line}')
# Output:
# 1: Olá, Mundo!

# 2: Olá, Python!
```

### Escrita em Arquivos

Para escrever em arquivos, é usado o modo **`w`** na função **`open()`**, e **`write()`** para escrever o conteúdo.

**Exemplo:**

``` py
with open('text.txt', 'w', encoding='UTF-8') as file:
    file.write("Olá, Mundo!")
```

> **NOTA:** Mesmo que não seja para leitura, é importante definir o formato para `'UTF-8'`, ou caracteres acentuados não serão escritos da maneira correta.

Se o arquivo não existir, ele será criado. Se o arquivo existir, terá seu conteúdo sobrescrito pelo novo.

### Anexar em Arquivos

Para anexar em arquivos, ou seja, adicionar conteúdo a ele sem sobrescrever o anterior, é utilizada função **`open()`** com o modo **`a`**.

**Exemplo:**

Arquivo de `text.txt`:

``` txt
Olá, Mundo!
```

Arquivo `main.py`:

``` py
with open('text.txt', 'a', encoding='UTF-8') as file:
    file.write("\nOlá, Python!")
```

O código acima adiciona uma nova linha ao arquivo de texto com o texto "Olá, Python!".

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
