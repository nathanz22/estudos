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

## *Output* de Valores

Para imprimir valores, é usada a função **`print()`**.

**Exemplo:**

``` py
print('Olá, Mundo!') # -> Olá, Mundo!
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
print(x) # -> 5
print(y) # -> Olá, Mundo!
print(z) # -> 10.2
```

**Para atribuir um único valor à várias variáveis:**

``` py
# Atribui o valor 10 para `x`, `y` e `z`
x = y = z = 10

# Imprime as variáveis
print(x) # -> 10
print(y) # -> 10
print(z) # -> 10
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
print(x) # -> Python
print(y) # -> C
print(z) # -> JavaScript
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
print(type(23)) # -> <class 'int'>
print(type('Olá, Mundo!')) # -> <class 'str'>
print(type(5.2)) # -> <class 'float'>
print(type(True)) # -> <class 'bool'>
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
print(str1 + ' ' + str2) # -> Olá Mundo
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
print(countChars) # -> 11
```

#### Operador `in` para Strings

O operador **`in`** pode ser usado para verificar se uma dada string existe dentro de outra, e retorna `True` ou `False` dependendo dessa verificação.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
analise = 'Mundo' in str
print(analise) # -> True
```

Para verificar se não existe, poderá usar **`not in`**.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
analise = 'Mundo' not in str
print(analise) # -> False
```

#### Índices em Strings

Cada caractere em uma string representa um índice, sendo o primeiro caractere o índice `0`, o segundo `1`, o terceiro `2` e assim por diante.

> **NOTA:** Strings são arrays (listas) de caracteres, e por isso podem ter seus elementos (caracteres) acessados por índices.

Esses índices são acessados por notação de colchete.

**Exemplo:**

``` py
str = 'Olá'
print(str[0]) # -> O
print(str[1]) # -> l
print(str[2]) # -> á
```

**Índices negativos** representam os caracteres começando do final, ou seja, `-1` representa o último caractere, `-2` representa o penúltimo, e assim por diante.

**Exemplo:**

``` py
str = 'Olá'
print(str[-1]) # -> á
print(str[-2]) # -> l
print(str[-3]) # -> O
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
print(novaStr) # -> Mun
```

Caso não definido o início, será considerado 0, e se não definido o fim, será considerado todo o resto da string.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
print(str[5:]) # -> Mundo!
print(str[:3]) # -> Olá
```

É possível saltar posições ao definir `inicio:fim:saltos`, onde o número final é a quantidade de saltos nos índices.

**Exemplo:**

``` py
str = 'Olá, Mundo!'
print(str[5::2]) # -> Mno
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
# -> A soma entre 5 e 2 é 7
```

Definir índices numéricos entre as chaves na string fará com que os argumentos de **`format()`** sejam formatados de acordo.

**Exemplo:**

``` py
num1 = 5
num2 = 2
print("A soma entre {1} e {0} é {2}".format(num2, num1, num1 + num2))
# -> A soma entre 5 e 2 é 7
```

**Exemplo com *F string*:**

``` py
num1 = 5
num2 = 2
print(f"A soma entre {num1} e {num2} é {num1 + num2}")
# -> A soma entre 5 e 2 é 7
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
# -> -------Olá, Mundo!-------
```

**Exemplo com *F String*:**

``` py
str = 'Olá, Mundo!'
print(f'{str:-^25}')
# -> -------Olá, Mundo!-------
```

Em ambos os exemplos é impresso `"Olá, Mundo!"` entre os caracteres `"-"`, que preenchem o espaço até a string inteira ocupar 25 caracteres.

**Os formatadores são:**

* **'`:<`'**: Alinhamento à esquerda.
* **'`:>`'**: Alinhamento à direita.
* **'`:^`'**: Alinhamento no centro.
* **'`:=`'**: Posiciona o resultado mais a direita possível.
* **'`:+`'**: Indica se o resultado é positivo ou negativo.
* **'`:-`'**: O resultado será sempre mostrado como negativo.
* **'`:{whitespace}`'**: Irá inserir um espaço em branco antes do resultado.
* **'`:,`'**: Formata o resultado com uma vírgula separando a milhar.
* **'`:_`'**: Formata o resultado com um *underline* separando a milhar.
* **'`:b`'**: Mostra o resultado em binário.
* **'`:c`'**: Converte o resultado para o caractere Unicode correspondente.
* **'`:d`'**: Mostra o resultado em decimal.
* **'`:e`'**: Mostra o resultado em formato científico ("e" em minúsculo).
* **'`:E`'**: Mostra o resultado em formato científico ("E" em maiúsculo).
* **'`:f`'**: Fixa os números de ponto flutuante.
* **'`:F`'**: Fixa os números de ponto flutuante em formato maiúsculo.
* **'`:g`'**: Formato geral.
* **'`:G`'**: Formato geral usando notação científica com "E".
* **'`:o`'**: Mostra o resultado em octal.
* **'`:x`'**: Mostra o resultado em hexadecimal (minúsculo).
* **'`:X`'**: Mostra o resultado em hexadecimal (maiúsculo).
* **'`:n`'**: Em formato numérico.
* **'`:%`'**: Em formato de porcentagem.

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
    print(newStr) # -> OLÁ, MUNDO!
    ```

* **'`lower()`'**: Retorna `self` com todos os caracteres em minúsculo.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.lower()
    print(newStr) # -> olá, mundo!
    ```

* **'`capitalize()`'**: Retorna `self` com o primeiro caractere em maiúsculo e o resto em minúsculo.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.capitalize()
    print(newStr) # -> Olá, mundo!
    ```

* **'`title()`'**: Retorna `self` com o primeiro caractere de todas as palavras em maiúsculo e o resto em minúsculo.

    ``` py
    str = 'oLá, mUndO!'
    newStr = str.title()
    print(newStr) # -> Olá, Mundo!
    ```

* **'`count()`'**: Retorna a quantidade de ocorrência de uma dada substring em `self`.

    ``` py
    str = 'Olá, Mundo!!!'
    contador = str.count('!')
    print(contador) # -> 3
    ```

* **'`find()`'**: Retorna o índice em que uma dada substring se inicia em `self`.

    ``` py
    str = 'Olá, Mundo!'
    indice = str.find('Mundo!')
    print(indice) # -> 5
    ```

* **'`replace()`'**: Substitui uma substring de `self` por uma nova substring.

    ``` py
    str = 'Olá, Mundo!'
    newStr = str.replace('Mundo', 'Python')
    print(newStr) # -> Olá, Python!
    ```

    É possível passar um terceiro argumento, e esse argumento define a quantidade de substituições que serão feitas.

    ``` py
    str = 'Olá, Mundo! Olá, Mundo!'
    newStr = str.replace('Mundo', 'Python', 1)
    print(newStr) # -> Olá, Python! Olá, Mundo!
    ```

    O valor padrão para esse terceiro padrão é `-1`, que define que serão feitas todas as substituições.

