# Box Model

## O que eu preciso lembrar

Todo elemento na tela e uma caixa.

Essa caixa tem:

- conteudo;
- padding;
- borda;
- margin.

## Exemplo simples

```css
.card {
  box-sizing: border-box;
  width: 320px;
  padding: 16px;
  border: 1px solid #ddd;
  margin: 24px;
}
```

## Conteudo

E o que fica dentro do elemento: texto, imagem, filhos.

## Padding

Espaco interno.

```css
.card {
  padding: 16px;
}
```

## Border

Linha ao redor da caixa.

```css
.card {
  border: 1px solid #ddd;
}
```

## Margin

Espaco externo, entre uma caixa e outra.

```css
.card {
  margin-bottom: 24px;
}
```

## `box-sizing: border-box`

Sem `border-box`, largura pode ficar confusa.

```css
* {
  box-sizing: border-box;
}
```

Com `border-box`, `width` inclui conteudo, padding e borda.

## Pegadinhas

- Confundir padding com margin.
- Colocar margin no filho quando `gap` resolveria.
- Esquecer `box-sizing`.
- Achar que border nao ocupa espaco.

## Resumo mental

Padding empurra para dentro. Margin empurra para fora.

## Exercicios para fixar

1. Crie um card com padding.
2. Adicione border.
3. Adicione margin entre cards.
4. Compare com e sem `box-sizing: border-box`.

## Relacionado

- [[CSS]]
- [[Flexbox]]

