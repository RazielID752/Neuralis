# Closures

## Ideia central

Uma closure acontece quando uma funcao lembra variaveis do escopo onde foi criada.

## Exemplo minimo

```js
function createCounter() {
  let count = 0;

  return function increment() {
    count += 1;
    return count;
  };
}

const counter = createCounter();
counter();
```

## Relacionado

- Funcoes
- Escopo
- Estado