* **'`strip()`'**: Retorna `self` sem espaços em branco no início e no fim.

    ``` py
    str = '     Olá, Mundo!     '
    newStr = str.strip()
    print(newStr) # -> Olá, Mundo!
    ```

    Os métodos **`lstrip()`** e **`rstrip()`** removem apenas os espaços em branco na esquerda e direita, respectivamente.

* **'`split()`'**: Retorna uma lista a partir de `self` e um separador (se não especificado, será os espaços).

    ``` py
    str = 'Eu amo Python'
    lista = str.split()
    print(lista) # -> ['Eu', 'amo', 'Python']
    ```

    Exemplo com um seperador definido:

    ``` py
    str = 'Eu-amo-Python'
    lista = str.split('-')
    print(lista) # -> ['Eu', 'amo', 'Python']
    ```

    É possível passar um segundo argumento, que define o limite de elementos que a lista terá.

    ``` py
    str = 'Eu-amo-Python'
    lista = str.split('-', 1)
    print(lista) # -> ['Eu', 'amo-Python']
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

print(type(x)) # -> <class 'int'>
print(type(y)) # -> <class 'str'>
print(type(z)) # -> <class 'float'>
```

**Exemplo com `__class__`:**

``` py
x = 5
y = 'Olá, Mundo!'
z = 10.2

print(x.__class__) # -> <class 'int'>
print(y.__class__) # -> <class 'str'>
print(z.__class__) # -> <class 'float'>
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

## *Input* de Valores

A função **`input()`** retorna o valor digitado pelo usuário. Essa função aceita uma string como argumento, que será impressa antes da digitação do usuário. Essa string é usada para informar o usuário sobre o que ele deve digitar.

**Exemplo:**

``` py
valor = input('Digite algo: ')
print(valor) # Imprime o valor digitado pelo usuário
```

A função **`input()`** retorna uma string, então se o valor requisitado ao usuário for numérico, deverá ser feita a conversão.

**Exemplo:**

``` py
x = input('Digite um número: ')
y = input('Digite outro número: ')
soma = int(x) + int(y)
print(f'A soma entre {x} e {y} é {soma}')
```

Essa conversão pode ser feita na função `input` diretamente:

``` py
x = int(input('Digite um número: '))
y = int(input('Digite outro número: '))
print(f'A soma entre {x} e {y} é {x+y}')
```

> **NOTA:** O programa para no momento da declaração da função `input()` e continua quando o valor dela é retornado, ou seja, as declações abaixo não são executadas junto à `input()`.

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
print(x + y)    # -> 7
print(x - y)    # -> 3
print(x * y)    # -> 10
print(x / y)    # -> 2.5
print(x // y)   # -> 2
print(x % y)    # -> 1
print(x ** y)   # -> 25
```

### Operadores de Comparação

* **'`==`' (Igual)**: Verdadeiro se ambos os operandos forem iguais.

    ``` py
    print(1 == 1)       # -> True
    print('Py' == "Py") # -> True
    print('5' == 5)     # -> False
    ```

* **'`!=`' (Diferente)**: Verdadeiro se os operandos forem diferentes um do outro.

    ``` py
    print(2 != 5)        # -> True
    print(5.0 != 5)      # -> False
    print('Oi' != 'Olá') # -> True
    ```

* **'`<`' (Menor)**: Verdadeiro se o operando à esquerda for menor.

    ``` py
    print(1 < 5)        # -> True
    print(7 < 6)        # -> False
    print('Oi' < 'Olá') # -> True
    ```

* **'`>`' (Maior)**: Verdadeiro se o operando da esquerda for maior.

    ``` py
    print(7 > 2)        # -> True
    print(2 > 4)        # -> False
    print('Oi' > 'Olá') # -> False
    ```

* **'`<=`' (Menor ou igual)**: Verdadeiro se o operando à esquerda for menor ou igual ao da direita.

    ``` py
    print(0 <= 2) # -> True
    print(5 <= 5) # -> True
    print(2 <= 1) # -> False
    ```

* **'`>=`' (Maior ou igual)**: Verdadeiro se o operando à esquerda for maior ou igual ao da direita.

    ``` py
    print(1 >= -1) # -> True
    print(4 >= 4)  # -> True
    print(2 >= 3)  # -> False
    ```

### Operadores Lógicos

* **'`and`'**: Verdadeiro quando ambos os operandos forem verdadeiro.

    ``` py
    print(True and True)    # -> True
    print(True and False)   # -> False
    print(False and True)   # -> False
    print(False and False)  # -> False
    ```

* **'`or`'**: Verdadeiro se pelo menos um dos operandos for verdadeiro.

    ``` py
    print(True or True)    # -> True
    print(True or False)   # -> True
    print(False or True)   # -> True
    print(False or False)  # -> False
    ```

* **'`not`'**: Inverte o valor (verdadeiro se torna falso e falso se torna verdadeiro).

    ``` py
    print(not True)    # -> False
    print(not False)   # -> True
    ```

### Operadores de Identidade

* **'`is`'**: Verdadeiro se ambos os valores corresponderem aos mesmo endereço de memória.

    ``` py
    x = 5
    y = 5
    print(x is y) # -> True

    x = [1, 2, 3]
    y = [1, 2, 3]
    print(x is y) # -> False
    ```

* **'`is not`'**: Verdadeiro se ambos os valores não corresponderem ao mesmo endereço de memória.

    ``` py
    x = 5
    y = 5
    print(x is not y) # -> False

    x = [1, 2, 3]
    y = [1, 2, 3]
    print(x is not y) # -> True
    ```

> **NOTA:** O Python otimiza o uso da memória e reutiliza objetos imutáveis como inteiros de pequeno valor. Isso é conhecido como *int caching* (memorização de inteiros). Para valores pequenos, como pequenos inteiros, o Python reutiliza o mesmo objeto na memória.

### Operadores de Afiliação

* **'`in`'**: Verdadeiro se o primeiro operando estiver dentro do segundo.

    ``` py
    lista = [1, 2, 3, 4, 5]
    print(2 in lista) # -> True
    ```

* **'`not in`'**: Verdadeiro se o primeiro operando não estiver dentro do segundo.

    ``` py
    lista = [1, 2, 3, 4, 5]
    print(2 not in lista) # -> False
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
    # -> Binário: 0b1 | Decimal: 1
    ```

