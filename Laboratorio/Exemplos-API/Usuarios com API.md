# Usuarios com API

## Objetivo

Praticar consumo de API com loading, erro, lista e funcoes pequenas.

## API

```txt
https://jsonplaceholder.typicode.com/users
```

## Tipo

```ts
type User = {
  id: number;
  name: string;
  email: string;
  phone: string;
  website: string;
};
```

## Passo 1: buscar usuarios

```ts
async function getUsers(): Promise<User[]> {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  return response.json();
}
```

## Passo 2: transformar usuario para UI

```ts
type UserCardView = {
  id: number;
  title: string;
  subtitle: string;
  websiteUrl: string;
};

function toUserCardView(user: User): UserCardView {
  return {
    id: user.id,
    title: user.name,
    subtitle: user.email,
    websiteUrl: `https://${user.website}`,
  };
}
```

## Passo 3: filtrar por busca

```ts
function filterUsers(users: User[], search: string) {
  const normalizedSearch = search.trim().toLowerCase();

  if (!normalizedSearch) {
    return users;
  }

  return users.filter((user) =>
    user.name.toLowerCase().includes(normalizedSearch)
  );
}
```

## Passo 4: juntar sem embolar

```ts
function getVisibleUsers(users: User[], search: string) {
  return filterUsers(users, search).map(toUserCardView);
}
```

## O que treinar aqui

- `getUsers` so busca dados.
- `toUserCardView` so transforma um usuario.
- `filterUsers` so filtra.
- `getVisibleUsers` junta os passos.

## Exercicio

1. Buscar usuarios.
2. Mostrar loading.
3. Mostrar erro.
4. Criar input de busca.
5. Filtrar usuarios por nome.
6. Transformar dados para `UserCardView`.
7. Renderizar lista.

## Relacionado

- [[Conhecimento/Frontend/Dados/Exemplos de Consumo de API|Exemplos de Consumo de API]]
- [[Conhecimento/Frontend/Logica/Como Quebrar um Problema|Como Quebrar um Problema]]
- [[Conhecimento/Frontend/Logica/Como Criar Funcoes Pequenas|Como Criar Funcoes Pequenas]]

