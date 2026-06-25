# Array

## O que eu preciso lembrar

Array e uma lista ordenada de itens.

Uso quando tenho varios valores em sequência.

## Exemplo simples

```ts
const frutas = ["maca", "banana", "laranja"];
```

## Acessar item

```ts
console.log(frutas[0]); // maca
```

Array começa no indice `0`.

## Adicionar item

```ts
const novaLista = [...frutas, "uva"];
```

Em React, prefiro criar novo array em vez de mutar.

## Remover item

```ts
const semBanana = frutas.filter((fruta) => fruta !== "banana");
```

## Transformar item

```ts
const maiusculas = frutas.map((fruta) => fruta.toUpperCase());
```

## Quando usar array

- lista de produtos;
- lista de usuarios;
- lista de tarefas;
- itens de menu;
- resultados de busca.

## Pegadinhas

- `push` muda o array original.
- `sort` muda o array original.
- Indice muda quando remove item.
- Buscar por id com `find` em lista gigante pode ser menos eficiente.

## Resumo mental

Array e lista. Se eu preciso percorrer, filtrar ou renderizar varios itens, provavelmente e array.

## Relacionado

- [[Conhecimento/Frontend/JavaScript/Arrays e Objetos|Arrays e Objetos]]
- [[Set]]
- [[Map]]