* **'`|`' (OR)**: Retorna 1 para cada posição de bit em que pelo menos um dos operandos tem o bit 1.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x | y # 0111 (7 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # -> Binário: 0b111 | Decimal: 7
    ```

* **'`^`' (XOR)**: Retorna 1 para cada posição de bit em que apenas um dos operandos tem um bit 1.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x ^ y # 0110 (6 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # -> Binário: 0b110 | Decimal: 6
    ```

* **'`<<`' (Deslocamento à Esquerda)**: Move os bits dos números para a esquerda.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x << y # 101000 (40 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # -> Binário: 0b101000 | Decimal: 40
    ```

* **'`>>`' (Deslocamento à Direita)**: Move os bits dos números para a direta.

    ``` py
    # Operação Bitwise
    x = 5 # 0101 em binário
    y = 3 # 0011 em binário
    resultado = x >> y # 0000 (0 em decimal)

    # Imprime o resultado da operação
    print(f'Binário: {bin(resultado)} | Decimal: {resultado}')
    # -> Binário: 0b0 | Decimal: 0
    ```

### Operadores de Atribuição

O operador de atribuição mais comum é **`=`**, mas também há outros operadores que realizam uma operação e armazenam o resultado na variável.

**Os operadores de atribuição são:**

* **'`=`'**: Atribui o valor à variavel.
* **'`+=`'**: Soma um valor à variável.

    ``` py
    x = 5
    x += 2
    print(x) # -> 7
    ```

* **'`-=`'**: Subtrai um valor da variável.

    ``` py
    x = 5
    x -= 2
    print(x) # -> 3
    ```

* **'`*=`'**: Multiplica a variável por um valor.

    ``` py
    x = 5
    x *= 2
    print(x) # -> 10
    ```

* **'`/=`'**: Divide a variável por um valor.

    ``` py
    x = 5
    x /= 2
    print(x) # -> 2.5
    ```

* **'`//=`'**: Calcula a divisão inteira da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x //= 2
    print(x) # -> 2
    ```

* **'`%=`'**: Calcula o resto da divisão da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x %= 2
    print(x) # -> 1
    ```

* **'`**=`'**: Calcula a potência da variável pelo valor e atribui o resultado à variável.

    ``` py
    x = 5
    x **= 2
    print(x) # -> 25
    ```

* **'`&=`'**: Realiza a operação bit a bit AND com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x &= 3
    print(x) # -> 1
    ```

* **'`|=`'**: Realiza a operação bit a bit OR com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x |= 3
    print(x) # -> 7
    ```

* **'`^=`'**: Realiza a operação bit a bit XOR com a variável e o valor, e então atribui o resultado à variável.

    ``` py
    x = 5
    x ^= 3
    print(x) # -> 6
    ```

* **'`<<=`'**: Desloca os bits da variável para a esquerda na mesma quantidade de vezes do valor.

    ``` py
    x = 5
    x <<= 3
    print(x) # -> 40
    ```

* **'`>>=`'**: Desloca os bits da variável para a direita na mesma quantidade do valor.

    ``` py
    x = 5
    x >>= 3
    print(x) # -> 0
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
print(languages) # -> ('JavaScript', 'PHP', 'Python')
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
print(tupla) # -> (0, 2, 4, 6, 8, 10)
```

### Acesso aos Elementos de uma Tupla

Cada elemento da tupla é numerado com índices começando do 0, podendo ser acessados por notação de colchetes.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python')
print(languages[0]) # -> JavaScript
print(languages[1]) # -> PHP
print(languages[2]) # -> Python
```

Índices negativos correspondem aos elementos do final, por exemplo: `-1` corresponde ao último elemento, `-2`, corresponde ao penúltimo elemento, etc.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python')
print(languages[-3]) # -> JavaScript
print(languages[-2]) # -> PHP
print(languages[-1]) # -> Python
```

### Fatiamento de Tuplas

O fatiamento de tuplas funciona da mesma maneira que em strings e listas.

**Exemplo:**

``` py
tupla = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
print(tupla[3:6]) # -> (4, 5, 6)
```

Também é possível fatiar pulando elementos com `inicio:fim:saltos`.

**Exemplo:**

``` py
tupla = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
print(tupla[1:8:2]) # -> (2, 4, 6, 8)
```

### Ordenar Tupla para Impressão

Mesmo que as tuplas sejam imutáveis, é possível organizá-las numericamente ou alfabeticamente para impressão utilizando a função `sorted()`.

**Exemplo:**

``` py
numeros = (2, 4, 1, 5, 3)
letras = ('c', 'a', 'e', 'b', 'd')

print(sorted(numeros)) # -> [1, 2, 3, 4, 5]
print(sorted(letras)) # -> ['a', 'b', 'c', 'd', 'e']
```

> **NOTA:** A função `sorted()` retorna uma lista ao invés de uma nova tupla.

Para organizá-las ao contrários, define `True` para o parâmetro **`reverse`**.

**Exemplo:**

``` py
numeros = (2, 4, 1, 5, 3)
letras = ('c', 'a', 'e', 'b', 'd')

print(sorted(numeros, reverse=True)) # -> [5, 4, 3, 2, 1]
print(sorted(letras, reverse=True)) # -> ['e', 'd', 'c', 'b', 'a']
```

### Desempacotar Tupla

É chamado de ***unpacking*** a ação de atruibuir os elementos de uma tupla ou lista à variáveis.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python', 'Ruby')
a, b, c, d = languages
print(a) # -> JavaScript
print(b) # -> PHP
print(c) # -> Python
print(d) # -> Ruby
```

Se definido **`*`** no início do nome de uma das variáveis, ela será uma lista com os elementos que não têm variáveis definidas.

**Exemplo:**

``` py
languages = ('JavaScript', 'PHP', 'Python', 'Ruby')
a, *b, c = languages
print(a) # -> JavaScript
print(b) # -> ['PHP', 'Python']
print(c) # -> Ruby
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
print(languages) # -> ['JavaScript', 'PHP', 'Python']
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
print(lista) # -> [0, 2, 4, 6, 8, 10]
```

### Acesso aos Elementos de uma Lista

Assim como nas tuplas, os elementos nas listas são acessados por notação de colchetes por meio de seus índices numerados.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python']
print(languages[0]) # -> JavaScript
print(languages[1]) # -> PHP
print(languages[2]) # -> Python
```

Índices negativos, assim como em tuplas, referenciam os elementos do final da lista.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python']
print(languages[-3]) # -> JavaScript
print(languages[-2]) # -> PHP
print(languages[-1]) # -> Python
```

### Operador `del` para Remover Elementos em Listas

Com o operador **`del`** é possível remover um elemento de uma lista a partir de seu índice.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5]
del lista[2]
print(lista) # -> [1, 2, 4, 5]
```

