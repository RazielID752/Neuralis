# HTML Semantico

## O que eu preciso lembrar

HTML semantico e usar a tag pelo significado, nao pela aparencia.

Se eu quero mudar aparencia, uso CSS. Se eu quero comunicar significado, uso HTML.

## Exemplo simples

Ruim:

```html
<div class="titulo">Meu artigo</div>
<div class="texto">Conteudo...</div>
```

Melhor:

```html
<article>
  <h1>Meu artigo</h1>
  <p>Conteudo...</p>
</article>
```

## Tags semanticas comuns

```html
<header>Topo da pagina ou secao</header>
<nav>Navegacao</nav>
<main>Conteudo principal</main>
<section>Secao tematica</section>
<article>Conteudo independente</article>
<aside>Conteudo complementar</aside>
<footer>Rodape</footer>
```

## Por que isso importa

HTML semantico ajuda:

- leitor de tela;
- SEO;
- manutencao;
- navegacao por teclado;
- outros devs lendo o codigo.

## Link vs botao

Se navega para outro lugar:

```html
<a href="/sobre">Sobre</a>
```

Se executa uma acao:

```html
<button type="button">Abrir menu</button>
```

## Pegadinhas

- Usar `div` para tudo.
- Usar `span` clicavel.
- Escolher `h3` porque e menor visualmente.
- Ter varios `h1` sem sentido estrutural.

## Resumo mental

HTML semantico e escrever a pagina de um jeito que o navegador entende o papel de cada coisa.

## Exercicios para fixar

1. Pegue uma tela com muitas `divs` e troque por tags semanticas.
2. Crie um `header`, `nav`, `main` e `footer`.
3. Revise se links e botoes estao corretos.

## Relacionado

- [[Estrutura de Documento HTML]]
- [[Acessibilidade em HTML]]

