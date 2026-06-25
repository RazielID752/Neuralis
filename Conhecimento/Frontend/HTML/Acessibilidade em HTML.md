# Acessibilidade em HTML

## O que eu preciso lembrar

Acessibilidade nao e detalhe extra. HTML bem feito ja resolve muita coisa.

## Explicando do zero

Nem todo mundo usa a pagina do mesmo jeito.

Pessoas podem navegar:

- com mouse;
- com teclado;
- com leitor de tela;
- com zoom alto;
- em celular;
- com conexao ruim.

HTML semantico ajuda o navegador e tecnologias assistivas a entenderem a pagina.

## Coisas basicas que ajudam muito

### Label em input

```html
<label for="email">Email</label>
<input id="email" type="email">
```

### Botao de verdade

```html
<button type="button">Abrir menu</button>
```

### Ordem de titulos

```html
<h1>Titulo principal</h1>
<h2>Secao</h2>
<h3>Subsecao</h3>
```

### Texto de link claro

Ruim:

```html
<a href="/docs">Clique aqui</a>
```

Melhor:

```html
<a href="/docs">Ler documentacao</a>
```

## ARIA

ARIA ajuda quando HTML nativo nao resolve.

Mas regra mental:

Antes de usar ARIA, veja se existe uma tag HTML nativa que ja faz aquilo.

## Pegadinhas

- `div` com `onClick` no lugar de `button`.
- Input sem label.
- Remover outline de foco sem colocar outro.
- Usar apenas cor para indicar erro.
- Colocar `aria-label` sem necessidade.

## Resumo mental

Primeiro HTML certo. Depois ARIA se precisar.

## Exercicios para fixar

1. Crie um formulario com labels corretos.
2. Crie uma navegacao com `nav`.
3. Revise uma pagina e troque `div` clicavel por `button`.
4. Escreva textos de links mais claros.

## Relacionado

- [[HTML Semantico]]
- [[Formularios]]

