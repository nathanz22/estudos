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

## Textos

### Fontes

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

### Transformações de Texto

A propriedade **`text-transform`** pode transformar um texto em maiúsculo, minúsculo ou capitalizá-lo.

**Seus valores são:**

* `capitalize`
* `lowercase`
* `uppercase`

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    p#capitalize {
        text-transform: capitalize;
    }

    p#lower {
        text-transform: lowercase;
    }

    p#upper {
        text-transform: uppercase;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p id="capitalize">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa, ducimus. Minus necessitatibus pariatur recusandae hic cum mollitia aut voluptas, officiis ipsa repellat sapiente quos, ut beatae possimus distinctio ex? Maiores!
        </p>
        <p id="lower">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde incidunt ex sunt aliquam blanditiis ut fuga rem veritatis consequatur repellendus voluptate dolores earum, aut velit qui deleniti excepturi alias. Fugiat!
        </p>
        <p id="upper">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem veniam praesentium quia alias sunt blanditiis, asperiores soluta quisquam harum ipsum placeat laudantium reprehenderit neque nam commodi, nostrum id quod sed.
        </p>
    </div>
</body>
```

### Espaçamento Horizontal

O espaçamento horizontal entre as linhas é definido pela propriedade **`line-height`**.

**Exemplo:**

``` css
body {
    line-height: 16px;
}
```

### Espaçamento Entre os Caracteres

A propriedade **`letter-spacing`** recebe um valor de tamanho, relativo ao espaçamento horizontal entre os caracteres.

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    p {
        letter-spacing: 5px;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa, ducimus. Minus necessitatibus pariatur recusandae hic cum mollitia aut voluptas, officiis ipsa repellat sapiente quos, ut beatae possimus distinctio ex? Maiores!
        </p>
        <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde incidunt ex sunt aliquam blanditiis ut fuga rem veritatis consequatur repellendus voluptate dolores earum, aut velit qui deleniti excepturi alias. Fugiat!
        </p>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem veniam praesentium quia alias sunt blanditiis, asperiores soluta quisquam harum ipsum placeat laudantium reprehenderit neque nam commodi, nostrum id quod sed.
        </p>
    </div>
</body>
```

### Espaçamento Entre as Palavras

A propriedade **`word-spacing`** recebe um valor em tamanho que determina o espaçamento entre as palavras.

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    p {
        word-spacing: 1.5em;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa, ducimus. Minus necessitatibus pariatur recusandae hic cum mollitia aut voluptas, officiis ipsa repellat sapiente quos, ut beatae possimus distinctio ex? Maiores!
        </p>
        <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde incidunt ex sunt aliquam blanditiis ut fuga rem veritatis consequatur repellendus voluptate dolores earum, aut velit qui deleniti excepturi alias. Fugiat!
        </p>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem veniam praesentium quia alias sunt blanditiis, asperiores soluta quisquam harum ipsum placeat laudantium reprehenderit neque nam commodi, nostrum id quod sed.
        </p>
    </div>
</body>
```

### Alinhamento de Texto

A propriedade **`text-align`** é usada para alinhar o texto. Os valores são:

* **'`left`'**, **'`start`**': Alinha à esquerda (no começo).
* **'`right`'**, **'`end`**': Alinha à direita (no final).
* **'`center`'**: Alinha no centro.
* **'`justify`'**: Padrão.

### Identação do Texto

A propriedade **`text-indent`** recebe um valor de tamanho relativo à identação do texto.

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    p {
        text-indent: 1.5em;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa, ducimus. Minus necessitatibus pariatur recusandae hic cum mollitia aut voluptas, officiis ipsa repellat sapiente quos, ut beatae possimus distinctio ex? Maiores!
        </p>
        <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde incidunt ex sunt aliquam blanditiis ut fuga rem veritatis consequatur repellendus voluptate dolores earum, aut velit qui deleniti excepturi alias. Fugiat!
        </p>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem veniam praesentium quia alias sunt blanditiis, asperiores soluta quisquam harum ipsum placeat laudantium reprehenderit neque nam commodi, nostrum id quod sed.
        </p>
    </div>
</body>
```

### Comportamento do Espaço em Branco

A propriedade **`white-space`** determina como o espaço em branco dentro do elemento deve se comportar.

**Seus valores são:**

* **'`normal`'**: O texto será quebrado quando necessário.
* **'`nowrap`'**: Não haverá quebra de linha.
* **'`pre`'**: O texto será mantido da forma que foi digitado.
* **'`pre-line`'**: Igual `pre`, porém exclui os espaços de identação.
* **'`pre-wrap`'**: Igual `pre`, porém quebra de linha quando necessário.

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: 'Courier New', Courier, monospace;
        font-size: 1em;
        font-weight: bold;
    }

    p {
        white-space: pre;
    }
