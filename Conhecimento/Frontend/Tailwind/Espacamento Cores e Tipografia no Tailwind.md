# Espacamento, Cores e Tipografia no Tailwind

## O que eu preciso lembrar

Tailwind tem classes pequenas para valores comuns de espaco, cor e texto.

## Espacamento

```html
<div class="p-4 m-2">
  Conteudo
</div>
```

- `p`: padding;
- `m`: margin;
- `px`: padding horizontal;
- `py`: padding vertical;
- `gap`: espaco entre itens.

Exemplo:

```html
<div class="flex gap-4 p-6">
  ...
</div>
```

## Cores

```html
<div class="bg-white text-neutral-900 border border-neutral-200">
  Conteudo
</div>
```

## Tipografia

```html
<h1 class="text-3xl font-bold">
  Titulo
</h1>

<p class="text-sm leading-6 text-neutral-600">
  Texto de apoio
</p>
```

## Pegadinhas

- Usar muitos tamanhos diferentes sem padrao.
- Escolher cor nova para cada componente.
- Esquecer contraste.
- Usar texto pequeno demais.

## Resumo mental

Espacamento organiza. Cor comunica. Tipografia cria hierarquia.

## Relacionado

- [[Utility First]]
- [[Tema e Configuracao do Tailwind]]

