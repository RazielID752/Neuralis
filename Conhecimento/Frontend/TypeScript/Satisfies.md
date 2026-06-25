# Satisfies

## O que eu preciso lembrar

`satisfies` verifica se um valor cumpre um tipo sem perder a inferencia especifica do valor.

## Exemplo

```ts
type Route = {
  path: string;
  label: string;
};

const routes = [
  { path: "/", label: "Home" },
  { path: "/about", label: "Sobre" },
] satisfies Route[];
```

## Por que usar

Com `satisfies`, TypeScript confere o formato, mas preserva melhor os valores literais.

## Exemplo com config

```ts
type ThemeConfig = {
  colors: Record<string, string>;
};

const theme = {
  colors: {
    primary: "#000",
    danger: "#f00",
  },
} satisfies ThemeConfig;
```

## Pegadinhas

- `satisfies` nao transforma valor em runtime.
- Nao substitui validação de API.
- E mais util em configs e objetos constantes.

## Resumo mental

`satisfies` e bom quando quero checar formato sem perder detalhes do objeto.

## Relacionado

- [[Type Alias vs Interface]]
- [[Utility Types]]