### Funções `max()` e `min()` em Listas

As funções `max()` e `min()`, quando recebem listas como argumento, retornam o maior e menor valor dessa lista, respectivamente.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5]
maior = max(lista)
menor = min(lista)

print(maior) # -> 5
print(menor) # -> 1
```

### Fatiamento de Listas

O fatiamento de listas funciona da mesma maneira que em strings e tuplas.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(lista[3:6]) # -> [4, 5, 6]
```

Também é possível fatiar pulando elementos com `inicio:fim:saltos`.

**Exemplo:**

``` py
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(lista[1:8:2]) # -> [2, 4, 6, 8]
```

### Desempacotar Lista

Assim como as tuplas, é possível atribuir os elementos de uma lista à variáveis.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
a, b, c, d = languages
print(a) # -> JavaScript
print(b) # -> PHP
print(c) # -> Python
print(d) # -> Ruby
```

**Exemplo com `*`:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
a, *b, c = languages
print(a) # -> JavaScript
print(b) # -> ['PHP', 'Python']
print(c) # -> Ruby
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

print(new_list) # -> ['PHP', 'Python']
```

Com uma compreensão de lista, é possível fazer exatamente o mesmo que no exemplo acima, porém de maneira mais curta.

**Exemplo:**

``` py
languages = ['JavaScript', 'PHP', 'Python', 'Ruby']
new_list = [i for i in languages if "P" in i]

print(new_list) # -> ['PHP', 'Python']
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
    print(lista) # -> [1, 2, 3, 4, 5]
    ```

* **'`insert()`'**: Insere um elemento dentro de `self` em índice específico.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.insert(2, 10)
    print(lista) # -> [1, 2, 10, 3, 4, 5]
    ```

* **'`remove()`'**: Remove um elemento de `self` pelo valor.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.remove(3)
    print(lista) # -> [1, 2, 4, 5]
    ```

    Este método remove apenas o primeiro elemento com esse valor.

    ``` py
    lista = [3, 1, 2, 3, 4, 5]
    lista.remove(3)
    print(lista) # -> [1, 2, 3, 4, 5]
    ```

* **'`pop()`'**: Remove o elemento em um dado índice.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.pop(2)
    print(lista) # -> [1, 2, 4, 5]
    ```

    Se não passado um argumento, será removido o último elemento da lista.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.pop()
    print(lista) # -> [1, 2, 3, 4]
    ```

* **'`clear()`'**: Limpa `self`, tornando-a uma lista vazia.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.clear()
    print(lista) # -> []
    ```

* **'`sort()`'**: Organiza `self` numericamente ou alfabeticamente.

    ``` py
    lista = [3, 1, 2, 5, 4]
    lista.sort()
    print(lista) # -> [1, 2, 3, 4, 5]
    ```

    Para organizar em ordem contrária, defina o parâmetro `reverse` para `True`.

    ``` py
    lista = [3, 1, 2, 5, 4]
    lista.sort(reverse=True)
    print(lista) # -> [5, 4, 3, 2, 1]
    ```

* **'`reverse()`'**: Inverte a ordem dos elementos em `self`.

    ``` py
    lista = [1, 2, 3, 4, 5]
    lista.reverse()
    print(lista) # -> [5, 4, 3, 2, 1]
    ```

* **'`index()`'**: Retorna o índice de um dado elemento de `self`.

    ``` py
    lista = ['Python', 'Ruby', 'Go']
    indice = lista.index('Ruby')
    print(indice) # -> 1
    ```

* **'`copy()`'**: Retorna `self` como uma cópia.

    ``` py
    # Declara uma lista
    lista = [1, 2, 3, 4, 5]

    # Cria uma cópia de `lista` e altera o primeiro elemento
    novaLista = lista.copy()
    novaLista[0] = 10

    # Imprime as listas
    print(lista) # -> [1, 2, 3, 4, 5]
    print(novaLista) # -> [10, 2, 3, 4, 5]
    ```

* **'`extend()`'**: Atribui a `self` os elementos de uma dada lista ou tupla.

    ``` py
    lista1 = [1, 2, 3]
    lista2 = [4, 5, 6]

    lista1.extend(lista2)
    print(lista1) # -> [1, 2, 3, 4, 5, 6]
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
# -> 0 1 2 3 4
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
# -> 0 2 4 6 8 10
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
# -> 2 4 6 8 10
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
# -> 0 1 2 3 4 5 FIM!
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
# -> 1 2 3 4 5
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
# -> 1 2 3 4 5 FIM!
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
# -> 1 2 3 4 5
```

No exemplo acima, `while True` cria um loop infinito que só pode ser parado com `break`. O loop é interrompido apenas quando o contador chega a 5.

**Exemplo com `continue`:**

``` py
for c in range(11):
    if c % 2 != 0:
        continue
    print(c, end=' ')
print()
# -> 0 2 4 6 8 10
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
print(my_set) # -> {True, 2.5, 3, 'Olá'}
```

Perceba que o valor `1` não existe, já que antes dele foi declarado `True`.

### Tipos de Dados em um Conjunto

Um **set** permite qualquer tipo de dado, com exceção de tipos especiais, como listas, tuplas, dicionários e outros sets.

### Comprimento de um Conjunto

Para obter o comprimento de um conjunto, é usada a função **`len()`**.

**Exemplo:**

``` py
my_set = {'Olá', 3, 2.5, True}
print(len(my_set)) # -> 4
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
# -> {True, 2.5, 3, 'Olá, Python!', 'Olá'}
```

Há também o método **`update()`**, que permite **atualizar um set com outro set, tupla ou lista**.

**Exemplo:**

``` py
set1 = {3, 'Oi', False}
set2 = {True, 2.5, 'Olá'}

set1.update(set2)

print(set1)
# -> {False, True, 2.5, 3, 'Olá', 'Oi'}
```

### Remover Itens de um Conjunto

Para remover um itens de um set, é usado o método **`remove()`** ou **`discard()`**.

**Exemplo:**

``` py
my_set = {3, 'Oi', False, 2.5, True}

my_set.remove('Oi')
my_set.discard(False)

print(my_set)
# -> {True, 2.5, 3}
```

> **NOTA:** Será retornado um erro caso o argumento do método `remove()` não existir dentro do set. Por outro lado, o método `discard()` ignora caso o itens não exista dentro do set, prosseguindo como se tivesse excluído o item.

O método **`pop()`** irá excluir um item aleatório. Já que sets não possuem uma ordem definida, não há como esperar qual item será excluído.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

item = my_set.pop()

print(item)   # -> False
print(my_set) # -> {True, 2.5, 3, 'Oi'}
```

