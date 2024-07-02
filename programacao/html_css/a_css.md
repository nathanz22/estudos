# CSS

## Sintaxe Básica

Nas CSS, os estilos são aplicados em um elemento HTML, e esse elemento é estilizado a partir de uma propriedade CSS, que recebe um valor. No fim de cada declaração, deve haver um **`;`**.

**Exemplo:**

``` css
@charset "UTF-8";
/* Para não haver nenhuma incompatibilidade com determinados caracteres */

* {
    margin: 0px;
    padding: 0px;
}

html, body {
    font-family: Arial, Helvetica, sans-serif;
    background-color: rgb(187, 186, 186);
}

h1 {
    padding-left: 10px;
}
```

As chaves após o elemento HTML delimitam o bloco em que são definidos os estilos desse elemento.

### Aplicar Estilos

Existem três formas de aplcar estilos em um documento HTML: ***inline***, ***internal*** e ***external***.

#### CSS *Inline*

CSS *Inline* é aplicar os estilos diretamente no elemento em HTML por meio do parâmetro **`style`**.

**Exemplo:**

``` html
<body>
    <h1 style="color: darkred;">Hello, World!</h1>
</body>
```

> **NOTA:** As CSS Inline devem ser evitadas, pois, além de tornar o código menos legível, dificultam a manutenção.

#### CSS *Internal*

CSS *Internal* é aplicar os estilos dentro do código HTML por meio da tag **`<style>`** (precisa ser fechada).

**Exemplo:**

``` html
<body>
    <h1>Hello, World!</h1>
</body>
<style>
    h1 {
        color: darkred;
    }
</style>
```

> **NOTA:** A tag `<style>` pode ficar em qualquer lugar no código HTML.

#### CSS *External*

CSS *External* é aplicar os estilos a partir de um arquivo CSS separado. No código HTML, é necessário importar o arquivo CSS com a tag **`<link>`**.

**Sintaxe `<link>`:**

``` html
<link rel="stylesheet" href="style.css">
```

O valor de `href` deve ser o arquivo CSS, que normalmente é chamado de `style.css`.

**Exemplo:**

``` html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Titulo</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>

```

``` css
@charset "UTF-8";

h1 {
    color: darkred;
}
```

> **Vários CSS externos:** Caso haja dois ou mais estilos externos, terão todos os seus estilos somados e aplicados à página. Em caso de diferentes valores em uma mesma propriedade, as CSS externa mais abaixo no código terá prioridade.

### Comentários em CSS

Em CSS, é considerado um comentário tudo entre **`/*`** e **`*/`**.

**Exemplo:**

``` css
/* Isso é um comentário */
/*
Isso
também
é um
comentário
*/
```

## Seletores

Os seletores são usados para selecionar elementos HTML, seja um elemento isolado ou um grupo.

**Exemplo:**

``` html
<style>
    body {
        font-family: Arial, Helvetica, sans-serif;
        background-color: darkslategray;
    }

    h1, p {
        color: white;
    }

    p {
        text-indent: 16px;
    }
</style>
<body>
    <h1>Hello, World!</h1>
    <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit aut laboriosam dicta. Corporis, repudiandae. Odit, at, magni minus porro natus laudantium accusantium dolorem veniam amet eius dolor, minima facere nesciunt.
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum ipsum animi officiis nisi eos optio nam consequuntur iure numquam minima voluptatum, reiciendis recusandae odio possimus veritatis assumenda architecto adipisci expedita?
    </p>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio nihil maxime, suscipit quaerat iste natus sequi consectetur eaque amet repellat est libero cupiditate nobis minus nisi odit necessitatibus aut itaque!
    </p>
</body>
```

Em `<style>` acima, `body`, `h1` e `p` são os seletores referentes aos elementos HTML definidos em `<body>`.

Como mostrado acima, se as mesmas propriedades devem ser aplicadas a diferentes elementos, seus seletores podem ser separados por vírgula e receber o mesmo bloco.

### Seleção por `id`

Para selecionar apenas um elemento específico, deve ser especificado o **`id`** dele após um **`#`**.

**Exemplo:**

``` html
<style>
    #p1 {
        color: red;
    }

    #p2 {
        color: blue;
    }

    #p3 {
        color: yellow;
    }
</style>
<body>
    <h1>Hello, World!</h1>
    <p id="p1">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit aut laboriosam dicta. Corporis, repudiandae. Odit, at, magni minus porro natus laudantium accusantium dolorem veniam amet eius dolor, minima facere nesciunt.
    </p>
    <p id="p2">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum ipsum animi officiis nisi eos optio nam consequuntur iure numquam minima voluptatum, reiciendis recusandae odio possimus veritatis assumenda architecto adipisci expedita?
    </p>
    <p id="p3">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio nihil maxime, suscipit quaerat iste natus sequi consectetur eaque amet repellat est libero cupiditate nobis minus nisi odit necessitatibus aut itaque!
    </p>
</body>
```

