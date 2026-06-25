# Variantes com clsx

## O que eu preciso lembrar

Quando classes dependem de condição, eu preciso organizar para nao virar bagunça.

## Problema

```tsx
<button
  className={`rounded px-4 py-2 ${
    variant === "primary" ? "bg-black text-white" : "bg-white text-black"
  }`}
>
  Salvar
</button>
```

Funciona, mas pode crescer.

## Ideia com clsx

```tsx
const className = clsx(
  "rounded px-4 py-2",
  variant === "primary" && "bg-black text-white",
  variant === "secondary" && "bg-white text-black border"
);
```

## Quando usar

- variantes;
- estado ativo;
- erro;
- disabled;
- tamanho.

## Pegadinhas

- Condicional demais dentro do JSX.
- Repetir variantes em vários componentes.
- Não padronizar nomes.

## Resumo mental

Se classe depende de estado, organizo a condição fora do caos visual.

## Relacionado

- [[Componentizacao com Tailwind]]

