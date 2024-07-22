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

### Combinadores

Os combinadores são usados para selecionar um seletor específico.

#### Combinador `>`

Indica que um elemento está imediatamente dentro de outro.

**Sintaxe:**

``` css
e1 > e2 > e3 {
    /* Propriedades */
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div > h1 {
        margin-left: 0.5em;
        font-size: 3em;
    }

    div > p {
        margin-left: 15px;
        font-family: Arial, Helvetica, sans-serif;
    }

    div > p > a {
        text-decoration: none;
        color: darkred;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem <a href="#">ipsum</a> dolor sit amet consectetur adipisicing elit. Quo reprehenderit porro at facilis eum, sequi eveniet itaque voluptatibus totam, commodi culpa iste cumque quibusdam error id molestiae. Nesciunt, aperiam quam?
        </p>
    </div>
</body>
```

O mesmo pode ser feito sem especificar o caminho inteiro até o elemento, não sendo mais necessário usar `>`.

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div h1 {
        margin-left: 0.5em;
        font-size: 3em;
    }

    div p {
        margin-left: 15px;
        font-family: Arial, Helvetica, sans-serif;
    }

    div a {
        text-decoration: none;
        color: darkred;
    }
</style>
<body>
    <div>
        <h1>Título</h1>
        <p>
            Lorem <a href="#">ipsum</a> dolor sit amet consectetur adipisicing elit. Quo reprehenderit porro at facilis eum, sequi eveniet itaque voluptatibus totam, commodi culpa iste cumque quibusdam error id molestiae. Nesciunt, aperiam quam?
        </p>
    </div>
</body>
```

#### Combinador `+`

Faz referência ao seu irmão adjacente, ou seja, o próximo seletor que compartilha o mesmo elemento pai será afetado.

**Exemplo:**

``` html
<style>
    h1 + p {
        font-family: Arial, Helvetica, sans-serif;
        color: blue;
    }
</style>
<body>
    <h1>Título</h1>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque quae id nostrum suscipit omnis debitis molestias placeat! Id, temporibus vel fugiat aperiam aut reprehenderit aspernatur vero cum quis, tempore eius.
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque deserunt praesentium consequatur, id dicta quaerat, est at quis ex neque nobis molestias illo veritatis minus cupiditate, eius minima nam harum?
    </p>
</body>
```

#### Combinador `~`

Seleciona todos os elementos após o elemento anterior dentro de um mesmo elemento pai.

**Exemplo:**

``` html
<style>
    h1 ~ p ~ p {
        font-family: Arial, Helvetica, sans-serif;
        color: blue;
    }
</style>
<body>
    <h1>Título</h1>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque quae id nostrum suscipit omnis debitis molestias placeat! Id, temporibus vel fugiat aperiam aut reprehenderit aspernatur vero cum quis, tempore eius.
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque deserunt praesentium consequatur, id dicta quaerat, est at quis ex neque nobis molestias illo veritatis minus cupiditate, eius minima nam harum?
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium alias, at perspiciatis dicta velit non quis repellat. Necessitatibus libero dolorem at eaque repellendus, maxime itaque esse, nobis sed, ex odit?
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

## Medidas

Existem diferentes medidas para definir tamanhos, e as mais recomendadas são **`em`** e **`px`**, além de **`%`** e **`vh`**.

**As medidas são:**

* **'`px`' (pixels)**: É a medida mais comum e representa um pixel na tela.
* **'`em`'**: É relativa à altura do elemento pai. Por exemplo, se o tamanho da fonte do elemento pai for 16 pixels, por padrão, `font-size: 1.5em;` definirá o tamanho da fonte como 24 pixels (1,5 vezes o tamanho da fonte do elemento pai).
* **'`rem`'**: Relativa ao tamanho do elemento raiz, definido em `html`.
* **'`%`' (porcentagem)**: É relativo ao valor de referência.
* **'`vw`'**: É relativa à largura da janela de visualização (viewport).
* **'`vh`'**: É relativa à altura da janela de visualização (viewport).

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

## Controle Sobre Conteúdo Transbordado

A propriedade **`overflow`** controla o que o acontece com o conteúdo muito grande.

**Seus valores são:**

* **'`visible`'**: O conteúdo é cortado, e o conteúdo renderiza mesmo fora da caixa (valor padrão).
* **'`hidden`'**: O conteúdo é cortado, e o conteúdo fora da caixa se torna invisível.
* **'`scroll`'**: O conteúdo é cortado, e é adicionado uma barra de rolagem lateral para possibilitar a leitura do conteúdo.
* **'`auto`'**: Parecido com `scroll`, porém adiciona uma barra de rolagem somente se necessário.

## Elementos Flutuantes

A propriedade **`float`** é posiciona e formata o conteúdo, permitindo posicioná-lo em uma direção.

**Seus valores são:**

* **'`none`'**: O elemento não irá flutuar (valor padrão).
* **'`left`'**: O elemento será posicionado mais à esquerda no container.
* **'`right`'**: O elemento será posicionado mais à direita no container.

**Exemplo:**

