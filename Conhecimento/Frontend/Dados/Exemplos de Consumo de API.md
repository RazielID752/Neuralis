# Exemplos de Consumo de API

## O que eu preciso lembrar

Consumir API nao e so chamar `fetch`.

Eu preciso pensar no fluxo inteiro:

1. chamar API;
2. checar status;
3. converter JSON;
4. tratar erro;
5. mostrar loading;
6. mostrar vazio;
7. mostrar sucesso.

## Exemplo 1: GET simples

```ts
async function getUsers() {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  const users = await response.json();
  return users;
}

getUsers()
  .then((users) => console.log(users))
  .catch((error) => console.error(error));
```

## Exemplo 2: Tipando resposta

```ts
type User = {
  id: number;
  name: string;
  email: string;
};

async function getUsers(): Promise<User[]> {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  const users = await response.json();
  return users;
}
```

## Pegadinha importante

Esse tipo:

```ts
Promise<User[]>
```

ajuda o TypeScript, mas nao valida se a API realmente mandou `User[]`.

Para validar em runtime, preciso de checagem manual ou schema.

## Exemplo 3: POST

```ts
type CreatePostInput = {
  title: string;
  body: string;
  userId: number;
};

async function createPost(input: CreatePostInput) {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(input),
  });

  if (!response.ok) {
    throw new Error("Erro ao criar post");
  }

  return response.json();
}
```

Uso:

```ts
createPost({
  title: "Meu post",
  body: "Conteudo do post",
  userId: 1,
});
```

## Exemplo 4: Camada de API

Em vez de chamar `fetch` direto em todo componente, crio uma funcao.

```ts
const API_URL = "https://jsonplaceholder.typicode.com";

export type User = {
  id: number;
  name: string;
  email: string;
};

export async function getUsers(): Promise<User[]> {
  const response = await fetch(`${API_URL}/users`);

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  return response.json();
}
```

## Exemplo 5: React consumindo API

```tsx
import { useEffect, useState } from "react";

type User = {
  id: number;
  name: string;
  email: string;
};

async function getUsers(): Promise<User[]> {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  return response.json();
}

export function UsersPage() {
  const [users, setUsers] = useState<User[]>([]);
  const [isLoading, setIsLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);

  useEffect(() => {
    async function loadUsers() {
      try {
        setIsLoading(true);
        setError(null);

        const data = await getUsers();
        setUsers(data);
      } catch {
        setError("Nao foi possivel carregar usuarios.");
      } finally {
        setIsLoading(false);
      }
    }

    loadUsers();
  }, []);

  if (isLoading) {
    return <p>Carregando...</p>;
  }

  if (error) {
    return <p role="alert">{error}</p>;
  }

  if (users.length === 0) {
    return <p>Nenhum usuario encontrado.</p>;
  }

  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>
          <strong>{user.name}</strong>
          <span>{user.email}</span>
        </li>
      ))}
    </ul>
  );
}
```

## O que observar nesse exemplo

- `users`: dados de sucesso.
- `isLoading`: estado de carregamento.
- `error`: mensagem de erro.
- `useEffect`: dispara busca quando componente monta.
- `try/catch/finally`: controla fluxo.
- `if`: renderiza estados diferentes.

## Exemplo 6: Estado como union

Quando quero evitar varios states soltos:

```ts
type AsyncState<T> =
  | { status: "loading" }
  | { status: "error"; message: string }
  | { status: "success"; data: T };
```

Uso:

```tsx
const [state, setState] = useState<AsyncState<User[]>>({
  status: "loading",
});
```

Render:

```tsx
if (state.status === "loading") return <p>Carregando...</p>;
if (state.status === "error") return <p>{state.message}</p>;

return (
  <ul>
    {state.data.map((user) => (
      <li key={user.id}>{user.name}</li>
    ))}
  </ul>
);
```

## Pegadinhas

- Esquecer `response.ok`.
- Nao tratar loading.
- Nao tratar erro.
- Achar que TypeScript valida JSON sozinho.
- Fazer fetch em varios componentes sem camada comum.
- Nao cancelar/ignorar request antiga em casos mais complexos.

## Resumo mental

Consumo de API bom tem caminho feliz e caminho ruim. Eu preciso escrever os dois.

## Exercicios para fixar

1. Busque posts do JSONPlaceholder.
2. Mostre loading enquanto carrega.
3. Mostre erro se falhar.
4. Mostre mensagem se vier lista vazia.
5. Separe a chamada em uma funcao `getPosts`.
6. Tipe `Post`.

## Relacionado

- [[Fetch API]]
- [[Camada de API]]
- [[Estados de UI Loading Empty Error Success]]
- [[TypeScript com React]]

