# Variaveis CSS

## O que eu preciso lembrar

Variaveis CSS guardam valores reutilizaveis, como cores e espacamentos.

## Exemplo simples

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

## Por que isso existe

Para evitar repetir valores por todo lado.

Sem variavel:

```css
.button {
  background: #111827;
}

.link {
  color: #111827;
}
```

Com variavel:

```css
:root {
  --brand: #111827;
}

.button {
  background: var(--brand);
}

.link {
  color: var(--brand);
}
```

## Tema claro e escuro

```css
:root {
  --background: white;
  --text: black;
}

[data-theme="dark"] {
  --background: black;
  --text: white;
}
```

## Pegadinhas

- Nome ruim vira bagunca.
- Variavel demais sem padrao confunde.
- Variavel CSS nao e igual variavel JavaScript.

## Resumo mental

Variavel CSS e bom para valor que se repete e faz parte do sistema visual.

## Relacionado

- [[CSS]]
- [[Conhecimento/Frontend/Tailwind/Tailwind CSS|Tailwind CSS]]
