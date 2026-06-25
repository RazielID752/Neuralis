# Seletores, Cascata e Especificidade

## O que eu preciso lembrar

CSS aplica regras por seletores. Quando varias regras brigam, cascata e especificidade decidem quem vence.

## Seletores basicos

Elemento:

```css
button {
  color: white;
}
```

Classe:

```css
.button {
  color: white;
}
```

ID:

```css
#submit {
  color: white;
}
```

## Cascata

Se duas regras tem mesma forca, a que vem depois ganha.

```css
.title {
  color: red;
}

.title {
  color: blue;
}
```

Resultado: azul.

## Especificidade

Ordem mental:

1. inline style;
2. id;
3. classe;
4. elemento.

```css
p {
  color: red;
}

.text {
  color: blue;
}
```

Se o paragrafo tem `class="text"`, azul ganha.

## Pegadinhas

- Usar ID demais torna estilo dificil de sobrescrever.
- Colocar seletor muito longo cria briga futura.
- `!important` resolve agora e cobra depois.

## Resumo mental

Se um estilo nao aplica, eu verifico: seletor, ordem, especificidade e se outro estilo esta vencendo.

## Exercicios para fixar

1. Crie duas regras para a mesma classe e veja a ultima vencer.
2. Compare seletor de elemento com classe.
3. Evite usar `!important` e tente resolver com ordem/especificidade.

## Relacionado

- [[CSS]]
- [[Box Model]]

