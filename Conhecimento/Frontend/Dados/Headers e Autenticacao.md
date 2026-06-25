# Headers e Autenticacao

## O que eu preciso lembrar

Headers sao metadados da requisicao/resposta.

Autenticacao e como o servidor sabe quem esta fazendo o pedido.

## Header de JSON

```ts
headers: {
  "Content-Type": "application/json",
}
```

Diz que estou enviando JSON.

## Authorization

```ts
headers: {
  Authorization: `Bearer ${token}`,
}
```

Esse formato e comum quando uso token bearer.

## Cookies

Algumas APIs usam cookies para sessao.

```ts
fetch("/api/me", {
  credentials: "include",
});
```

## Pegadinhas

- Token no localStorage pode ser alvo de XSS.
- Cookie precisa de configuracoes seguras.
- Nunca coloque segredo real no frontend.
- Header errado pode causar erro de CORS ou autorizacao.

## Resumo mental

Header carrega informacao extra. Auth diz quem eu sou para a API.

## Relacionado

- [[Seguranca Frontend]]
- [[Tokens no Frontend]]

