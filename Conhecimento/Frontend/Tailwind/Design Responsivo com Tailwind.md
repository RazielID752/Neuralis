# Design Responsivo com Tailwind

## O que eu preciso lembrar

Tailwind e mobile-first.

Classe sem prefixo vale para todos os tamanhos. Prefixos como `md:` e `lg:` aplicam a partir daquele breakpoint.

## Exemplo simples

```html
<section class="grid gap-4 md:grid-cols-2 lg:grid-cols-3">
  ...
</section>
```

Leitura:

- mobile: uma coluna;
- `md`: duas colunas;
- `lg`: tres colunas.

## Texto responsivo

```html
<h1 class="text-2xl md:text-4xl">
  Titulo
</h1>
```

## Layout responsivo

```html
<div class="flex flex-col gap-4 md:flex-row">
  ...
</div>
```

No mobile fica coluna. Em `md`, vira linha.

## Pegadinhas

- Achar que `md:` vale so no tamanho medio. Na verdade vale de `md` para cima.
- Criar desktop primeiro e depois tentar consertar mobile.
- Usar largura fixa demais.

## Resumo mental

Sem prefixo e mobile. Com prefixo, muda a partir daquele tamanho.

## Relacionado

- [[Layout com Tailwind]]
- [[Conhecimento/Frontend/CSS/Responsividade|Responsividade]]