O método **`clear()`** irá excluir todos os itens do set.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

my_set.clear()

print(my_set) # -> set()
```

A palavra-chave **`del`** exclui um set por completo.

**Exemplo:**

``` py
my_set = {'Oi', 3, False, 2.5, True}

del my_set

# Ocorrerá um erro, já que `my_set` não existe mais
print(my_set) # -> set()
```

### Unir Coleções

O método **`union()`** retorna um novo set, que é a junção de `self` com um dado set, lista ou tupla.

**Exemplo:**

``` py
set1 = {'Oi', 3, 2.5, True}
set2 = {5, 2, False, 'Olá'}
set3 = set1.union(set2)

print(set3)
# -> {False, True, 2.5, 3, 'Oi', 2, 5, 'Olá'}
```

### Itens Duplicados em um Conjunto

O método **`intersection()`** retorna os itens que existem em ambos os sets.

**Exemplo:**

``` py
set1 = {'Oi', 5, 3, 2.5, True}
set2 = {5, 2, False, 'Olá', True}
set3 = set1.intersection(set2)

print(set3)
# -> {True, 5}
```

Para manter apenas os itens que não são duplicados, há o método **`symmetric_difference()`**.

**Exemplo:**

``` py
set1 = {'Oi', 5, 3, 2.5, True}
set2 = {5, 2, False, 'Olá', True}
set3 = set1.symmetric_difference(set2)

print(set3)
# -> {False, 2, 2.5, 3, 'Oi', 'Olá'}
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
print(dicionario['nome'])   # -> Luana
print(dicionario['idade'])  # -> 22
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
print(dicionario) # -> {'nome': 'John', 'idade': 32}
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
print(dicionario) # -> {'nome': 'Luana', 'idade': 22, 'sexo': 'feminino'}
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
print(dicionario) # -> {'nome': 'Luana'}
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
print(item_excluido) # -> Luana
print(dicionario) # -> {'idade': 22}
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
    print(dicionario)       # -> {'nome': 'Luana', 'idade': 22}
    print(copiaDicionario)  # -> {'nome': 'John', 'idade': '32'}
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
    print(dicionario) # -> {}
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
    print(chaves) # -> dict_keys(['nome', 'idade'])
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
    print(valores) # -> dict_values(['Luana', 22])
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
    print(itens) # -> dict_items([('nome', 'Luana'), ('idade', 22)])
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
ola_mundo() # -> Olá, Mundo!
```

**Exemplo com parâmetros:**

``` py
# Função que imprime uma saudação
def saudacao(nome):
    print(f'Olá, {nome}!')

# Chama a função
saudacao('Mundo') # -> Olá, Mundo!
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
soma(y=2, x=5) # -> 7
soma(x=1, y=5) # -> 6
soma(2, y=3)   # -> 5
```

Definir **`/`** como argumento impede essa atribuição por parâmetro para todos os parâmetros antes de `/`.

**Exemplo:**

``` py
def soma(x, y, /):
    print(x + y)

soma(5, 2) # -> 7
```

No exemplo acima, ocorrerá um erro se os argumentos forem passados por palavra-chave, como `soma(y = 2, x = 5)`.

Por outro lado, definir **`*`** como parâmetro irá permitir apenas que os argumentos sejam passados por palavra-chave. Isso vale para todos os argumentos após `*`.

**Exemplo:**

``` py
def soma(*, x, y):
    print(x + y)

soma(y = 5, x = 2) # -> 7
```

No exemplo acima, ocorrerá um erro se os argumentos forem passados por posição, como `soma(5, 2)`.

É possível combinar `*` e `/` em uma mesma função, definindo os parâmetros que receberão argumentos por posição e os parâmetros que receberão os argumentos por palavra-chave.

**Exemplo:**

``` py
def soma(x, y, /, *, z):
    print(x + y + z)

soma(5, 2, z = 3) # -> 10
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
soma(2, 4)          # -> 6
soma(5)             # -> 5
soma(1, 2, 3, 4, 5) # -> 15
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
mult(5, 2, 4)           # -> 30
mult(2, 5)              # -> 10
mult(0, 1, 2, 3, 4, 5)  # -> 0
```

#### Argumentos de Palavras-chave

Indicar dois asteriscos no início de um parâmetro, tornará ele um dicionário, e assim seus argumentos podem ser passados de maneira variádica.

**Exemplo:**

``` py
def my_function(**kwargs):
    print(kwargs)

my_function(name='Luana', idade='23')
# -> {'name': 'Luana', 'idade': '23'}
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
soma(5, 2)  # -> 7
soma(3)     # -> 8
soma(0)     # -> 5
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
print(resultado) # -> 10
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
minha_funcao() # -> Olá, Mundo!
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

#### Variável em Função Externa

Usar a palavra-chave **`nonlocal`** em uma variável fará com que ela pertença à função externa à função chamada.

**Exemplo:**

``` py
def foo():
    str = "Hello, World!"
    def bar():
        nonlocal str
        str = "Hello, Python!"
    bar()
    return str

print(foo()) # -> Hello, Python!
```

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

### Lambdas

Uma lambda é uma função anônima pequena. Uma lambda pode receber vários argumentos, porém é escrita com apenas uma expressão.

**Sintaxe:**

``` py
lambda argumentos : expressao
```

**Exemplo:**

``` py
my_lambda = lambda x, y : x + y
print(my_lambda(5, 2))
# -> 7
```

Lambdas podem ser retornadas em funções.

**Exemplo:**

``` py
def my_function(num):
    return lambda x : x * num

my_lambda = my_function(5)
print(my_lambda(3))
# -> 15
```

No exemplo acima, a função `my_function()` retorna uma lambda que retorna um dado valor multiplicado por 5.

## Classes

Uma classe é basicamente um modelo para um objeto.

**Sintaxe:**

``` py
class MyClass:
    # Declarações da classe
```

> **NOTA:** Para nomear as classes, geralmente é usado CamelCase.

**Exemplo:**

``` py
class MyClass:
    x = 5
    y = 2

obj = MyClass
print(MyClass.x + MyClass.y)
# -> 7
```

No exemplo acima, `obj` é uma instância da classe `MyClass`. Essa instância tem acesso às variáveis `x` e `y` declaradas na classe, e acessa elas por meio de notação de ponto.

### Métodos

Métodos são funções que geralmente executam no contexto de uma classe.

Para declarar um método, basta declarar uma função dentro de uma classe.

**Exemplo:**

