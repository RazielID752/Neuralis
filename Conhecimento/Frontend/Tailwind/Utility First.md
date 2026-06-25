# Utility First

## O que eu preciso lembrar

Utility first significa montar estilos com classes pequenas.

Cada classe faz uma coisa.

## CSS tradicional

```css
.button {
  background: black;
  color: white;
  padding: 8px 16px;
  border-radius: 6px;
}
```

## Tailwind

```html
<button class="rounded bg-black px-4 py-2 text-white">
  Salvar
</button>
```

## Por que isso ajuda

Eu nao preciso inventar nome de classe para cada variacao pequena.

Tambem consigo ver o visual diretamente no componente.

## Pegadinhas

- Classes demais podem deixar dificil de ler.
- Se repetir muito, vira componente.
- Utility first nao substitui entender CSS.

## Resumo mental

Tailwind e CSS em pecinhas pequenas. Se a mesma combinacao aparece muito, eu extraio componente.

## Relacionado

- [[Tailwind CSS]]
- [[Componentizacao com Tailwind]]

