# Headings (Títulos)

Os títulos em Markdown são escritos utilizando `#`. Podem ser escritos até seis, sendo que um equivale a título nível 1, e seis equivalem a um título de nível 6.

***Exemplo:***

```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

# Formatação de Texto

Podemos formatar para negrito e/ou itálico.

## Itálico

Tudo que estiver entre um `_`(underline) será formatado para *itálico*. O mesmo acontece se utilizar `*`(asterisco) para cercar uma palavra ou trecho.

***Exemplo:***

```
_Este texto está formatado em itálico_
*Este texto também está formatado em itálico*
```

## Negrito

O trecho que estiver cercado com `__` ou `**` será formatado em **negrito**.

```
__Este texto está em negrito__
**Este texto também está em negrito**
```

## Itálico e Negrito

Para que um trecho seja formatado tanto para *itálico* quanto para **negrito**, pode-se cercar o trecho com `***`.

***Exemplo:***

```
***Texto***
```

Para fazer isso, você basicamente formata para negrito, e depois para itálico, ou ao contrário, não importa a forma que você faz isso (seja com `_`, ou seja com `*`).

# *Links*

Existem dois tipos de *links* em Markdown: ***inline link*** e ***reference link***.

## *Inline Link*

Usando colchetes `[]` e parênteses `()` é possível criar um *inline link*, onde o trecho que servirá como *link* ficará entre os colchetes e a URL ficará entre os parênteses.

***Exemplo:***

```
[Acesse o Google](www.google.com)
```

## *Reference Link*

Um *link* de referência é uma referência a outro local do documento.

```
[Acesse o Youtube][YouTube]
[Acesse o Google][Google]

[YouTube]: www.youtube.com
[Google]: www.google.com
```

Basicamente, as palavras-chaves `YouTube` e `Google` são referências para os seus respectivos *links*.

Caso um mesmo *link* seja usado mais de uma vez em um mesmo documento, esta é uma maneira inteligente de implementação de *links*, pois caso necessário alguma modificação na URL posteriormente, você pode modificá-la em uma única linha.

# Imagens

Adicionar imagens é igual a criar *links*, porém adicionando um ponto de exclamação `!` ao início. Após o ponto de exclamação, segue os colchetes e parênsetes `![texto_alternativo](link_da_imagem)`.

***Exemplo:***

```
![Gatinho](https://images.pexels.com/photos/3257811/pexels-photo-3257811.jpeg)
```

## Imagem de Referência

Uma imagem de referência é exatamente igual a um *link* de referência.

***Sintaxe:***

```
[nome_de_referência]: url
```

# Citação de Bloco

Possui o objetivo de formatar um bloco para trazer a atenção do leitor.

Para criar uma citação de bloco, use o sinal de maior que `>` antes da citação.

***Exemplo:***

```
> "A vantagem de ter péssima memória é divertir-se muitas vezes com as mesmas coisas boas como se fosse a primeira vez. (Friedrich Nietzsche)"
```

# Listas

Existem dois tipos de listas: **listas desordenadas** e **listas ordenadas**.

## Lista Desordenada

Uma lista é criada a partir de seus itens, e para criar uma lista desordenada, escrevemos cada linha que é um item da lista com um asterisco no começo `*`.

***Exemplo:***

```
* Item 1
* Item 2
* Item 3
```

## Lista Ordenada

Cada item de uma lista ordenada é criado a partir de um número seguido de um ponto, como `1.`.

***Exemplo:***

```
1. Item 1
2. Item 2
3. Item 3
```

Caso no início das linhas dos itens fossem iguais, como por exemplo `1.`, não haveria nenhum problema, já a numeração dos itens é feita automaticamente.

## Aninhamento de Listas

Você pode aninhar uma lista dentro da outra, e a única regra a se lembrar é que os itens das listas mais de dentro devem ter uma espaço a mais.

***Exemplo:***

```
* Item 1
    * Sub item 1
        * Sub item 3
```

