# Arrays e Objetos

## Explicacao em uma frase

Arrays guardam listas, objetos guardam dados em pares de chave e valor.

## Arrays

```js
const frutas = ["Maca", "Banana", "Laranja"];
```

Acessando item:

```js
console.log(frutas[0]); // Maca
```

Adicionando item:

```js
frutas.push("Uva");
```

## `map`

`map` transforma cada item e devolve um novo array.

```js
const frutas = ["Maca", "Banana", "Laranja"];

const novaLista = frutas.map((fruta) => fruta.toUpperCase());

console.log(novaLista);
```

## `filter`

`filter` mantem apenas os itens que passam em uma condicao.

```js
const numeros = [1, 2, 3, 4, 5];

const pares = numeros.filter((numero) => numero % 2 === 0);
```

## `find`

`find` encontra o primeiro item que passa em uma condicao.

```js
const usuarios = [
  { id: 1, nome: "Ana" },
  { id: 2, nome: "Marcos" },
];

const usuario = usuarios.find((usuario) => usuario.id === 2);
```

## Objetos

```js
const pessoa = {
  nome: "Carlos",
  idade: 30,
  cidade: "SP",
};

console.log(pessoa.nome);
```

Alterando propriedade:

```js
pessoa.idade = 31;
```

Criando novo objeto:

```js
const pessoaAtualizada = {
  ...pessoa,
  idade: 31,
};
```

## JSON

JSON e um formato de texto para troca de dados.

Objeto para JSON:

```js
const json = JSON.stringify(pessoa);
console.log(json);
```

JSON para objeto:

```js
const objeto = JSON.parse(json);
console.log(objeto);
```

## Por que isso importa para React

Em React, listas e objetos aparecem o tempo todo:

- lista de produtos;
- usuario logado;
- tarefas;
- configuracoes;
- resposta de API.

Voce precisa saber transformar arrays sem baguncar o dado original.

## Relacionado

- [[Loops]]
- [[Funcoes e Callbacks]]
- [[Conhecimento/Frontend/React/State|State]]

