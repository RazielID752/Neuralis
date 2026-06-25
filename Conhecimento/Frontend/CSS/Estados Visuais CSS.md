# Estados Visuais CSS

## O que eu preciso lembrar

Estados visuais mostram que algo pode ser clicado, focado, ativado ou esta desabilitado.

## Hover

```css
.button:hover {
  background: #222;
}
```

## Focus

```css
.button:focus-visible {
  outline: 2px solid blue;
  outline-offset: 2px;
}
```

`focus-visible` e importante para teclado.

## Disabled

```css
.button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

## Active

```css
.button:active {
  transform: translateY(1px);
}
```

## Pegadinhas

- Remover `outline` sem colocar foco alternativo.
- Ter hover bonito mas sem estado de focus.
- Indicar erro so com cor.

## Resumo mental

UI boa responde ao usuario. Hover e para mouse. Focus e para teclado. Disabled precisa parecer e se comportar como desabilitado.

## Relacionado

- [[Conhecimento/Frontend/HTML/Acessibilidade em HTML|Acessibilidade em HTML]]
- [[Conhecimento/Frontend/Tailwind/Utility First|Utility First]]
