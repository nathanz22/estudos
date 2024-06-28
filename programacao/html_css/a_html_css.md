# HTML e CSS

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

### Parágrafos

Para criar um parágrafo, é utilizada a tag **`<p>`**.

**Exemplo:**

``` html
<body>
    <p>Isso é um parágrafo!</p>
    <p>Isso é um outro parágrafo!</p>
</body>
```

### Títulos

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

### Listas

As listas podem ser ordenadas e não ordenadas, sendo marcadas por número e marcadores, respectivamente.

#### Listas Ordenadas

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

#### Listas não Ordenadas

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

#### Listas Mistas

É possível criar listas dentro de listas, criando assim uma lista mista.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="en">
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

#### Listas de Definição

As ***definition lists*** são como dicionários criados a partir da tag **`dl`** (precisa ser fechada), onde o termo a ser definido é posto na tag **`<dt>`** (precisa ser fechada) e a definição é posta na tag **`<dd>`**.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="en">
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

#### *Entities*

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

### Destaques em Textos

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

<!-- Citações -->
<!-- Abreviação -->
<!-- Imagens -->
