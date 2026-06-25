# JSON

## O que eu preciso lembrar

JSON e um formato de texto usado para trocar dados entre frontend e backend.

## Exemplo

```json
{
  "id": "1",
  "name": "Marcos",
  "active": true
}
```

Parece objeto JavaScript, mas e texto.

## Transformar objeto em JSON

```js
const user = {
  id: "1",
  name: "Marcos",
};

const json = JSON.stringify(user);
```

## Transformar JSON em objeto

```js
const user = JSON.parse(json);
```

## Com fetch

```ts
const response = await fetch("/api/users");
const data = await response.json();
```

## Pegadinhas

- JSON nao aceita comentario.
- Chaves precisam de aspas duplas.
- `response.json()` tambem pode falhar.
- JSON recebido da API nao e automaticamente confiavel.

## Resumo mental

JSON e texto com formato de dado. Eu preciso converter para usar como objeto.

## Relacionado

- [[Fetch API]]
- [[Validacao de Dados da API]]