</style>
<body>
    <div>
        <h1>Par ou Ímpar em Go</h1>
        <p>
            package main

            import "fmt"

            func main() {
                var n int
                fmt.Print("Digite um número: ")
                _, err := fmt.Scan(&n)
                if err != nil {
                    fmt.Println("Err:", err)
                    return
                }
                if n % 2 == 0 {
                    fmt.Printf("O número %d é PAR\n", n)
                } else {
                    fmt.Printf("O número %d é ÍMPAR\n", n)
                }
            }
        </p>
    </div>
</body>
```

## Estilização de Estados de Links

Para estilizar um estado específico de um link, são usadas as seguintes pseudo-classes:

* **'`:link`'**: Ainda não visitado.
* **'`:visited`'**: Já visitado.
* **'`:hover`'**: Cursor sobre o link.
* **'`:active`'**: No momento do clique.

**Exemplo:**

``` html
<style>
    div {
        background-color: #dbd9d9;
        padding: 10px;
        margin: 5px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    a {
        display: block;
        text-align: center;
    }

    a:link {
        color: red;
        text-decoration: none;
    }

    a:visited {
        color: blue;
    }

    a:hover {
        color: darkred;
        text-decoration: underline;
    }

    a:active {
        color: blueviolet;
        font-weight: bold;
    }
</style>
<body>
    <div>
        <a href="#">Link</a>
    </div>
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

### Tipos de Caixas

Existem dois tipos de caixa, classificados de acordo com seu comportamento. São eles ***block-level*** e ***inline-level***.

#### Caixas *Block-level*

Um elemento *block-level* sempre se inicia em uma nova linha, e vai ocupar a largura total do elemento onde está contido. Se não estiver contido em nenhuma outra caixa, vai ocupar a largura total do `<body>`.

**Exemplos de elementos *block-level*:**

* `<address>`
* `<articles>`
* `<aside>`
* `<blockquote>`
* `<canvas>`
* `<dd>`
* `<div>`
* `<main>`
* `<ol>`
* `<h1>`
* `<p>`
* `<pre>`

#### Caixas *Inline-level*

Elementos *inline-level* ocupam o espaço relativo ao seu conteúdo, e se iniciam no ponto exato em que está definido.

**Exemplos de elementos *inline-level*:**

* `<a>`
* `<abbr>`
* `<b>`
* `<br>`
* `<i>`
* `<label>`
* `<select>`
* `<sub>`
* `<strong>`
* `<tt>`
* `<img>`
* `<button>`
* `<input>`

### Cantos da Borda Arredondados

Para arredondar as bordas da caixa, é usada a propriedade **`border-radius`**, que recebe o valor de arredondamento para cada canto.

**Os valores são:**

1. Valor de arredondamento para o canto superior esquerdo.
1. Valor de arredondamento para o canto superior direito.
1. Valor de arredondamento para o canto inferior esquerdo.
1. Valor de arredondamento para o canto inferior direito.

**Exemplo:**

``` html
<style>
    div {
        background-color: grey;
        padding: 10px;
        margin: 10px;
        text-align: justify;
        font-family: Arial, Helvetica, sans-serif;

        /* Arredondamento da borda */
        border-radius: 1em 2em 1em 1.5em;
    }

    h1 {
        font-variant: small-caps;
    }

    p {
        text-indent: 10px;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ipsa, unde eum exercitationem non corporis blanditiis tempore quisquam possimus expedita architecto vero quia natus voluptatum culpa assumenda totam fuga quaerat ipsum.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta, distinctio! Obcaecati tenetur, delectus dignissimos earum reprehenderit quibusdam doloribus magni nesciunt dolorem odio, sed temporibus ipsam at reiciendis. Excepturi, est ea.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi, enim blanditiis qui doloremque eligendi voluptatum, ipsa iusto similique eum temporibus in perferendis consequatur nesciunt placeat nulla odit hic natus facilis.
        </p>
    </div>
</body>
```

> **NOTA:** Especificar um único valor para a propriedade `border-radius` irá definir um mesmo tamanho para todos os quatro cantos.

### Borda Personalizada

É possível criar uma borda personalizada usando uma imagem. Essa imagem precisa ser feita contendo todos os lados da borda e possuir o tamanho de 80x80px.

Para criar a borda, é necessário antes definir uma borda simples como `border: 10px solid black`. A borda personalizada é aplicada a partir da propriedade **`border-image`**, que recebe três valores:

1. `url('caminho/da/borda.png')` (caminho da borda)
1. Repetições
1. Modo de repetição

**Exemplo:**

``` html
<style>
    div {
        border: 10px solid black;
        border-image: url(borda.png) 15 repeat;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ipsa, unde eum exercitationem non corporis blanditiis tempore quisquam possimus expedita architecto vero quia natus voluptatum culpa assumenda totam fuga quaerat ipsum.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta, distinctio! Obcaecati tenetur, delectus dignissimos earum reprehenderit quibusdam doloribus magni nesciunt dolorem odio, sed temporibus ipsam at reiciendis. Excepturi, est ea.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi, enim blanditiis qui doloremque eligendi voluptatum, ipsa iusto similique eum temporibus in perferendis consequatur nesciunt placeat nulla odit hic natus facilis.
        </p>
    </div>
</body>
```

> **NOTA:** A propriedade `border-image` é uma *shorthand* para as propriedades `border-image-source`, `border-image-slice` e `border-image-repeat`.

### Sombras nas Caixas

Para criar sombras nas caixas, é usada a propriedade **`box-shadow`**. Essa propriedade recebe quatro valores:

1. Largura da sombra à direita.
1. Largura da sombra para baixo.
1. Dissipação da sombra.
1. Cor da sombra.

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
        background-color: darkslategray;
    }

    section#principal {
        background-color: white;
        padding: 1em;

        font-family: Arial, Helvetica, sans-serif;
        font-size: 1em;
    }

    h1, h2 {
        font-variant: small-caps;
    }

    p {
        text-indent: 1em;
        text-align: justify;
    }

    aside#sombra {
        background-color: #e0dcdc;
        width: 400px;
        margin: auto;
        padding: 1px 10px;

        /* Sombra */
        box-shadow: 2px 1px 10px #00000073;

        /* Arredondando a borda */
        border-radius: 1em;
    }
