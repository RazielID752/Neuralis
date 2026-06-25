# Animacoes e Transicoes

## O que eu preciso lembrar

Transicao suaviza mudança. Animacao cria uma sequencia de estados.

## Transition

```css
.button {
  background: black;
  transition: background 150ms ease;
}

.button:hover {
  background: #333;
}
```

## Animation

```css
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.modal {
  animation: fade-in 200ms ease;
}
```

## Performance

Prefira animar:

- `transform`;
- `opacity`.

Cuidado com:

- `width`;
- `height`;
- `top`;
- `left`.

## Pegadinhas

- Animacao demais cansa.
- Esquecer `prefers-reduced-motion`.
- Animar propriedade cara.

## Resumo mental

Animacao boa ajuda a entender mudança, nao chama atenção sem motivo.

## Relacionado

- [[Estados Visuais CSS]]

