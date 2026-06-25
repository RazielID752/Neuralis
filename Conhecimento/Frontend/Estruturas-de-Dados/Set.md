# Set

## O que eu preciso lembrar

`Set` guarda valores unicos.

Ele nao deixa duplicar.

## Exemplo simples

```ts
const ids = new Set();

ids.add("1");
ids.add("1");
ids.add("2");

console.log(ids); // 1, 2
```

## Remover duplicados

```ts
const numbers = [1, 1, 2, 3, 3];
const uniqueNumbers = [...new Set(numbers)];
```

## Verificar se existe

```ts
selectedIds.has("1");
```

## Quando usar

- ids selecionados;
- tags unicas;
- remover duplicados;
- verificar existencia rapidamente.

## Exemplo em frontend

```ts
const selectedIds = new Set<string>();

selectedIds.add("task-1");
selectedIds.delete("task-1");
selectedIds.has("task-1");
```

## Pegadinhas

- `Set` nao tem indice.
- Para renderizar, converto para array.
- Em React, preciso criar novo Set para atualizar state.

```ts
setSelectedIds((current) => new Set(current).add(id));
```

## Resumo mental

Set e lista sem repetição.

## Relacionado

- [[Array]]
- [[Map]]

