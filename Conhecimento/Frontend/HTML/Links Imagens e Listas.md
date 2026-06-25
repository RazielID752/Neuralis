# Links, Imagens e Listas

## O que eu preciso lembrar

Links navegam, imagens mostram conteudo visual, listas organizam itens relacionados.

## Links

```html
<a href="/sobre">Sobre</a>
```

Use link quando a acao leva para outro lugar.

```html
<a href="https://developer.mozilla.org" target="_blank" rel="noreferrer">
  MDN
</a>
```

## Botao nao e link

Link navega:

```html
<a href="/contato">Contato</a>
```

Botao executa acao:

```html
<button type="button">Abrir menu</button>
```

## Imagens

```html
<img src="/avatar.png" alt="Foto de Marcos sorrindo">
```

`alt` descreve a imagem.

Se a imagem for decorativa:

```html
<img src="/linha.png" alt="">
```

## Listas

Lista sem ordem:

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

Lista ordenada:

```html
<ol>
  <li>Instalar dependencias</li>
  <li>Rodar projeto</li>
  <li>Abrir navegador</li>
</ol>
```

## Pegadinhas

- Usar `a` sem `href`.
- Usar imagem importante sem `alt`.
- Usar varios textos "clique aqui" sem contexto.
- Usar lista visual sem tags de lista.

## Resumo mental

Se navega, e link. Se executa acao, e botao. Se e imagem importante, precisa de descricao.

## Exercicios para fixar

1. Crie um link para uma pagina interna.
2. Crie um link externo com `target="_blank"`.
3. Adicione uma imagem com `alt`.
4. Crie uma lista de estudos.

## Relacionado

- [[HTML Semantico]]
- [[Acessibilidade em HTML]]

