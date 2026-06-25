# useReducer

## O que eu preciso lembrar

`useReducer` ajuda quando state tem varias transicoes ou regras.

## Modelo mental

```txt
estado atual + acao -> novo estado
```

## Exemplo

```tsx
type State = {
  count: number;
};

type Action =
  | { type: "increment" }
  | { type: "decrement" }
  | { type: "reset" };

function reducer(state: State, action: Action): State {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    case "reset":
      return { count: 0 };
  }
}
```

Uso:

```tsx
const [state, dispatch] = useReducer(reducer, { count: 0 });
```

## Quando usar

- state complexo;
- muitas ações;
- transições previsiveis;
- quando varios `useState` ficam confusos.

## Quando nao usar

- state simples;
- input pequeno;
- boolean local.

## Resumo mental

`useReducer` organiza mudanças de state por ações nomeadas.

## Relacionado

- [[State]]
- [[Discriminated Unions]]

