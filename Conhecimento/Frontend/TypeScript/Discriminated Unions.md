# Discriminated Unions

## O que eu preciso lembrar

Discriminated union e uma union de objetos que usa um campo para identificar qual caso esta ativo.

Normalmente o campo se chama `status`, `type` ou `kind`.

## Exemplo

```ts
type AsyncState<T> =
  | { status: "loading" }
  | { status: "error"; message: string }
  | { status: "success"; data: T };
```

## Por que ajuda

Impede estados impossiveis.

Ruim:

```ts
type State = {
  isLoading: boolean;
  error: string | null;
  data: User[] | null;
};
```

Esse modelo permite combinações estranhas:

- `isLoading: true` com `data`;
- `error` e `data` ao mesmo tempo;
- nada definido.

Melhor:

```ts
type State =
  | { status: "loading" }
  | { status: "error"; message: string }
  | { status: "success"; data: User[] };
```

## Renderizando

```tsx
if (state.status === "loading") return <p>Carregando...</p>;
if (state.status === "error") return <p>{state.message}</p>;

return <UserList users={state.data} />;
```

## Pegadinhas

- Esquecer de tratar um caso.
- Criar nomes de status vagos.
- Colocar campos opcionais demais e perder o beneficio.

## Resumo mental

Discriminated union deixa cada estado carregar apenas os dados que fazem sentido nele.

## Relacionado

- [[Union Types e Literal Types]]
- [[Narrowing]]

