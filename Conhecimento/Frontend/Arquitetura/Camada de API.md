# Camada de API

## O que eu preciso lembrar

Camada de API centraliza como o frontend conversa com o backend.

## Sem camada de API

```tsx
fetch("/api/users")
  .then((response) => response.json())
  .then(setUsers);
```

Isso espalhado por varios componentes vira bagunca.

## Com camada de API

```ts
export async function getUsers() {
  const response = await fetch("/api/users");

  if (!response.ok) {
    throw new Error("Erro ao buscar usuarios");
  }

  return response.json();
}
```

Componente:

```tsx
useEffect(() => {
  getUsers().then(setUsers).catch(setError);
}, []);
```

## O que pode ficar na camada de API

- URL base;
- headers;
- token;
- tratamento de erro HTTP;
- parse de JSON;
- tipos de resposta;
- funcoes por recurso.

## Pegadinhas

- Tratar erro diferente em cada tela.
- Repetir URL por todo lado.
- Nao verificar `response.ok`.
- Confiar cegamente no formato da API.

## Resumo mental

Componente nao deveria saber detalhes demais de HTTP. Ele deveria pedir dados.

## Relacionado

- [[Client State vs Server State]]
- [[Tratamento de Erros no Frontend]]