Se desejar, você pode também especificar o tipo de elemento antes do `id`.

**Exemplo:**

``` css
p#p1 {
    color: red;
}

p#p2 {
    color: blue;
}

p#p3 {
    color: yellow;
}
```

### Seleção por `class`

Para selecionar um grupo, todos os elementos devem pertencer à mesma classe. Para estilizar o grupo inteiro, deve ser escrito o nome da classe após um **`.`**.

**Exemplo:**

``` html
<style>
    p {
        color: darkblue;
    }

    .paragrafo {
        color: darkred;
    }
</style>
<body>
    <h1>Hello, World!</h1>
    <p class="paragrafo">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit aut laboriosam dicta. Corporis, repudiandae. Odit, at, magni minus porro natus laudantium accusantium dolorem veniam amet eius dolor, minima facere nesciunt.
    </p>
    <p class="paragrafo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum ipsum animi officiis nisi eos optio nam consequuntur iure numquam minima voluptatum, reiciendis recusandae odio possimus veritatis assumenda architecto adipisci expedita?
    </p>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio nihil maxime, suscipit quaerat iste natus sequi consectetur eaque amet repellat est libero cupiditate nobis minus nisi odit necessitatibus aut itaque!
    </p>
</body>
```

Se desejar, você pode também especificar o tipo de elemento antes da `class`, fazendo com que apenas tipos de elementos específicos sejam afetados.

``` html
<style>
    p {
        color: darkblue;
    }

    p.destaque {
        font-style: italic;
        font-weight: bold;
    }
</style>
<body>
    <h1 class="destaque">Hello, World!</h1>
    <p class="destaque">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit aut laboriosam dicta. Corporis, repudiandae. Odit, at, magni minus porro natus laudantium accusantium dolorem veniam amet eius dolor, minima facere nesciunt.
    </p>
    <p class="destaque">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum ipsum animi officiis nisi eos optio nam consequuntur iure numquam minima voluptatum, reiciendis recusandae odio possimus veritatis assumenda architecto adipisci expedita?
    </p>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio nihil maxime, suscipit quaerat iste natus sequi consectetur eaque amet repellat est libero cupiditate nobis minus nisi odit necessitatibus aut itaque!
    </p>
</body>
```

No exemplo acima, mesmo que o elemento `<h1>` presente faça parte da classe `destaque`, ele não é afetado por não ser um parágrafo.

#### Elemento com Mais de Uma Classe

É possível que um mesmo elemento possua duas classes, podendo assim receber propriedades de seletores diferentes.

**Exemplo:**

``` html
<style>
    p {
        color: darkblue;
    }

    p.paragrafo {
        color: darkred;
    }

    .destaque {
        font-style: italic;
        font-weight: bold;
    }
</style>
<body>
    <h1 class="destaque">Hello, World!</h1>
    <p class="paragrafo">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit aut laboriosam dicta. Corporis, repudiandae. Odit, at, magni minus porro natus laudantium accusantium dolorem veniam amet eius dolor, minima facere nesciunt.
    </p>
    <p class="paragrafo destaque">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum ipsum animi officiis nisi eos optio nam consequuntur iure numquam minima voluptatum, reiciendis recusandae odio possimus veritatis assumenda architecto adipisci expedita?
    </p>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio nihil maxime, suscipit quaerat iste natus sequi consectetur eaque amet repellat est libero cupiditate nobis minus nisi odit necessitatibus aut itaque!
    </p>
</body>
```

### Pseudo-classes

São usados para selecionar os elementos em um estado especial, como `:hover` (quando o cursor está sob o elemento) e `:visited` (quando o link já foi visitado antes).

**Exemplo:**

``` html
<style>
    h1 {
        color: darkblue;
    }

    h1:hover {
        color: darkred;
    }
</style>
<body>
    <h1>Hello, World!</h1>
</body>
```

### Pseudo-elementos

Servem para formatar um pedaço específico do elemento referenciado. Exemplos são `::before`, `::after`, `::first-letter` e `::first-line`.

**Exemplo:**

``` html
<style>
    h1 {
        color: darkblue;
    }

    h1::first-letter {
        color: darkred;
    }
</style>
<body>
    <h1>Hello, World!</h1>
</body>
```

### *Children*

Os elementos internos de um outro elemento podem ser acessados por meio de um caminho com `>`, ou simplesmente especificando o tipo/`id`/`class` do elemento.

**Exemplo:**

``` html
<style>
    div > p > a {
        color: darkred;
    }

    /* Ou */
    div a {
        color: darkred
    }
</style>
<body>
    <div>
        <p>
            Acesse o <a href="https://www.google.com" target="_blank">Google</a>
        </p>
    </div>
    <p>
        Acesse o <a href="https://www.youtube.com" target="_blank">YouTube</a>
    </p>
</body>
```

