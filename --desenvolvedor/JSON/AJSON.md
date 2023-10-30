# JSON

Significa "JavaScript Object Notation", e é um formato de dados leve e de fácil leitura.

Em JSON, os dados são representados em pares de chave-valor.

``` json
{
    "nome": "JS",
    "idade": 21,
    "peso": "93.3kg",
    "casado": false,
    "hobbies": ["esportes", "programação"]
}
```

É uma linguagem independente, e por esse motivo, pode ser usado em conjunto com diversas outras linguagens.

## Uso do JSON

JSON é usado em uma variedade de situações:

* Transferência de dados entre servidor e cliente.
* Armazenamento de configurações.
* Armazenamento de dados de maneira estruturada.
* Troca de informações entre aplicativos.

## Tipos de Dados em JSON

JSON suporta vários tipos de dados, como números, strings, booleanos, objetos, arrays e valores nulos.

``` json
{
    "str": "Olá, Mundo!",

    "num_int": 5,
    "num_float": 2.3,

    "verdadeiro": true,
    "falso": false,

    "obj": {
        "valor1": "Olá, Mundo!",
        "valor2": "Olá, JSON!"
    },

    "array": [0, 2.3, true, null, "Olá"],

    "nulo": null
}
```

> Strings em JSON devem sempre estar entre aspas duplas.
