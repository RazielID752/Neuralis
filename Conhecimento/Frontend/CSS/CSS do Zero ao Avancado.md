# CSS do Zero ao Avancado

## O que e CSS

CSS define como o HTML aparece visualmente.

Com CSS voce controla:

- cores;
- tipografia;
- espacamento;
- layout;
- responsividade;
- animacoes;
- estados como hover, focus e disabled.

## Sintaxe basica

Leia tambem: [[Seletores Cascata e Especificidade]].

```css
button {
  background: black;
  color: white;
  padding: 12px 16px;
}
```

Partes:

- `button`: seletor.
- `background`: propriedade.
- `black`: valor.

## Cascata

Leia tambem: [[Seletores Cascata e Especificidade]].

CSS significa Cascading Style Sheets.

Quando varias regras afetam o mesmo elemento, o navegador decide qual vence com base em:

- origem;
- especificidade;
- ordem;
- importancia.

## Especificidade

Seletores mais especificos vencem seletores menos especificos.

Ordem aproximada:

- elemento: `button`
- classe: `.button`
- id: `#submit`
- inline style

Regra pratica: prefira classes simples e evite brigar com especificidade.

## Box model

Todo elemento e uma caixa:

```css
.card {
  box-sizing: border-box;
  width: 320px;
  padding: 16px;
  border: 1px solid #ddd;
  margin: 24px;
}
```

- content: conteudo;
- padding: espaco interno;
- border: borda;
- margin: espaco externo.

## Display

Leia tambem: [[Display Position e Z Index]].

`display` muda como o elemento participa do layout.

```css
.hidden {
  display: none;
}

.row {
  display: flex;
}

.grid {
  display: grid;
}
```

## Flexbox

Flexbox e ideal para alinhar elementos em uma direcao.

```css
.toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}
```

Use para:

- navbars;
- botoes lado a lado;
- alinhamento vertical;
- componentes internos.

## Grid

Grid e ideal para layout em duas dimensoes.

```css
.dashboard {
  display: grid;
  grid-template-columns: 240px 1fr;
  gap: 24px;
}
```

Use para:

- paginas;
- dashboards;
- galerias;
- layouts complexos.

## Responsividade

Responsividade significa que a interface funciona em diferentes tamanhos de tela.

```css
.cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

@media (min-width: 768px) {
  .cards {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

## Estados visuais

Leia tambem: [[Estados Visuais CSS]].

```css
.button:hover {
  background: #222;
}

.button:focus-visible {
  outline: 2px solid blue;
}

.button:disabled {
  opacity: 0.5;
}
```

Estados ajudam o usuario a entender interacao.

## Variaveis CSS

Leia tambem: [[Variaveis CSS]].

```css
:root {
  --color-primary: #111827;
  --space-4: 16px;
}

.button {
  background: var(--color-primary);
  padding: var(--space-4);
}
```

Variaveis ajudam a criar sistemas de design.

## Nivel avancado

Topicos para aprofundar:

- cascade layers;
- container queries;
- custom properties;
- animation performance;
- stacking context;
- positioning;
- fluid typography;
- design systems;
- arquitetura CSS;
- acessibilidade visual.

## Ordem de estudo

1. Seletores.
2. Cascata.
3. Especificidade.
4. Box model.
5. Display.
6. Position.
7. Flexbox.
8. Grid.
9. Responsividade.
10. Estados.
11. Variaveis.
12. Animacoes.
13. Arquitetura CSS.

## Criterio de dominio

Voce esta ficando bom em CSS quando consegue prever por que um estilo venceu outro e criar layouts responsivos sem tentativa e erro infinito.
