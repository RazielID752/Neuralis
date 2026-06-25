# XSS

## O que eu preciso lembrar

XSS acontece quando codigo malicioso consegue executar JavaScript dentro da minha pagina.

## Explicando do zero

Se o usuario consegue enviar um texto como:

```html
<script>alert("hack")</script>
```

E minha pagina renderiza isso como HTML real, esse script pode executar.

## Exemplo perigoso em React

```tsx
<div dangerouslySetInnerHTML={{ __html: content }} />
```

O proprio nome avisa: `dangerously`.

## Por que e perigoso

Um XSS pode:

- roubar token;
- fazer acao em nome do usuario;
- ler dados da pagina;
- alterar conteudo;
- redirecionar usuario.

## Como reduzir risco

- Evitar renderizar HTML de usuario.
- Sanitizar HTML quando for inevitavel.
- Usar bibliotecas confiaveis de sanitizacao.
- Escapar conteudo.
- Usar Content Security Policy.
- Nao guardar token sensivel em local acessivel por JS quando possivel.

## React ajuda?

React escapa strings por padrao:

```tsx
<p>{userInput}</p>
```

Isso e mais seguro do que injetar HTML.

Mas React nao salva se eu usar `dangerouslySetInnerHTML` sem cuidado.

## Pegadinhas

- Markdown convertido para HTML sem sanitizar.
- Comentarios de usuario renderizados como HTML.
- Conteudo vindo de CMS.
- Query param colocado direto no HTML.

## Resumo mental

Se um texto externo vira HTML executavel, eu preciso desconfiar.

## Relacionado

- [[Dados Sensiveis no Frontend]]
- [[LocalStorage vs Cookies]]

