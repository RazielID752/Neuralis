# Imutabilidade

## O que eu preciso lembrar

Imutabilidade e mudar dados criando uma nova versao, sem alterar o original diretamente.

## Por que importa

Em React, imutabilidade ajuda a detectar mudancas.

Ruim:

```js
const user = { name: "Ana", age: 20 };
user.age = 21;
```

Melhor:

```js
const updatedUser = {
  ...user,
  age: 21,
};
```

## Array

Adicionar:

```js
const next = [...items, newItem];
```

Remover:

```js
const next = items.filter((item) => item.id !== id);
```

Atualizar:

```js
const next = items.map((item) =>
  item.id === id ? { ...item, done: !item.done } : item
);
```

## Pegadinhas

- `push`, `splice`, `sort` mutam array.
- Spread copia raso, nao profundo.
- Mutar state em React pode nao renderizar como esperado.

## Resumo mental

Nao mexo no dado antigo. Crio um novo dado com a alteracao.

## Relacionado

- [[Arrays e Objetos]]
- [[Conhecimento/Frontend/React/State|State]]

