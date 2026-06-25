# Promises

## Ideia central

Promise representa um valor que pode estar disponivel agora, depois, ou falhar.

## Exemplo minimo

```js
fetch("/api/user")
  .then((response) => response.json())
  .then((user) => console.log(user))
  .catch((error) => console.error(error));
```

## Relacionado

- [[Async Await]]
- Fetch API

