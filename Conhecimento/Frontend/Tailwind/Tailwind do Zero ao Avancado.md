# Tailwind do Zero ao Avancado

## O que e Tailwind

Tailwind CSS e um framework utility-first.

Em vez de criar uma classe para cada componente:

```css
.button {
  background: black;
  color: white;
  padding: 8px 16px;
}
```

Voce compoe utilitarios:

```html
<button class="bg-black px-4 py-2 text-white">
  Salvar
</button>
```

## Por que isso existe

Tailwind reduz a necessidade de inventar nomes de classes e facilita manter consistencia visual.

Ele e bom quando voce quer:

- velocidade;
- padroes previsiveis;
- design system com tokens;
- responsividade rapida;
- evitar CSS global crescendo sem controle.

## Classes de espacamento

Leia tambem: [[Espacamento Cores e Tipografia no Tailwind]].

```html
<div class="p-4 m-2 gap-6">
  Conteudo
</div>
```

- `p`: padding.
- `m`: margin.
- `gap`: espaco entre itens em flex/grid.
- `px`: padding horizontal.
- `py`: padding vertical.

## Layout

Leia tambem: [[Layout com Tailwind]].

Flex:

```html
<div class="flex items-center justify-between gap-4">
  ...
</div>
```

Grid:

```html
<div class="grid grid-cols-3 gap-4">
  ...
</div>
```

## Tipografia

Leia tambem: [[Espacamento Cores e Tipografia no Tailwind]].

```html
<h1 class="text-3xl font-bold tracking-normal">
  Titulo
</h1>

<p class="text-sm leading-6 text-neutral-600">
  Texto de apoio.
</p>
```

## Cores

```html
<div class="bg-white text-neutral-900 border border-neutral-200">
  ...
</div>
```

Use cores com intencao:

- texto principal;
- texto secundario;
- borda;
- fundo;
- acao;
- erro;
- sucesso.

## Responsividade

Leia tambem: [[Design Responsivo com Tailwind]].

Tailwind usa prefixos:

```html
<section class="grid gap-4 md:grid-cols-2 lg:grid-cols-3">
  ...
</section>
```

Leitura:

- mobile: uma coluna;
- `md`: duas colunas;
- `lg`: tres colunas.

## Estados

Leia tambem: [[Estados no Tailwind]].

```html
<button class="bg-black text-white hover:bg-neutral-800 focus-visible:outline focus-visible:outline-2 disabled:opacity-50">
  Salvar
</button>
```

Estados comuns:

- `hover:`
- `focus:`
- `focus-visible:`
- `active:`
- `disabled:`
- `dark:`

## Componentizacao

Leia tambem: [[Componentizacao com Tailwind]].

Tailwind nao significa repetir classes enormes para sempre.

Em React, voce pode encapsular:

```tsx
type ButtonProps = {
  children: React.ReactNode;
};

function Button({ children }: ButtonProps) {
  return (
    <button className="rounded bg-black px-4 py-2 text-sm font-medium text-white hover:bg-neutral-800">
      {children}
    </button>
  );
}
```

## Erros comuns

- Usar classes sem entender CSS por baixo.
- Criar markup ilegivel com classes demais.
- Repetir componentes sem extrair.
- Usar cores aleatorias fora do tema.
- Esquecer estados de foco e disabled.

## Nivel avancado

Topicos para aprofundar:

- `tailwind.config`;
- tokens de design;
- dark mode;
- plugins;
- variantes;
- `clsx` e `tailwind-merge`;
- class variance authority;
- componentes com variantes;
- design system.

## Ordem de estudo

1. Espacamento.
2. Cores.
3. Tipografia.
4. Flex.
5. Grid.
6. Responsividade.
7. Estados.
8. Dark mode.
9. Configuracao de tema.
10. Componentes reutilizaveis.
11. Variantes.
12. Design system.

## Criterio de dominio

Voce esta ficando bom em Tailwind quando consegue olhar para uma classe e entender o CSS gerado, criar componentes consistentes e manter responsividade sem baguncar o markup.
