# HTML do Zero ao Avancado

## O que e HTML

HTML e a linguagem de marcacao que define a estrutura e o significado do conteudo de uma pagina.

HTML nao e sobre deixar bonito. Isso e CSS.

HTML responde:

- qual e o titulo?
- qual e o paragrafo?
- qual e o formulario?
- qual e a navegacao?
- qual e o conteudo principal?
- qual botao executa uma acao?

## Documento basico

Leia tambem: [[Estrutura de Documento HTML]].

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha pagina</title>
  </head>
  <body>
    <h1>Ola, mundo</h1>
  </body>
</html>
```

Partes:

- `doctype`: informa que o documento usa HTML moderno.
- `html`: elemento raiz.
- `head`: metadados.
- `body`: conteudo visivel.
- `meta viewport`: essencial para responsividade.

## Titulos e texto

```html
<h1>Titulo principal</h1>
<h2>Secao</h2>
<p>Paragrafo de texto.</p>
```

Use titulos em ordem logica. Nao escolha `h1`, `h2`, `h3` pelo tamanho visual. Tamanho e trabalho do CSS.

## Links e botoes

Leia tambem: [[Links Imagens e Listas]].

Link navega:

```html
<a href="/sobre">Sobre</a>
```

Botao executa acao:

```html
<button type="button">Abrir menu</button>
```

Erro comum: usar `div` clicavel no lugar de botao.

## Imagens

Leia tambem: [[Links Imagens e Listas]].

```html
<img src="/avatar.png" alt="Foto de Ana sorrindo">
```

`alt` descreve a imagem para acessibilidade. Se a imagem for decorativa, pode usar `alt=""`.

## HTML semantico

Elementos semanticos comunicam papel:

```html
<header>Topo</header>
<nav>Navegacao</nav>
<main>Conteudo principal</main>
<article>Conteudo independente</article>
<section>Secao tematica</section>
<aside>Conteudo complementar</aside>
<footer>Rodape</footer>
```

Semantica melhora:

- acessibilidade;
- SEO;
- manutencao;
- leitura do codigo.

## Formularios

Formulario basico:

```html
<form>
  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>

  <button type="submit">Enviar</button>
</form>
```

Regra importante:

- input precisa de label;
- button dentro de form deve ter `type`;
- mensagens de erro devem ser claras;
- campos obrigatorios devem ser comunicados.

## Acessibilidade

Leia tambem: [[Acessibilidade em HTML]].

Acessibilidade nao e extra. E parte do HTML correto.

Boas praticas:

- usar elementos nativos;
- associar `label` e `input`;
- manter ordem de titulos;
- escrever textos de link claros;
- nao depender apenas de cor;
- garantir navegacao por teclado.

## Nivel avancado

Topicos para aprofundar:

- ARIA, apenas quando HTML nativo nao basta;
- landmarks;
- formularios acessiveis;
- tabelas semanticas;
- SEO tecnico;
- Open Graph;
- meta tags;
- performance de imagens;
- progressive enhancement.

## Ordem de estudo

1. Estrutura do documento.
2. Texto e titulos.
3. Links.
4. Imagens.
5. Listas.
6. Botoes.
7. Formularios.
8. HTML semantico.
9. Acessibilidade.
10. Tabelas.
11. Metadados.
12. SEO.
13. ARIA.

## Criterio de dominio

Voce esta ficando bom em HTML quando consegue criar uma pagina que continua fazendo sentido mesmo sem CSS e JavaScript.