## Caixas (Boxes)

As caixas são a grande maioria dos objetos em HTML, como os títulos e os parágrafos. Elas armazenam conteúdos dentro deles, podendo esses conteúdos ser outras caixas.

**Estrutura de uma caixa:**

* **'`content`'**: É o conteúdo, sendo o centro da caixa.
* **'`padding`'**: É o preenchimento que fica entre o conteúdo e a borda.
* **'`border`'**: É a borda, e vem em seguido do preenchimento.
* **'`outline`'**: É o contorno, visualmente um traçado. É pouco utilizado.
* **'`margin`'**: É a margem, a parte de fora da caixa.

**Exemplo:**

``` html
<style>
    h1 {
        width: 300px;
        height: 50px;
        background-color: gray;
        border: 10px solid darkgreen;
        padding: 20px;
        outline: blue solid 30px;
        margin: 50px;
    }
</style>
<body>
    <h1>Hello, World!</h1>
</body>
```

A propriedade **`border`** é uma *shorthand* para as propriedades:

1. **`border-width`**
1. **`border-style`**
1. **`border-color`**

A propriedade **`outline`** é uma *shorthand* para as propriedades:

1. **`outline-color`**
1. **`outline-style`**
1. **`outline-width`**

A propriedade **`padding`** é uma *shorthand* para as propriedades:

1. **`padding-top`**
1. **`padding-right`**
1. **`padding-bottom`**
1. **`padding-left`**

A propriedade **`margin`** é uma *shorthand* para as propriedades:

1. **`margin-top`**
1. **`margin-right`**
1. **`margin-bottom`**
1. **`margin-left`**

Se definido apenas um valor para as propriedades `padding` e `margin`, será contado esse valor para todos os outros lados. Caso definidos dois valores, o primeiro será para cima e para baixo, e o segundo será para os lados.

Definir **`auto`** como valor de **`margin`** fará com que o navegador calcule automaticamente o valor para que a caixa fique centralizada.

> **Tamanho total da caixa:** Para calcular o tamanho total de um elemento, é preciso somar: `content` + `padding` + `border` + `margin`. O `outline` (contorno) não entra nessa conta, pois o mesmo utiliza parte da margem.

## Fontes

As propriedades que configuram as fontes são:

1. **`font-style`**: Estilo da fonte (itálico, obliquo).
1. **`font-variant`**: Versaletes (letras maiúsculas com tamanho de minúsculas).
1. **`font-weight`**: Peso.
1. **`font-size`**: Tamanho.
1. **`font-family`**: Familia tipográfica.

**Exemplo:**

``` css
body {
    font-style: italic;
    font-variant: small-caps;
    font-weight: bold;
    font-size: 16px;
    font-family: Arial, Helvetica, sans-serif;
}
```

A propriedade **`font`** é uma *shorthand* para todas as propriedades acima, na mesma ordem que elas estão dispostas.

``` css
body {
    font: oblique small-caps bold 16px Arial, Helvetica, sans-serif;
}
```

### Espaçamento Horizontal

O espaçamento horizontal entre as linhas é definido pela propriedade **`line-height`**.

**Exemplo:**

``` css
body {
    line-height: 16px;
}
```

### Alinhamento de Texto

A propriedade **`text-align`** é usada para alinhar o texto. Os valores são:

* **'`left`'**, **'`start`**': Alinha à esquerda (no começo).
* **'`right`'**, **'`end`**': Alinha à direita (no final).
* **'`center`'**: Alinha no centro.
* **'`justify`'**: Padrão.

### Identação

A propriedade **`text-indent`** é usada para definir o tamanho da identação de um texto.

**Exemplo:**

``` css
p {
    text-indent: 30px;
}
```

### Fontes Externas

É possível usar fontes externas por meio de arquivos de fonte. Esses arquivos são do tipo **OTF** ou **TTF**, e a diferença entre elas é a compatibilidade com os navegadores.

Para aplicar uma fonte externa, é necessário criar a regra **`@font-face`** no início do código CSS.

**Sintaxe:**

``` css
@font-face {
    font-family: ; /* Nome de referência para a fonte */
    src: url() format();
    /* Em `src`, especifique o iretório do arquivo da fonte */
    /* Em `format()`, especifique o tipo da fonte */
}
```

**Tipos de fonte:**

* **'`opentype`'**: Para fontes OTF (algumas fontes opentype são TTF).
* **'`truetype`'**: Para fontes TTF.
* **'`embedded-opentype`'**
* **'`truetype-att`'**: Apple Advanced Typography.
* **'`svg`'**

> **NOTA:** É possível colocar vários url, mas cada um deve vir acompanhado de um format e cada conjunto de url e format devem ser separados por vírgula. Isso é útil para garantir que o site seja compatível com vários navegadores.
