# Async Await

## Ideia central

`async` e `await` tornam codigo assincrono mais parecido com codigo sequencial.

## Exemplo minimo

```js
async function loadUser() {
  const response = await fetch("/api/user");
  return response.json();
}
```

## Cuidados

- Sempre tratar erros.
- Evitar `await` desnecessariamente sequencial quando tarefas podem rodar em paralelo.

