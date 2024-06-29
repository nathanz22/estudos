# HTML

## Sintaxe Básica de HTML

Em HTML, os elementos são criados a partir de **tags**. Existem dois tipos de tags, as que precisam ser fechadas, e as que não.

**Exemplo:**

``` html
<!-- Tags com fechamento -->
<h1>titulo</h1>
<p>paragrafo</p>

<!-- Tags sem fechamento -->
<link>
<img>
```

### Comentários

Em HTML, é considerado um comentário tudo entre **`<!--`** e **`-->`**.

**Exemplo:**

``` html
<!-- Isso é um comentário! -->
<!--
Isso
também
é um
comentário
-->
```

## Parágrafos

Para criar um parágrafo, é utilizada a tag **`<p>`**.

**Exemplo:**

``` html
<body>
    <p>Isso é um parágrafo!</p>
    <p>Isso é um outro parágrafo!</p>
</body>
```

## Títulos

Existem seis títulos em HTML.

1. **'`h1`'**: Título de nível 1.
1. **'`h2`'**: Título de nível 2 (subtítulo do nível 1).
1. **'`h3`'**: Título de nível 3 (subtítulo do nível 2).
1. **'`h4`'**: Título de nível 4 (subtítulo do nível 3).
1. **'`h5`'**: Título de nível 5 (subtítulo do nível 4).
1. **'`h6`'**: Título de nível 6 (subtítulo do nível 5).

**Exemplo:**

``` html
<body>
    <h1>Título</h1>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis, fuga, architecto natus, quidem reiciendis quia commodi eius ratione quae ea quo doloribus neque error harum esse. Provident eaque maxime repudiandae?
    </p>
    <h2>Subtítulo</h2>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus animi, tenetur quia natus tempora nostrum fuga dignissimos dolores possimus! Sunt vel voluptates nam ea quae velit saepe necessitatibus quo tempora.

        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ut repellat distinctio esse optio eum minus? Aliquid soluta nulla aperiam rem deleniti corporis, commodi quaerat quisquam esse voluptatem labore beatae quo!
    </p>
</body>
```

O título principal deve ser o **`<h1>`**. Os subtítulos desse título principal devem ser **`<h2>`**, os subtítulos desse `<h2>` devem ser **`<h3>`**, e assim por diante.

Além disso, não há problema nenhum em haver dois **`<h1>`** em uma mesma página, contanto que seja de maneira organizada e afim de aprimorar o entendimento do conteúdo.

**Exemplo:**

``` html
<body>
    <h1>Conteúdo 1</h1>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis, fuga, architecto natus, quidem reiciendis quia commodi eius ratione quae ea quo doloribus neque error harum esse. Provident eaque maxime repudiandae?
    </p>

    <h1>Conteúdo 2</h1>
    <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque magnam quos totam id in hic ut reiciendis. Itaque dolores odio magni ratione ducimus quod, eligendi, sapiente tempora voluptas et omnis.
    </p>
</body>
```

## Listas

As listas podem ser ordenadas e não ordenadas, sendo marcadas por número e marcadores, respectivamente.

### Listas Ordenadas

As ***ordered lists*** são aquelas listas que a ordem de cada item é importante.

Para criar uma lista ordenada, é usada a tag **`<ol>`** (precisa ser fechada), e dentro dessa tag, são listados os itens da lista com a tag **`<li>`** (pode ou não ser fechada).

**Exemplo:**

``` html
<body>
    <ol>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
        <li>Item 4</li>
        <li>Item 5</li>
    </ol>
</body>
```

A tag `<ol>` possui o parâmetro **`type`**, onde é definido o tipo de marcador ordenado dessa lista.

* **'`1`'**: Valor padrão. Os itens são numerados no sistema decimal. Ex.: 1, 2, 3, 4, 5.
* **'`a`'**: Lista alfabética minúscula. Os itens são numerados com as letras do alfabeto minúsculas e em ordem alfabética. Ex.: a, b, c, d, e.
* **'`A`'**: Lista alfabética maiúscula. Os itens são numerados com as letras do alfabeto maiúsculas e em ordem alfabética. Ex.: A, B, C, D, E.
* **'`i`'**: Lista ordenada com algarismos romanos minúsculos. Ex.: i, ii, iii, iv, v.
* **'`I`'**: Lista ordenada com algarismos romanos maiúsculos. Ex.: I, II, III, IV, V.

