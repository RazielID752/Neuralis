# Tema e Configuracao do Tailwind

## O que eu preciso lembrar

Tema e onde defino padroes visuais: cores, fontes, espacamentos e breakpoints.

## Por que isso existe

Para nao escolher valor aleatorio em cada tela.

Em vez de cada botao ter um azul diferente, o projeto tem uma paleta.

## Exemplo mental

```js
// tailwind.config.js
export default {
  theme: {
    extend: {
      colors: {
        brand: {
          500: "#2563eb",
          600: "#1d4ed8",
        },
      },
    },
  },
};
```

Uso:

```html
<button class="bg-brand-500 hover:bg-brand-600">
  Salvar
</button>
```

## Dark mode

```html
<div class="bg-white text-black dark:bg-black dark:text-white">
  Conteudo
</div>
```

## Pegadinhas

- Criar tema antes de entender o visual.
- Colocar cor demais.
- Fugir do tema com valores arbitrarios o tempo todo.

## Resumo mental

Tema e memoria visual do projeto. Ele deixa a interface consistente.

## Relacionado

- [[Espacamento Cores e Tipografia no Tailwind]]
- [[Componentizacao com Tailwind]]