``` html
<style>
    div#caixa1 {
        width: 500px;
        height: 200px;
        background-color: blue;

        float: right;
    }

    div#caixa2 {
        width: 400px;
        height: 200px;
        background-color: blueviolet;

        float: left;
    }

    div#caixa3 {
        width: 300px;
        height: 200px;
        background-color: darkred;

        float: right;
    }
</style>
<body>
    <div id="caixa1"></div>
    <div id="caixa2"></div>
    <div id="caixa3"></div>
</body>
```

A propriedade **`clear`** determina como um elemento se comporta em relação a elementos flutuantes ao redor.

**Seus valores são:**

* **'`none`'**: O elemento não será colocado abaixo dos elementos flutuantes (valor padrão).
* **'`left`'**: O elemento será empurrado para baixo dos elementos flutuantes à esquerda.
* **'`right`'**: O elemento será empurrado para baixo dos elementos flutuantes à direita.
* **'`both`'**: O elemento será empurrado para baixo dos elementos flutuantes à esquerda e à direita.

## Variáveis

Para criar uma variável em CSS, é  necessário criar um seletor especial chamado **`:root`**. As propriedades desse seletor serão as variáveis, e devem ser escritas com dois hífens (`--`) antes do nome, e o valores dessas propriedades são os valores das variáveis.

**Sintaxe:**

``` css
:root {
    --var1: valor;
    --var2: valor;
    /* ... */
    --varN: valor;
}
```

Ao aplicar uma variável a um elemento, é necessário usar **`var(--variável)`**.

**Exemplo:**

``` html
<style>
    :root {
        --cor1: #aa0101;
        --cor2: #e9e93a;
        --cor3: #2828fa;
    }

    #vermelho {
        color: var(--cor1);
    }

    #amarelo {
        color: var(--cor2);
    }

    #azul {
        color: var(--cor3);
    }
</style>
<body>
    <h1>Título</h1>
    <p id="vermelho">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque quae id nostrum suscipit omnis debitis molestias placeat! Id, temporibus vel fugiat aperiam aut reprehenderit aspernatur vero cum quis, tempore eius.
    </p>
    <p id="amarelo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque deserunt praesentium consequatur, id dicta quaerat, est at quis ex neque nobis molestias illo veritatis minus cupiditate, eius minima nam harum?
    </p>
    <p id="azul">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium alias, at perspiciatis dicta velit non quis repellat. Necessitatibus libero dolorem at eaque repellendus, maxime itaque esse, nobis sed, ex odit?
    </p>
</body>
```

## Posições

O posicionamento de um elemento é definido pela propriedade **`position`**, que pode receber cinco valores:

* **'`static`'**: Alinhamento no canto superior esquerdo do corpo do documento (posicionamento padrão).
* **'`fixed`'**: Fixa o elemento na tela, não deixando-o se mover. Ele se mantém fixo mesmo com a rolagem da página.
* **'`sticky`'**: Fixa o elemento na tela em relação ao rolamento da página.
* **'`absolute`'**: O posicionamento absoluto possui dois comportamentos diferentes:
    1. O primeiro é quando o elemento com esse valor possui um elemento pai de valor diferente de `static`, usando esse elemento como referência para ser posicionado.

    1. O segundo é quando o elemento absoluto não possui pai, ou o elemento pai possui o valor `static`. Nesse caso, ele irá ser posicionado no canto superior esquerdo do documento, podendo ser sobreposto.

* **'`relative`'**: Altera a posição do elemento com base na posição inicial dele. Essa posição permite manipular a posição por meio das propriedades **`top`** e **`left`**.

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        position: absolute;
        width: 600px;
        height: 300px;
        background-color: darkslategray;
    }

    div#content {
        position: relative;
        background-color: gray;
        width: 250px;
        height: 250px;
        top: 50%;
        left: 50%;

        transform: translate(-50%, -50%);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```

No exemplo acima, o elemento `content` é centralizado vertical e horizontalmente dentro do elemento `container`. Isso é feito com a posição **`absolute`** para o elemento pai, e a posição **`relative`** para o elemento filho.

> **NOTA:** A propriedade `transform` com o valor `translate(-50%, -50%)` foi usada para alterar o eixo de referência para a centralização no centro do elemento.

## Transformações

As transformações permitem alterar a posição, o tamanho, a rotação e a perspectiva dos elementos, oferecendo maneiras de manipular elementos no espaço 2D e 3D.

Tudo isso é feito com a propriedade **`transform`**, que possui como valores algumas funções.

### Transformações em 2D

#### Translação

A função **`translate()`** move o elemento em uma determinada direção. Aceita dois argumento, sendo eles os valores de translação para o eixo X e Y, respectivamente.

**Sintaxe:**

``` css
#elemento {
    transform: translate(X, Y);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        width: 600px;
        height: 300px;
        background-color: darkslategray;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;

        transform: translate(160px, 21px);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```

#### Rotação

A função **`rotate()`** gira um elemento em torno de um ponto de referência, definindo o ângulo de rotação em graus.

**Sintaxe:**

``` css
#elemento {
    transform: rotate(Xdeg);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;
        margin: 80px;

        transform: rotate(45deg);
    }
</style>
<body>
    <div id="content"></div>