> **Parâmetro `start`**: O parâmetro `start` define o primeiro valor de uma lista, a atualizando a partir desse valor. O valor desse parâmetro deve ser numérico, mesmo que a forma de contagem da lista seja alfabética.

### Listas não Ordenadas

As ***unordered lists*** são aquelas em que a ordem dos itens não importa.

Para criar uma lista não ordenada, é usada a tag **`<ul>`** (precisa ser fechada), e cada item dessa lista é criado a partir da tag **`<li>`** (pode ou não ser fechada).

**Exemplo:**

``` html
<body>
    <ul>
        <li>Primeiro item</li>
        <li>Segundo item</li>
        <li>Terceiro item</li>
        <li>Quarto item</li>
        <li>Quinto item</li>
    </ul>
</body>
```

### Listas Mistas

É possível criar listas dentro de listas, criando assim uma lista mista.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Listas Mistas</title>
</head>
<body>
    <ol>
        <li>Ação</li>
        <ul>
            <li>Mad Max: Estrada da Fúria (2015)</li>
            <li>John Wick (2014)</li>
            <li>Velozes e Furiosos 7 (2015)</li>
        </ul>

        <li>Aventura</li>
        <ul>
            <li>Indiana Jones e os Caçadores da Arca Perdida (1981)</li>
            <li>O Senhor dos Anéis: A Sociedade do Anel (2001)
            </li>
            <li>Piratas do Caribe: A Maldição do Pérola Negra (2003)
            </li>
        </ul>

        <li>Comédia</li>
        <ul>
            <li>Superbad: É Hoje (2007)
            </li>
            <li>Se Beber, Não Case! (2009)
            </li>
            <li>A Vida de Brian (1979)
            </li>
        </ul>
    </ol>
</body>
</html>
```

### Listas de Definição

As ***definition lists*** são como dicionários criados a partir da tag **`dl`** (precisa ser fechada), onde o termo a ser definido é posto na tag **`<dt>`** (precisa ser fechada) e a definição é posta na tag **`<dd>`**.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Listas de Definição</title>
</head>
<body>
    <dl>
        <dt>Epistemologia</dt>
        <dd>Ramo da filosofia que estuda a natureza, origem e limites do conhecimento humano.</dd>
        <dt>Homeostase</dt>
        <dd>Capacidade de um organismo ou sistema de manter a estabilidade interna em resposta a mudanças externas.</dd>
        <dt>Entropia</dt>
        <dd>Medida da desordem ou aleatoriedade em um sistema, frequentemente associada à segunda lei da termodinâmica.</dd>
    </dl>
</body>
</html>
```

## *Entities*

As entidades são caracteres especiais, escritos a partir de um código de identificação.

**Exemplo:**

``` html
<body>
    <ul>
        <li>Espaço em branco: nbsp; - &nbsp;</li>
        <li>Marca registrada: reg; - &reg;</li>
        <li>Copyright: copy; - &copy;</li>
        <li>Trade Mark: trade - &trade;</li>
        <li>Euro: euro; - &euro;</li>
        <li>Libra: pound; - &pound;;</li>
        <li>Yen: yen; - &yen;</li>
        <li>Cent: cent; - &cent;</li>
        <li>Vazio: empty; - &empty;</li>
        <li>Soma: sum; - &sum;</li>
        <li>Delta: Delta; - &Delta;</li>
        <li>Seta esquerda: larr; - &larr;</li>
        <li>Seta acima: uarr; - &uarr;</li>
        <li>Seta direita: rarr; - &rarr;</li>
        <li>Seta abaixo: darr; - &darr;</li>
    </ul>
</body>
```

## Semântica em HTML

Em HTML, o que importa é o significado, já a parte da forma (estilização) é com as CSS.