``` py
# Classe que possui métodos
class MyClass:
    # Método que retorna a soma de dois números
    def sum(self, x, y):
        return x + y

    # Método que retorna o dobro de um número
    def double(self, x):
        return x * 2

# Cria uma instância da classe
my_instance = MyClass()

# Imprime o resultado dos métodos
print(my_instance.sum(5, 2)) # -> 7
print(my_instance.double(9)) # -> 18
```

Como primeiro parâmetro, é definido `self`, que referência à própria classe.

Se `self` não for definido como parâmetro, o método se torna **estático**, podendo ser acessado diretamente pela classe, e não por uma instância dela. Isso significa que o método não pode acessar os atributos da classe.

**Exemplo:**

``` py
# Classe que possui métodos
class MyClass:
    # Método que retorna a soma de dois números
    def sum(x, y):
        return x + y

    # Método que retorna o dobro de um número
    def double(x):
        return x * 2

# Imprime o resultado dos métodos
print(MyClass.sum(5, 2)) # -> 7
print(MyClass.double(9)) # -> 18
```

Perceba que não há uma instância da classe. Os métodos são simplesmente acessados diretamente pela classe.

### Atributos

Os atributos de um objeto são valores definidos assim que eles são criados. Esses valores são usados como argumentos em métodos da classe e podem inclusive, ser acessados de fora dela por meio de notação de ponto.

os atributos são definidas assim que uma instância é criada quando o método especial **`__init()__`** está definido na classe.

Quando **`__init__()`** é definido em uma classe, é obrigatório passar como argumentos os parâmetros desse método na criação de instâncias da classe.

**Exemplo:**

``` py
# Classe que possui métodos
class MyClass:
    # Adquire os atributos
    def __init__(self, x, y):
        self.x = x
        self.y = y

    # Soma o valor dos atributos
    def sum(self):
        return self.x + self.y

    # Multiplica o valor dos atributos
    def mult(self):
        return self.x * self.y

# Instância da classe
obj = MyClass(5, 2)

# Imprime o resultado dos métodos
print(obj.sum())    # -> 7
print(obj.mult())   # -> 10
```

os atributos de uma classe podem ser alteradas.

**Exemplo:**

``` py
# Classe que possui métodos
class MyClass:
    # Adquire os atributos
    def __init__(self, x, y):
        self.x = x
        self.y = y

# Instância da classe
obj = MyClass(5, 2)

# Imprime os atributos antes de alterá-las
print(obj.x) # -> 5
print(obj.y) # -> 2

# Altera os atributos
obj.x = 10
obj.y = 23

# Imprime os atributos após as alterações
print(obj.x) # -> 10
print(obj.y) # -> 23
```

### Herança

É possível que uma classe herde todos os métodos e propriedades de outra classe, isso é chamado de **herança**.

**Sintaxe:**

``` py
class ClassePai:
    # Conteúdo da classe pai

class ClasseFilha(ClassePai):
    # Conteúdo da classe filha
```

**Exemplo:**

``` py
# Classe pai
class ClassePai:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

class ClasseFilha(ClassePai):
    pass

obj = ClasseFilha(5, 2)
print(obj.soma()) # -> 7
```

Os métodos da classe filha têm prioridade, então se houver uma duplicidade de nomes, será o método da filha que irá executar.

**Exemplo:**

``` py
# Classe pai
class ClassePai:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

class ClasseFilha(ClassePai):
    def soma(self):
        return self.x - self.y

obj = ClasseFilha(5, 2)
print(obj.soma()) # -> 3
```

#### Função `super()`

A função **`super()`** faz com que a classe filha herde todos os métodos e propriedades da classe pai ao definir o método `__init__()` na classe filha.

**Exemplo:**

``` py
# Classe pai
class ClassePai:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

class ClasseFilha(ClassePai):
    def __init__(self, x, y):
        super().__init__(x, y)

obj = ClasseFilha(5, 2)
print(obj.soma()) # -> 7
```

Junto às propriedades já definidas pela classe pai, pode-se definir novas propriedades:

**Exemplo:**

``` py
# Classe pai
class ClassePai:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

class ClasseFilha(ClassePai):
    def __init__(self, x, y):
        super().__init__(x, y)
        self.z = 13

obj = ClasseFilha(5, 2)
print(obj.soma()) # -> 7
print(obj.z)      # -> 13
```

Além disso, outras propriedades podem ser diretamente definidas como parâmetros de `__init__()`.

**Exemplo:**

``` py
# Classe pai
class ClassePai:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

class ClasseFilha(ClassePai):
    def __init__(self, x, y, z):
        super().__init__(x, y)
        self.z = z

obj = ClasseFilha(5, 2, 22)
print(obj.soma()) # -> 7
print(obj.z)      # -> 22
```

### Criação de Iterador

É possível criar um iterador criando uma classe com os métodos **`__iter__()`** e **`__next__()`**.

O método **`__iter__()`** é similar ao método `__init__()`, porém ele deve sempre retornar o próprio objeto iterador.

Já o método **`__next__()`** é usado para dar sequência à iteração, sempre retornando o próximo elemento dela.

**Exemplo:**

``` py
class Foo:
    def __iter__(self):
        self.x = 1
        return self

    def __next__(self):
        x = self.x
        self.x += 1
        return x

obj = Foo()
it = iter(obj)

print(next(it)) # -> 1
print(next(it)) # -> 2
print(next(it)) # -> 3
print(next(it)) # -> 4
print(next(it)) # -> 5
```

#### Interromper a Iteração

A iteração pode ser interrompida chamando a exceção **`StopIteration`** com a palavra-chave **`raise`**.

**Exemplo:**

``` py
class Foo:
    def __init__(self, end):
        self.end = end

    def __iter__(self):
        self.x = 1
        return self

    def __next__(self):
        x = self.x
        if x >= self.end:
            raise StopIteration
        self.x += 1
        return x

obj = Foo(6)
it = iter(obj)

for n in it:
    print(n, end=' ') # -> 1 2 3 4 5
```

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
print(raiz_quadrada(25))  # -> 5.0
print(raiz_quadrada(0))   # -> 0.0
print(raiz_quadrada('4')) # -> <class 'TypeError'>
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
print(divisao(5, 2))  # -> 2.5
print(divisao(3, 0))  # -> ERRO: Não é possível dividir por 0
print(divisao(9, -1)) # -> -9.0
```

### Chamar uma Exceção

A palavra-chave **`raise`** chama uma exceção imediatamente.

**Exemplo:**

``` py
x = int(input('Digite um número positivo: '))
if x <= 0:
    raise Exception('Número digitado não é positivo')