</body>
```

No exemplo acima, o elemento `content`, que é um quadrado, é rotacionado em 45 graus no sentido horário.

#### Escala

A função **`scale()`** altera o tamanho do elemento por meio de dois argumentos: escala horizontal e escala vertical, respectivamente;

**Sintaxe:**

``` css
#elemento {
    transform: scale(X, Y);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;
        margin: 80px;

        transform: scale(4, 2);
    }
</style>
<body>
    <div id="content"></div>
</body>
```

No exemplo acima, o eixo X é aumentado 4 vezes, enquanto o eixo Y é aumentado 2 vezes.

#### Inclinação

A função **`skew()`** aplica uma inclinação ao elemento. Aceita valores para os eixos X e/ou Y, e permite distorcer a forma do elemento em um ângulo específico.

**Sintaxe:**

``` css
#seletor {
    transform: skew(Xdeg, Ydeg);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;
        margin: 80px;

        transform: skew(20deg, -10deg);
    }
</style>
<body>
    <div id="content"></div>
</body>
```

#### Matriz 2D

A função **`matrix()`** define transformações 2D personalizadas usando uma matriz 4x4. Os valores da matriz definem as transformações de translação, escala e inclinação.

**Sintaxe:**

``` css
#elemento {
    transform: matrix(a, b, c, d, e, f);
}
/*
[a, c, e]
[b, d, f]
[0, 0, 1]
*/
```

* **``a``** e **``d``**: Escala no eixo X e Y, respectivamente.
* **``b``** e **``c``**: Inclinação (skew) no eixo Y e X, respectivamente.
* **``e``** e **``f``**: Translação no eixo X e Y, respectivamente.

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;
        margin: 80px;

        transform: matrix(1, 0.5, -0.5, 0, 0, 0);
    }
</style>
<body>
    <div id="content"></div>
</body>
```

### Múltiplas Transformações

É possível aplicar múltiplas transformações em uma única declaração **`transform`**. Para isso, basta separar as funções com espaço.

**Exemplo:**

``` css
#elemento {
    transform: translate(-50px, -50px) rotate(45deg) scale(2.5, 3);
}
```

### Transformações em 3D

As funções de transformação 3D são usadas junto à propriedade **`perspective`**, que deve ser aplicada no elemento pai do elemento em que serão aplicadas as transformações 3D. Isso é feito para criar a ilusão de profundidade e tridimensionalidade.

**Sintaxe:**

``` css
#elemento-pai {
    perspective: valor;
}
```

O valor deve ser especificado em alguma unidade de medida, como por exemplo `1000px`.

#### Translação 3D

A função **`translate3d()`** se assemelha à função `translate`, mas aceita também o eixo Z.

**Sintaxe:**

``` css
#elemento {
    transform: translate3d(X, Y, Z);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        background-color: darkslategrey;
        width: 600px;
        height: 300px;
        perspective: 1000px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;

        transform: translate3d(100px, 10%, 50px);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```

#### Rotação 3D

A função **`rotate3d()`** permite realizar rotações em três dimensões. Devem ser definidos os eixos X, Y, Z e o ângulo como argumentos.

**Sintaxe:**

``` css
#elemento {
    transform: rotate3d(X, Y, Z, angulo);
}
```

Os eixos apresentam os componentes do vetor de eixo em torno do qual a rotação será aplicada. Esses valores podem variar de -1 a 1, e definem a direção do eixo.

O último argumento é o ângulo de rotação em graus.

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        background-color: darkslategrey;
        width: 600px;
        height: 300px;
        perspective: 1000px;
        margin: 30px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;

        transform: rotate3d(0, 1, -1, -20deg);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```

#### Escala 3D

A função **`scale3d()`** é semelhante à função `scale()`, mas recebe também o valor do eixo Z além de X e Y.

**Sintaxe:**

``` css
#elemento {
    transform: scale3d(X, Y, Z);
}
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        background-color: darkslategrey;
        width: 600px;
        height: 300px;
        perspective: 1000px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;
        margin: auto;

        transform: scale3d(2, 1.5, 0.5);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```

#### Matriz 3D

A função **`matrix3d()`** recebe todos os dezesseis valores da matriz para obter o efeito de transformação desejado.

**Sintaxe:**

``` css
#elemento {
    transform: matrix3d(m11, m12, m13, m14, m21, m22, m23, m24, m31, m32, m33, m34, m41, m42, m43, m44);
}
/*
[m11, m12, m13, m14]
[m21, m22, m23, m24]
[m31, m32, m33, m34]
[m41, m42, m43, m44]
*/
```

**Exemplo:**

``` html
<style>
    body {
        margin: 0px;
        padding: 0px;
    }

    div#container {
        background-color: darkslategrey;
        width: 600px;
        height: 300px;
        perspective: 1000px;
    }

    div#content {
        background-color: gray;
        width: 250px;
        height: 250px;

        transform: matrix3d(1.299, 0.75, 0, 0, -0.75, 1.299, 0, 0, 0, 0, 1, 0, 50, 0, 0, 1);
    }
</style>
<body>
    <div id="container">
        <div id="content"></div>
    </div>
</body>
```