Tags como `<u>` e `<b>`, que transformam seu conteúdo em itálico e negrito, respectivamente, são tags genéricas. Já as tags `<em>` e `<strong>`, são tags que possuem semântica (elas significam "ênfase" e "forte").

## Destaques em Textos

* **Negrito**: É utilizada a tag **`<strong>`** (semântico) ou **`<b>`** (não semântico).

    ``` html
    <body>
        <p>
            Olá, <strong>Mundo</strong>!
            <br>
            Hello, <b>World</b>!
        </p>
    </body>
    ```

* **Itálico**: É utilizada a tag **`<em>`** (semântico) ou **`<i>`** (não semântico).

    ``` html
    <body>
        <p>
            Olá, <em>Mundo</em>!
            <br>
            Hello, <i>World</i>!
        </p>
    </body>
    ```

* **Sublinhar**: Para sublinhar um texto, é usada a tag **`<mark>`**.

    ``` html
    <body>
        <p>
            Olá, <mark>Mundo</mark>!
        </p>
    </body>
    ```

* **Riscar texto (descartar)**: Para riscar um texto (descartar) é usada a tag **`<del>`**.

    ``` html
    <body>
        <p>
            Olá, <del>Mundo</del>!
        </p>
    </body>
    ```

* **Caracteres Pequenos Acima/Abaixo**: Para escrever o 2 de H20, por exemplo, poderia usar a tag **`<sub>`**. Já para escrever o expoente de um número, poderia utilizar **`<sup>`**.

    ``` html
    <body>
        <p>
            H<sub>2</sub>0
        </p>
        <p>
            10<sup>5</sup>
        </p>
    </body>
    ```

* **Texto invertido**: Para inverter o texto, é usada a tag **`<bdo>`**, que recebe a direção no parâmetro `dir`.

  * `rtl`: Right to left (direita para a esquerda)
  * `ltr`: Left to right (esquerda para direita)

    ``` html
    <body>
        <p>
            Olá, <bdo dir="rtl">Mundo</bdo>!
        </p>
        <p>
            Olá, <ltr>Mundo</ltr>!
        </p>
    </body>
    ```

## Emojis

Para usar emojis em uma página, é necessário o ***Codepoint*** do emoji.

> Os codepoints dos emojis podem ser encontrados em [Emojipedia](www.emojipedia.org).

Um codepoint deve ser transcrito substituindo "U+" por `&#x`, acrescentando um ponto e vírgula (`;`) no final.

**Exemplo:**

``` html
<body>
    <p>Fire:&#x1F525;</p>
</body>
```

## Manter Escrita da Forma Digitada

Todo texto dentro da tag **`<pre>`** e seu fechamento é mantido da forma digitada, com espaços e quebras de linha.

**Exemplo:**

``` html
<body>
    <pre>
        Lorem
        ipsum dolor sit amet consectetur adipisicing
        elit. Sunt minus cum voluptate
        laborum quisquam facilis cumque
        reiciendis magnam aspernatur.
        Eaque, amet cumque
        adipisci magni consequatur natus id
        doloremque culpa
        molestiae.
    </pre>
</body>
```

Geralmente é usado em conjunto com a tag **`<code>`**, que é usada para ilustrar código.

## Ilustração de Código

Para ilustrar código, é usada a tag **`<code>`** (precisa ser fechada).

**Exemplo:**

``` html
<body>
    <h1>
        <pre>   Ímpar ou Par em Python</pre>
    </h1>
    <pre>
        <code>
            n = int(input('Digite um número: '))
            if n % 2 == 0:
                print(f'O número {n} é PAR!')
            else:
                print(f'O número {n} é ÍMPAR!')
        </code>
    </pre>
</body>
```

## Citações

Para fazer uma citação, é usada a tag **`<q>`** (*"quote"*), que precisa ser fechada.

**Exemplo:**

``` html
<body>
    <p>
        Lorem ipsum dolor <q>sit amet consectetur adipisicing</q> elit. Sint perspiciatis ab suscipit dicta mollitia et quibusdam incidunt, error, natus doloribus voluptates dolorum aliquid molestias commodi, minima voluptas quaerat veritatis eius?
    </p>
</body>
```

