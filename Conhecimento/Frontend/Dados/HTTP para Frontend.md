# HTTP para Frontend

## O que eu preciso lembrar

HTTP e o protocolo que o frontend usa para pedir e enviar dados para um servidor.

## Explicando do zero

Quando o frontend precisa de usuarios, produtos ou posts, ele faz uma requisicao.

Exemplo mental:

```txt
Frontend -> GET /api/users -> Servidor
Frontend <- JSON com usuarios <- Servidor
```

## Metodos HTTP

### GET

Buscar dados.

```txt
GET /api/products
```

### POST

Criar algo.

```txt
POST /api/products
```

### PUT/PATCH

Atualizar algo.

```txt
PATCH /api/products/123
```

### DELETE

Remover algo.

```txt
DELETE /api/products/123
```

## Request e response

Request e o pedido.

Response e a resposta.

Uma resposta pode ter:

- status code;
- headers;
- body.

## Pegadinhas

- `GET` nao deveria alterar dados.
- `POST` geralmente envia body.
- `DELETE` precisa de cuidado na UI.
- HTTP pode falhar mesmo com internet funcionando.

## Resumo mental

HTTP e conversa: frontend pede, servidor responde.

## Relacionado

- [[Status Codes]]
- [[Fetch API]]

