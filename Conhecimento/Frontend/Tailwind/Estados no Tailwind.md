# Estados no Tailwind

## O que eu preciso lembrar

Estados no Tailwind usam prefixos como `hover:`, `focus-visible:` e `disabled:`.

## Hover

```html
<button class="bg-black text-white hover:bg-neutral-800">
  Salvar
</button>
```

## Focus

```html
<button class="focus-visible:outline focus-visible:outline-2 focus-visible:outline-blue-500">
  Salvar
</button>
```

## Disabled

```html
<button class="disabled:cursor-not-allowed disabled:opacity-50">
  Salvar
</button>
```

## Combinando estados

```html
<button class="rounded bg-black px-4 py-2 text-white hover:bg-neutral-800 focus-visible:outline focus-visible:outline-2 disabled:opacity-50">
  Salvar
</button>
```

## Pegadinhas

- Fazer hover e esquecer focus.
- Remover outline sem alternativa.
- Disabled parecer normal.

## Resumo mental

Estado visual ajuda o usuario a entender se algo e clicavel, focado ou desabilitado.

## Relacionado

- [[Conhecimento/Frontend/CSS/Estados Visuais CSS|Estados Visuais CSS]]

