# Listas e Keys

## O que eu preciso lembrar

Para renderizar lista em React, uso `map`. Cada item precisa de uma `key` estavel.

## Exemplo simples

```tsx
const names = ["Ana", "Marcos", "Joao"];

function NameList() {
  return (
    <ul>
      {names.map((name) => (
        <li key={name}>{name}</li>
      ))}
    </ul>
  );
}
```

## Exemplo com objetos

```tsx
type User = {
  id: string;
  name: string;
};

function UserList({ users }: { users: User[] }) {
  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

## Por que key existe

`key` ajuda o React a saber qual item e qual quando a lista muda.

Use ID estavel:

```tsx
<li key={user.id}>{user.name}</li>
```

Evite indice se a lista pode mudar:

```tsx
items.map((item, index) => <li key={index}>{item.name}</li>)
```

## Pegadinhas

- `key` deve ficar no primeiro elemento retornado pelo `map`.
- Key precisa ser unica entre irmaos.
- Indice como key pode causar bug visual quando remove/reordena.

## Resumo mental

Lista em React e `array.map`. Key e identidade do item.

## Relacionado

- [[Conhecimento/Frontend/JavaScript/Arrays e Objetos|Arrays e Objetos]]
- [[State]]

