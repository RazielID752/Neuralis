# Fetch API

## O que eu preciso lembrar

`fetch` e a API do navegador para fazer requisicoes HTTP.

## GET simples

```ts
async function getUsers() {
  const response = await fetch("/api/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  return response.json();
}
```

## POST com JSON

```ts
async function createUser(user: { name: string }) {
  const response = await fetch("/api/users", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(user),
  });

  if (!response.ok) {
    throw new Error("Erro ao criar usuario");
  }

  return response.json();
}
```

## Tratando erro

```ts
try {
  const users = await getUsers();
  console.log(users);
} catch (error) {
  console.error(error);
}
```

## Pegadinhas

- `fetch` so rejeita em erro de rede, nao em 404/500.
- Preciso checar `response.ok`.
- Para enviar JSON, preciso de `Content-Type` e `JSON.stringify`.
- A resposta pode nao ser JSON.

## Resumo mental

Fetch faz a chamada. Eu ainda preciso cuidar de status, parse, erro e formato.

## Relacionado

- [[HTTP para Frontend]]
- [[Status Codes]]
- [[Camada de API]]