print(x) # Imprime o número digitado
```

## Módulos

Um módulo é como uma biblioteca de código, onde você pode importá-la quando quiser e usar suas ferramentas.

Qualquer arquivo com a extensão **`.py`** pode ser um módulo, e para importá-lo, é necessário usar a declaração **`import nome_do_modulo`**.

**Exemplo:**

``` py
# Arquivo modulo.py
def helloWorld():
    return 'Hello, World!'
```

``` py
# Arquivo principal
import modulo

print(modulo.helloWorld()) # -> Hello, World!
```

Além de funções, um módulo pode armazenar variáveis e classes.

**Exemplo:**

``` py
# Arquivo modulo.py
class Foo:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

    def mult(self):
        return self.x * self.y

str = 'Hello, World!'
```

``` py
# Arquivo principal
import modulo

obj = modulo.Foo(5, 2)
print(obj.soma()) # -> 7
print(obj.mult()) # -> 10
print(modulo.str) # -> Hello, World!
```

### Alias para Módulo

Com a palavra-chave **`as`**, é possível criar um alias para o módulo importado.

**Sintaxe:**

``` py
import modulo as alias
```

**Exemplo:**

``` py
import modulo as m

str = m.helloWorld()
print(str) # -> Hello, World!
```

### Listar Ferramentas de um Módulo

A função **`dir()`** retorna todos os elementos de um

**Exemplo:**

``` py
# Arquivo modulo.py
class Foo:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

    def mult(self):
        return self.x * self.y

str = 'Hello, World!'
linguagens = ['Python', 'JavaScript', 'Go', 'Ruby', 'Java', 'PHP', 'C']
```

``` py
# Arquivo principal
import modulo

for x in dir(modulo):
    print(x)

# Output:
# Foo
# __builtins__
# __cached__
# __doc__
# __file__
# __loader__
# __name__
# __package__
# __spec__
# linguagens
# str
```

### Importar Parte de um Módulo

Utilizando a palavra-chave **`from`**, é possível importar somente uma parte de um módulo.

**Sintaxe:**

``` py
from modulo import parte
```

**Exemplo:**

``` py
# Arquivo modulo.py
class Foo:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def soma(self):
        return self.x + self.y

    def mult(self):
        return self.x * self.y

str = 'Hello, World!'
linguagens = ['Python', 'JavaScript', 'Go', 'Ruby', 'Java', 'PHP', 'C']
```

``` py
# Arquivo principal
from modulo import str

print(str) # -> Hello, World!
```

Perceba que desta forma não é necessário especificar o módulo ao qual a variável/objeto pertence.

Se houver mais de um objeto/variável para importar de um módulo, você pode especificá-los separando-os com vírgula.

**Exemplo:**

``` py
# Arquivo principal
from modulo import str, linguagens

print(str) # -> Hello, World!
for x in linguagens:
    print(x, end=' ')
# -> Python JavaScript Go Ruby Java PHP C
```

## Data e Hora

O módulo **`datetime`** fornece diversos objetos para trabalhar com datas e horas.

**Exemplo:**

``` py
import datetime

horaAtual = datetime.datetime.now()
print(horaAtual) # Imprime a hora atual
```

Para **criar uma data**, é necessário criar um objeto de data.

**Sintaxe:**

``` py
data = datetime.datetime(ano, mes, dia, hora, minuto, seg, milissegundo, timezone)
```

**Exemplo:**

``` py
import datetime

d = datetime.datetime(2007, 2, 4, 0, 5, 0, 0)
print(d) # -> 2007-02-04 00:05:00
```

Para **criar apenas uma hora**, é criado um objeto **`time`**.

**Sintaxe:**

``` py
hora = datetime.time(hora, minuto, segundo, milissegundo, timezone)
```

**Exemplo:**

``` py
import datetime

t = datetime.time(17, 22, 13)
print(t) # -> 17:22:13
```

### Formatação de Datas em Strings

O método **`strftime()`** formata objetos de data em strings legíveis. Ele possui apenas um parâmetro, que é o formato em que a string será retornada.

**Exemplo:**

``` py
import datetime

d = datetime.datetime(2022, 10, 5)
print(d) # -> 2022-10-05 12:30:00

print(f'Dia da semana: {d.strftime('%A')}') # -> Dia da semana: Wednesday
print(f'Dia do mês: {d.strftime('%d')}') # -> Dia do mês: 05
print(f'Mês: {d.strftime('%B')}') # -> Mês: October
print(f'Ano: {d.strftime('%Y')}') # -> Ano: 2022
```

**Os formatos são:**

* **'`%a`'**: Dia da semana (curto).
* **'`%A`'**: Dia da semana (completo).
* **'`%w`'**: Dia da semana como um número (0-6, onde 0 é domingo).
* **'`%d`'**: Dia do mês (01-31).
* **'`%b`'**: Nome do mês (curto).
* **'`%B`'**: Nome do mês (completo).
* **'`%m`'**: Mês como um número (01-12).
* **'`%y`'**: Ano (curto).
* **'`%Y`'**: Ano (completo).
* **'`%H`'**: Hora (00-23).
* **'`%I`'**: Hora (00-12).
* **'`%p`'**: AM/PM.
* **'`%M`'**: Minuto (00-59).
* **'`%S`'**: Segundo (00-59).
* **'`%f`'**: Microssegundo (000000-999999).
* **'`%z`'**: UTC offset.
* **'`%Z`'**: Timezone.
* **'`%j`'**: Dia do ano (001-366).
* **'`%U`'**: Dia da semana do ano, onde domingo é o primeiro dia da semana (00-53).
* **'`%W`'**: Dia da semana do ano, onde segunda-feira é o primeiro dia da semana (00-53).
* **'`%c`'**: Versão local da data e hora.
* **'`%C`'**: Século.
* **'`%x`'**: Versão local da data.
* **'`%X`'**: Versão local da hora.
* **'`%G`'**: ISO 8601 ano.
* **'`%u`'**: ISO 8601 dia da semana (1-7).
* **'`%V`'**: ISO 8601 número da semana (01-53).
* **'`%%`'**: O caractere "%".

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

### Excluir Arquivos

Para excluir um arquivo, é usada a função **`os.remove()`**.

**Exemplo:**

``` py
import os

os.remove('text.txt')
```

Antes da exclusão, é importante verificar se o arquivo existe com **`os.path.exists()`**.

**Exemplo:**

``` py
import os

if os.path.exists('text.txt'):
    os.remove('text.txt')
else:
    raise Exception('Arquivo não existe')
```

> **Exclusão de pastas:** Excluir uma pasta é exatamente como excluir um arquivo, porém usando a função **`os.rmdir()`**. É possível apenas excluir pastas vazias.

## JSON

Python possui o pacote **`json`** para trabalhar com dados JSON.

**Exemplo:**

``` py
import json

