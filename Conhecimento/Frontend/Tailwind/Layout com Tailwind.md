# Layout com Tailwind

## O que eu preciso lembrar

Tailwind usa classes para aplicar flex, grid, largura, altura e alinhamento.

## Flex

```html
<div class="flex items-center justify-between gap-4">
  ...
</div>
```

- `flex`: ativa flexbox;
- `items-center`: alinha no eixo cruzado;
- `justify-between`: distribui no eixo principal;
- `gap-4`: espaco entre itens.

## Grid

```html
<div class="grid grid-cols-3 gap-4">
  ...
</div>
```

## Largura e container

```html
<main class="mx-auto max-w-5xl px-4">
  ...
</main>
```

- `mx-auto`: centraliza horizontalmente;
- `max-w-5xl`: largura maxima;
- `px-4`: respiro lateral.

## Pegadinhas

- Usar flex quando grid seria mais simples.
- Usar largura fixa demais.
- Esquecer `gap` e tentar resolver com margin em tudo.

## Resumo mental

Layout com Tailwind e o mesmo CSS: flex para uma direcao, grid para duas dimensoes.

## Relacionado

- [[Conhecimento/Frontend/CSS/Flexbox|Flexbox]]
- [[Conhecimento/Frontend/CSS/Grid|Grid]]

