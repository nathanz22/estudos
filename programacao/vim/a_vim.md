# Vim

## Normal Mode

### Movimentos de Linha

* **'`0`'**: Move para o início da linha.
* **'`$`'**: Move para o final da linha.
* **'`^`'**: Move para o primeiro caractere da linha que não seja em branco.
* **'`g_`'**: Move para o último caractere da linha que não seja em branco.
* **'`gg`'**: Move para o topo do arquivo.
* **'`{linha}gg`'**: Move para a linha especificada.
* **'`G`'**: Move para o final do arquivo.
* **'`%`'**: Move para a ocorrência que corresponde ao abrir/fecha do `({[]})`.

### Movimento entre Palavras

* **'`w`'**: Move para a próxima palavra.
* **'`b`'**: Move para a palavra anterior.
* **'`W`'**: Move para a próxima PALAVRA.
* **'`B`'**: Move para a PALAVRA anterior.

* **'`e`'**: Move para o final da próxima palavra.
* **'`ge`'**: Move para o final da palavra anterior.
* **'`E`'**: Move para o final da próxima PALAVRA.
* **'`gE`'**: Move para o final da PALAVRA anterior.

### Movimento para Caractere Específico

* **'`f{caractere}`'**: Move para a próxima ocorrência do caractere na linha.
* **'`F{caractere}`'**: Move para ocorrência anterior do caractere na linha.

* **'`t{caractere}`'**: Move para um caractere antes da próxima ocorrência do caractere na linha.
* **'`T{caractere}`'**: Move para um caractere depois do próxima ocorrência do caractere na linha.

Para alternar entre as ocorrências do caractere encontrado na linha, use:

### Movimento por Parágrafos

* **'`}`'**: Move para a próxima linha em branco.
* **'`{`'**: Move para a linha em branco anterior.

### Movimento Scrolloing

* **'`CTRL-D`'**: Move meia página para baixo como scrolling.
* **'`CTRL-U`'**: Move meia página para cima como scrolling.

### Pesquisa de Padrão com Movimento Vertical

* **'`/{padrao}`'**: Pesquisa à frente.
* **'`?{padrao}`'**: Pesquisa atrás.

Após encontrar o texto desejado, pressione `ENTER`.

Se houver mais de uma ocorrência, pressione **`n`** ou **`*`** para alternar entre elas. Para retroceder a uma ocorrência, use **`N`**.

### Movimento com Contadores

Um número seguido de um comando multiplica esse comando pelo número. Sintaxe: `{contador}{comando}`.

**Exemplos de comandos são:**

* **'`{n}w`'**: Pula `n` palavras.
* **'`{n}W`'**: Pula `n` PALAVRAS.
* **'`{n}j`'**: Pula `n` linhas.

### Cópia de Linha

Use **`Shift + y`** para copiar a linha atual. Para colar, use **`p`**.

### Excluir Palavras e Linhas

Use **`d`** seguido de um comando para excluir uma quantidade específica de palavras, por exemplo `d5w`, para excluir as próximas cinco palavras.

Para **excluir a linha inteira**, use **`dd`**. **Para excluir a partir do cursor até o final**, use **`D`**.

Para excluir até um determinado caractere, use **`dt{catactere}`**, e para excluir até uma determinada palavra, use **`d/{palavra}`**.

* **'`dd`'**: Exclui tudo que a linha inteira.
* **'`D`'**: Exclui a partir do curso até o final.
* **'`d/{palavra}`'**: Exclui até determinada palavra.
* **'`dG`'**: Exclui tudo no documento a partir do cursor.

### Desfazer e Refazer

* **'`u`'**: Desfaz a última ação.
* **'`CRTL-r`'**: Refaz a última ação desfeita.