# Dados em JSON
j = '{ "nome": "Matheus", "idade": 17 }'

# Extrai os dados em JSON
s = json.loads(j)

# Imprime os dados como um dicionário
print(s['nome'])  #  -> Matheus
print(s['idade']) #  -> 17
```

### Objetos em Python para JSON

Para converter os objetos em JSON, é usada a função **`dumps()`**.

**Exemplo:**

``` py
import json

# Dicionário
d = {'nome': 'Matheus', 'idade': 17}

# Converte para JSON
s = json.dumps(d)

# Imprime os dados
print(s) # -> {"nome": "Matheus", "idade": 17}
```

Essa função pode receber também o parâmetro `indent`, que define a indentação na formatação.

**Exemplo:**

``` py
import json

# Dicionário
d = {'nome': 'Matheus', 'idade': 17}

# Converte para JSON
s = json.dumps(d, indent=4)

# Imprime os dados
print(s)
# Output:
# {
#     "nome": "Matheus",
#     "idade": 17
# }
```

Além da identação, é possível também configurar os separadores passando um argumento para o parâmetro **`separators`**. Esse parâmetro deve receber uma tupla ou lista, onde o primeiro valor é o separador e o segundo é o separador da chave para o valor.

**Exemplo:**

``` py
import json

# Dicionário
d = {'nome': 'Matheus', 'idade': 17}

# Converte para JSON
s = json.dumps(d, indent=4, separators=('; ', ' -> '))

# Imprime os dados
print(s)
# Output:
# {
#     "nome" -> "Matheus";
#     "idade" -> 17
# }
```

Há também o parâmetro **`sort_keys`**. Ele recebe um valor booleano que, por padrão, é `False`, mas se `True`, ele ordena os valores.

**Exemplo:**

``` py
import json

# Dicionário
d = {'nome': 'Matheus', 'idade': 17, 'sexo': 'masculino', 'peso': 68.7}

# Converte para JSON
s = json.dumps(d, indent=4, sort_keys=True)

# Imprime os dados
print(s)
# Output:
# {
#     "idade": 17,
#     "nome": "Matheus",
#     "peso": 68.7,
#     "sexo": "masculino"
# }
```

## Expressões Regulares

O pacote **`re`** é usado para trabalhar com expressões regulares em Python.

### Função `re.findall()`

A função **`findall()`** retorna uma lista com todas as ocorrências

**Exemplo:**

``` py
import re

s = 'Ruby Python Go Python Ruby Java Python PHP'
regex = re.findall('Python', s)
print(regex) # -> ['Python', 'Python', 'Python']
```

### Função `re.search()`

A função **`re.search()`** retorna um objeto **`Match`** se houver alguma correspondência na string.

**Exemplo:**

``` py
import re

s = 'Hello, World!'
regex = re.search('World', s)
print(regex) # -> <re.Match object; span=(7, 12), match='World'>
```

Se não houver ocorrências, é retornado `None`.

### Função `re.split()`

A função **`split()`** retorna uma lista que contém as separações feitas na string com base em um padrão.

**Exemplo:**

``` py
import re

s = 'abcde fghij klmno pqrst'
resultado = re.split('\s', s)
print(resultado) # -> ['abcde', 'fghij', 'klmno', 'pqrst']
```

Se desejar, você pode controlar o número de ocorrências retornadas passando um terceiro argumento.

**Exemplo:**

``` py
import re

s = 'abcde fghij klmno pqrst'
resultado = re.split('\s', s, 3)
print(resultado) # -> ['abcde', 'fghij', 'klmno']
```

### Função `re.sub()`

A função **`sub()`** substitui as ocorrências.

**Exemplo:**

``` py
import re

s = 'abcde fghij klmno pqrst'
resultado = re.sub('\s', '-', s)
print(resultado) # -> abcde-fghij-klmno-pqrst
```

O quarto parâmetro recebe o número de substituições que serão feitas.

**Exemplo:**

``` py
import re

s = 'abcde fghij klmno pqrst'
resultado = re.sub('\s', '-', s, 2)
print(resultado) # -> abcde-fghij-klmno pqrst
```

### Metacaracteres

* **'`[]`'**: Conjunto de caracteres.
* **'`.`'**: Qualquer caractere que não seja uma nova linha.
* **'`^`'**: Começa com.
* **'`$`'**: Termina com.
* **'`*`'**: Zero ou mais ocorrências.
* **'`+`'**: Uma ou mais ocorrências.
* **'`?`'**: Zero ou uma ocorrência.
* **'`{}`'**: O número específico de ocorrências.
* **'`|`'**: Um ou outro.
* **'`()`'**: Captura e grupo.
* **'`\`'**: Usado para escape de caracteres especiais.

### Sequências Especiais

* **'`\A`'**: Se o caractere especificado está no começo da string.
* **'`\Z`'**: Corresponde se o caractere especificado está no fim da string.
* **'`\b`'**: Corresponde se o caractere especificado está no início ou no fim de uma palavra.
* **'`\B`'**: Corresponde se o caractere especificado está presente, mas não no início e no fim da palavra.
* **'`\d`'**: Corresponde se a string contém números (0-9).
* **'`\D`'**: Corresponde se a string não contém números.
* **'`\s`'**: Corresponde se a string contém um caractere de espaço em branco.
* **'`\S`'**: Corresponde se a string não contém um caractere de espaço em branco.
* **'`\w`'**: Corresponde se a string contém algum caractere de palavra, algum número ou um *underline* (a-Z, 0-9, _).
* **'`\W`'**: Corresponde se a string não possui nenhum caractere de palavra, algum número ou *underline*.

### Conjunto de Caracteres

* **'`[xyz]`'**: Corresponde se x, y ou z estiver presente.
* **'`[a-z]`'**: Corresponde se o caractere estiver dentro do intervalo de a até z.
* **'`[a-zA-Z]`'**: Corresponde se o caractere estiver dentro do intervalo de a até z, tanto maiúsculas quanto minúsculas.
* **'`[^xyz]`'**: Corresponde a qualquer caractere que não seja x, y e z.
* **'`[0-9]`'**: Corresponde se for qualquer dígito entre 0 e 9.

### Objeto `Match`

Um objeto **`Match`** contém informações sobre a procura de uma ocorrência e o resultado.

**Exemplo:**

``` py
import re

s = 'Hello, World!'
m = re.search('World', s)
print(m) # -> <re.Match object; span=(7, 12), match='World'>
```

## Estilo de Texto no Terminal

Para imprimir mensagens coloridas no terminal é utilizado um código ANSI.

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
