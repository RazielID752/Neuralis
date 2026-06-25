# Status Codes

## O que eu preciso lembrar

Status code e o numero que diz o resultado da requisicao HTTP.

## Grupos principais

### 2xx: sucesso

```txt
200 OK
201 Created
204 No Content
```

### 3xx: redirecionamento

```txt
301 Moved Permanently
302 Found
304 Not Modified
```

### 4xx: erro do cliente

```txt
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
422 Unprocessable Entity
```

### 5xx: erro do servidor

```txt
500 Internal Server Error
502 Bad Gateway
503 Service Unavailable
```

## Diferença entre 401 e 403

`401`: nao autenticado.

`403`: autenticado, mas sem permissao.

## Fetch e status code

Pegadinha importante: `fetch` nao cai no `catch` so porque veio `404` ou `500`.

```ts
const response = await fetch("/api/users");

if (!response.ok) {
  throw new Error("Erro ao buscar usuarios");
}
```

## Resumo mental

Status code me diz se a conversa com o servidor deu certo e que tipo de problema aconteceu.

## Relacionado

- [[Fetch API]]
- [[Tratamento de Erros no Frontend]]

