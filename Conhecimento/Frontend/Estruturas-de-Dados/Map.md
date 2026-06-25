# Map

## O que eu preciso lembrar

`Map` guarda pares de chave e valor, parecido com objeto, mas mais apropriado para mapa dinamico.

## Exemplo simples

```ts
const users = new Map();

users.set("1", { id: "1", name: "Ana" });
users.set("2", { id: "2", name: "Marcos" });

console.log(users.get("1"));
```

## Com tipo

```ts
type User = {
  id: string;
  name: string;
};

const usersById = new Map<string, User>();
```

## Quando usar

- buscar item por id;
- cache simples;
- associar chave a valor;
- chave que nao precisa ser string;
- inserir/remover dinamicamente.

## Comparando com array

Array:

```ts
const user = users.find((user) => user.id === id);
```

Map:

```ts
const user = usersById.get(id);
```

## Pegadinhas

- `Map` nao vira JSON diretamente como objeto.
- Para renderizar, preciso converter para array.

```ts
Array.from(usersById.values());
```

## Resumo mental

Map e bom quando eu quero buscar por chave.

## Relacionado

- [[Objeto]]
- [[Complexidade Big O Basico]]

