# Timers: setTimeout e setInterval

## Explicacao em uma frase

Timers executam codigo depois de um tempo ou repetidamente em intervalos.

## `setTimeout`

Executa uma funcao uma vez depois de um tempo.

```js
console.log("Inicio");

setTimeout(function () {
  console.log("Executado depois de 2 segundos");
}, 2000);

console.log("Fim");
```

Saida:

```txt
Inicio
Fim
Executado depois de 2 segundos
```

Isso mostra uma ideia importante: JavaScript nao fica parado esperando o `setTimeout`. Ele agenda a funcao e continua executando o resto.

## `setInterval`

Executa uma funcao repetidamente.

```js
let contador = 0;

const intervalo = setInterval(function () {
  contador++;
  console.log(contador);

  if (contador >= 5) {
    clearInterval(intervalo);
  }
}, 1000);
```

`clearInterval` para o intervalo.

## Cancelando `setTimeout`

```js
const timeout = setTimeout(function () {
  console.log("Nao vou executar se for cancelado");
}, 1000);

clearTimeout(timeout);
```

## Relacao com promises

Timers usam callbacks. Promises representam um resultado futuro.

Voce pode criar uma espera com Promise:

```js
function wait(ms) {
  return new Promise((resolve) => {
    setTimeout(resolve, ms);
  });
}

async function run() {
  console.log("Inicio");
  await wait(1000);
  console.log("Depois de 1 segundo");
}
```

## Relacionado

- [[Promises]]
- [[Async Await]]
- [[Funcoes e Callbacks]]

