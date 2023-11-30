# Markdown

## Headings (Títulos)

Os títulos em Markdown são escritos utilizando `#`. Existem até no máximo título nível 6.

**Exemplo:**

``` md
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

## Formatação de Texto

Podemos formatar para negrito e/ou itálico.

### Itálico

Tudo que estiver entre um `_`(underline) será formatado para *itálico*. O mesmo acontece se utilizar `*`(asterisco) para cercar uma palavra ou trecho.

**Exemplo:**

``` md
_Este texto está formatado em itálico_
*Este texto também está formatado em itálico*
```

### Negrito

O trecho que estiver cercado com `__` ou `**` será formatado em **negrito**.

``` md
__Este texto está em negrito__
**Este texto também está em negrito**
```

### Itálico e Negrito

Para que um trecho seja formatado tanto para *itálico* quanto para **negrito**, o mesmo deve ser envolto em `***`.

**Exemplo:**

``` md
***Texto***
```

Para fazer isso, você basicamente formata para negrito, e depois para itálico, ou ao contrário, não importa a forma que você faz isso (seja com `_`, ou seja com `*`).

## *Links*

Existem dois tipos de *links* em Markdown: ***inline link*** e ***reference link***.

### *Inline Link*

Usando colchetes `[]` e parênteses `()` é possível criar um *inline link*, onde o trecho que servirá como *link* ficará entre os colchetes, enquanto a URL ficará entre os parênteses.

**Exemplo:**

``` md
[Acesse o Google](www.google.com)
```

### *Reference Link*

Um *link* de referência é uma referência a outro local do documento.

``` md
[Acesse o Youtube][YouTube]
[Acesse o Google][Google]

[YouTube]: www.youtube.com
[Google]: www.google.com
```

Basicamente, as palavras-chaves `YouTube` e `Google` são referências para os seus respectivos *links*.

Caso um mesmo *link* seja usado mais de uma vez em um mesmo documento, esta é uma maneira inteligente de implementação de *links*, pois caso necessário alguma modificação na URL posteriormente, você pode modificá-la em uma única linha.

## Imagens

Adicionar imagens é igual a criar *links*, porém adicionando um ponto de exclamação `!` ao início. Após o ponto de exclamação, segue os colchetes e parênsetes `![texto_alternativo](link_da_imagem)`.

**Exemplo:**

``` md
![Gatinho](https://images.pexels.com/photos/3257811/pexels-photo-3257811.jpeg)
```

### Imagem de Referência

Uma imagem de referência é exatamente igual a um *link* de referência, só que para imagens.

**Sintaxe:**

``` md
[nome_de_referência]: url
```

## Citação de Bloco

Possui o objetivo de formatar um bloco para trazer a atenção do leitor.

Para criar uma citação de bloco, use o sinal de maior que (`>`) antes da citação.

**Exemplo:**

``` md
> "A vantagem de ter péssima memória é divertir-se muitas vezes com as mesmas coisas boas como se fosse a primeira vez. (Friedrich Nietzsche)"
```

## Listas

Existem dois tipos de listas: **listas desordenadas** e **listas ordenadas**.

### Listas Desordenadas

Para cada elemento da lista, é escrito um **`*`** no início.

**Exemplo:**

``` md
* Item 1
* Item 2
* Item 3
```

### Listas Ordenadas

Cada item de uma lista ordenada é criado a partir de um número seguido de um ponto, como **`1.`**.

**Exemplo:**

``` md
1. Item 1
1. Item 2
1. Item 3
```

3. Item 1
3. Item 2
3. Item 3

A numeração dos itens é feita automaticamente a partir do valor do primeiro item, ou seja, só o que importa é numerar corretamente o primeiro item.

> Recomendado numerar todos os itens com '`1.`' ao início.

### Aninhamento de Listas

Você pode aninhar uma lista dentro da outra, e a única regra a se lembrar é que os itens das listas mais de dentro devem ter uma espaço a mais (identação).

**Exemplo:**

``` md
* Pessoa 1
    * Homem
    * Professor
    * 28 anos

* Pessoa 2
    * Mulher
    * Médica
    * 23 anos

* Pessoa 3
    * Mulher
    * Advogada
    * 36 anos
```

### Parágrafos em Listas

É possível também escrever parágrafos em itens de listas

``` md
* Exemplo:

    Lorem ipsum, dolor sit amet consectetur adipisicing elit.

    * Sublista:

        Lorem ipsum, dolor sit amet consectetur adipisicing elit.
```

