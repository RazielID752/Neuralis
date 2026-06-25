# Display, Position e Z Index

## O que eu preciso lembrar

`display` define como o elemento participa do layout. `position` muda como ele se posiciona. `z-index` controla sobreposicao.

## Display

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

## Block e inline

Elemento block ocupa largura disponivel:

```css
div {
  display: block;
}
```

Elemento inline ocupa so o conteudo:

```css
span {
  display: inline;
}
```

## Position

```css
.relative {
  position: relative;
}

.absolute {
  position: absolute;
}

.fixed {
  position: fixed;
}

.sticky {
  position: sticky;
}
```

Resumo:

- `relative`: fica no fluxo, mas pode servir de referencia.
- `absolute`: sai do fluxo e se posiciona em relacao a um ancestral posicionado.
- `fixed`: fica preso na tela.
- `sticky`: gruda depois de certa posicao.

## Z-index

```css
.modal {
  position: fixed;
  z-index: 50;
}
```

`z-index` so funciona como esperado em elementos posicionados e dentro de contextos de empilhamento.

## Pegadinhas

- Usar `absolute` quando flex/grid resolveria.
- `z-index` alto nao vence se estiver em outro stacking context.
- `fixed` pode atrapalhar mobile se usado sem cuidado.

## Resumo mental

Primeiro tento layout normal, flex ou grid. Uso position quando preciso tirar algo do fluxo ou sobrepor.

## Relacionado

- [[Flexbox]]
- [[Grid]]

