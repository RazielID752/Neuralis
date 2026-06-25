# Event Loop

## O que eu preciso lembrar

Event loop e o mecanismo que explica por que JavaScript consegue lidar com tarefas assincronas mesmo rodando em uma thread principal.

## Explicando do zero

JavaScript executa uma coisa por vez na call stack.

Quando aparece algo assincrono, como `setTimeout` ou `fetch`, o navegador registra essa tarefa fora da stack e continua o codigo.

Depois, quando a stack fica livre, o event loop coloca callbacks prontos para executar.

## Exemplo

```js
console.log("1");

setTimeout(() => {
  console.log("2");
}, 0);

console.log("3");
```

Saida:

```txt
1
3
2
```

Mesmo com `0`, o `setTimeout` fica para depois da stack atual terminar.

## Microtasks e macrotasks

Promises entram na fila de microtasks.

`setTimeout` entra na fila de macrotasks.

```js
console.log("inicio");

setTimeout(() => console.log("timeout"), 0);

Promise.resolve().then(() => console.log("promise"));

console.log("fim");
```

Saida:

```txt
inicio
fim
promise
timeout
```

## Pegadinhas

- `setTimeout(fn, 0)` nao executa imediatamente.
- Promise costuma rodar antes de timeout.
- Loop pesado trava a UI.
- Async/await tambem usa promises por baixo.

## Resumo mental

JavaScript executa a stack primeiro. Tarefas assincronas entram em filas e voltam quando a stack libera.

## Relacionado

- [[Promises]]
- [[Async Await]]
- [[Timers setTimeout setInterval]]