Para citar um bloco inteiro, é usada a tag **`<blockquote>`** (precisa ser fechada), que recebe o parâmetro `cite`, que deve receber uma URL.

**Exemplo:**

``` html
<body>
    <blockquote cite="link.com">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium eveniet dolorum tenetur possimus distinctio asperiores corporis quo quia. Minus asperiores quae neque magnam debitis suscipit, iste ratione iure cumque commodi.
    </blockquote>
</body>
```

## Abreviação

A tag **`<abbr>`** (precisa ser fechada) é usada para criar uma abreviação de um trecho do texto. Ela faz com que apareça um texto quando passado o cursor sobre o trecho. O texto que irá aparecer deve ser definido no parâmetro **`title`**.

**Exemplo:**

``` html
<body>
    <p>
        Lorem ipsum <abbr title="foobar">dolor</abbr>, sit amet consectetur adipisicing elit.
    </p>
</body>
```

## Imagens

### Formatos de Imagens

Existem diversos formatos para imagens, e os melhores para se usar são **PNG** e **JPEG** por serem formatos leves, o que facilita sua renderização.

**Utilize PNG** caso seja necessário um fundo transparente. Em qualquer outro caso, **utilize JPEG**.

### Importação de Imagem

Para importar uma imagem, é usada a tag `<img>` (não precisa ser fechada).

**Sintaxe:**

``` html
<img src="caminho_da_imagem" alt="texto alternativo">
```

**Exemplo:**

``` html
<body>
    <img src="img.jpeg" alt="Imagem">
</body>
```

O **texto alternativo** aparecerá quando a imagem não puder ser carregada.

### *Favicons*

Os ***favicons*** são os ícones ao lado do título da página. Para eles, é recomendado o formato **`ico`**, que são arquivos de ícones.

Os *favicons* são definidos na área **`<head>`** por meio da tag **`<link>`**.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="favicon.jpeg" type="image/x-icon">
    <title>Favicon</title>
</head>
<body>
    <h1>Favicon</h1>
</body>
</html>
```

## Hyperlinks

Para colocar um link, é usada a tag **`<a>`** (precisa ser fechada). O texto que ficar dentro dessa tag será transformado em um link, definido no parâmetro **`href`**.

**Exemplo:**

``` html
<body>
    <p>
        Link do <a href="https://www.youtube.com">YouTube</a>.
    </p>
</body>
```

Ao clicar em um link o usuário é, por padrão, redirecionado a uma página aberta na mesma aba, substituindo a aba anterior. É possível incluir o parâmetro **`target`** para definir se a página do link deve ser aberta em uma nova aba ou na mesma.

**Os valores para `target` são:**

* **'`_blank`'**: Vai abrir o link em uma nova aba.
* **'`_self`'**: Vai abrir o link na mesma aba (padrão).

**Exemplo:**

``` html
<body>
    <p>
        Link do <a href="https://www.youtube.com" target="_blank">YouTube</a>.
    </p>
</body>
```

### Tipos de Redirecionamento

A tag `<a>` aceita também o parâmetro **`rel`**, que determina o tipo de redirecionamento.

**Os valores para `rel` são:**

* **'`next`'**: Próxima página.
* **'`prev`'**: Página anterior.
* **'`author`'**: Para o site do autor do documento atual.
* **'`external`'**: Para um site que não faz parte do atual.
* **'`nofollow`'**: Para um site não endosado, como um link pago.

### Link Interno

Um link interno direciona o usuário para uma página dentro do mesmo site. Dessa forma, é especificado o caminho da página dentro da pasta do arquivo do site.

**Exemplo:**

``` html
<!-- Página principal -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página inicial</title>
</head>
<body>
    <h1>Página 1</h1>
    <p>
        Clique <a href="pagina2.html">aqui</a> para ir para a próxima página.
    </p>
</body>
</html>
```

``` html
<!-- Página 2 -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página 2</title>
</head>
<body>
    <h2>Página 2</h2>
    <p>
        Clique <a href="index.html">aqui</a> para voltar para a página inicial.
    </p>
</body>
</html>
```
