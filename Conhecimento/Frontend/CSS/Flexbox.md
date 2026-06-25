# Flexbox

## O que eu preciso lembrar

Flexbox organiza elementos em uma direcao: linha ou coluna.

Ele e muito bom para alinhar coisas.

## Exemplo bem simples

```css
.toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}
```

## Eixo principal e eixo cruzado

Se `flex-direction: row`, o eixo principal e horizontal.

```css
.row {
  display: flex;
  flex-direction: row;
}
```

Se `flex-direction: column`, o eixo principal e vertical.

```css
.column {
  display: flex;
  flex-direction: column;
}
```

## Propriedades que eu mais uso

```css
.box {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
}
```

- `align-items`: alinha no eixo cruzado.
- `justify-content`: distribui no eixo principal.
- `gap`: espaco entre itens.

## Quando usar

- Navbar.
- Toolbar.
- Grupo de botoes.
- Alinhar icone e texto.
- Centralizar conteudo.
- Layout simples em linha ou coluna.

## Pegadinhas

- Confundir `align-items` e `justify-content`.
- Usar margin em todos os filhos em vez de `gap`.
- Usar flex para layout de pagina que seria melhor com grid.

## Resumo mental

Flexbox e para alinhar e distribuir itens em uma direcao.

## Exercicios para fixar

1. Crie uma linha com tres botoes e `gap`.
2. Centralize uma caixa na tela.
3. Crie uma coluna com titulo, texto e botao.

## Relacionado

- [[Grid]]
- [[Layout com Tailwind]]

