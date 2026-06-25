# Tailwind Merge

## O que eu preciso lembrar

Tailwind Merge ajuda a resolver conflito de classes Tailwind.

## Problema

```tsx
"px-2 px-4"
```

As duas classes definem padding horizontal. A ultima vence, mas em componentes isso pode ficar confuso.

## Ideia

```ts
twMerge("px-2 py-2", "px-4")
```

Resultado mental:

```txt
py-2 px-4
```

## Quando usar

- componente recebe `className`;
- variantes podem conflitar;
- quero permitir sobrescrita externa.

## Pegadinhas

- Nao usar para esconder design bagunçado.
- Ainda preciso organizar variantes.
- Nao substitui bom componente.

## Resumo mental

Tailwind Merge limpa conflitos quando classes vêm de lugares diferentes.

## Relacionado

- [[Componentizacao com Tailwind]]
- [[Variantes com clsx]]