</style>
<body>
    <main>
        <section id="principal">
            <h1>Formato da Terra</h1>
            <p>
                A Terra não é uma esfera perfeita. Ela é ligeiramente achatada nos polos e um pouco mais larga no equador, um formato conhecido como elipsoide ou geoide.
            </p>
            <aside id="sombra">
                <h2>Curiosidade</h2>
                <p>
                    Esse achatamento ocorre devido à rotação da Terra. A força centrífuga resultante da rotação faz com que o material no equador se afaste um pouco mais do centro da Terra do que o material nos polos. Como resultado, o diâmetro equatorial da Terra é cerca de 43 quilômetros maior que o diâmetro polar.
                </p>
            </aside>
        </section>
    </main>
</body>
```

### *Outline*

O *outline*, ou o contorno, é parecido com uma borda, porém desenhado no lado de fora. Suas propriedades são as seguintes:

* **'`outline-style`'**: Estilo do contorno.
* **'`outline-color`'**: Cor do contorno.
* **'`outline-width`'**: Largura do contorno.
* **'`outline-offset`'**: Espaço transparente entre o contorno e a borda.
* **'`outline`'** (*shorthand*)

> **NOTA:** A propriedade `outline-offset` não faz parte da *shorthand*, precisando então ser escrita separadamente.

**Exemplo:**

``` html
<style>
    div {
        outline: 2px outset black;
        outline-offset: 10px;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ipsa, unde eum exercitationem non corporis blanditiis tempore quisquam possimus expedita architecto vero quia natus voluptatum culpa assumenda totam fuga quaerat ipsum.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta, distinctio! Obcaecati tenetur, delectus dignissimos earum reprehenderit quibusdam doloribus magni nesciunt dolorem odio, sed temporibus ipsam at reiciendis. Excepturi, est ea.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi, enim blanditiis qui doloremque eligendi voluptatum, ipsa iusto similique eum temporibus in perferendis consequatur nesciunt placeat nulla odit hic natus facilis.
        </p>
    </div>
</body>
```

## Sobreposição de Elementos

A propriedade **`z-index`** espeficifica a ordem em que um elemento fica em um plano de fundo, isso é, se ele vai ficar mais à frente ou atrás de um outro elemento.

Essa propriedade pode ter valores positivos ou negativos, onde o elemento com o menor valor ficará mais atrás e o elemento com maior valor ficará mais à frente.
