# JavaScript do Zero ao Avancado

## O que e JavaScript

JavaScript e a linguagem que adiciona comportamento as paginas web.

HTML estrutura, CSS apresenta, JavaScript faz a pagina reagir:

- clicar em botoes;
- validar formularios;
- buscar dados;
- abrir menus;
- atualizar conteudo;
- criar aplicacoes inteiras.

## Valores e tipos

Valores comuns:

```js
"texto"; // string
42; // number
true; // boolean
null;
undefined;
{}; // object
[]; // array
```

JavaScript e dinamico: uma variavel pode receber valores de tipos diferentes.

```js
let value = "texto";
value = 10;
```

Isso da flexibilidade, mas tambem pode gerar bugs. Por isso TypeScript ajuda.

## Variaveis

Leia tambem: [[Variaveis var let const]].

Use `const` por padrao:

```js
const name = "Ana";
```

Use `let` quando o valor precisa mudar:

```js
let count = 0;
count = count + 1;
```

Evite `var` em codigo moderno.

## Funcoes

Leia tambem: [[Funcoes e Callbacks]].

Funcao nomeada:

```js
function sum(a, b) {
  return a + b;
}
```

Arrow function:

```js
const sum = (a, b) => a + b;
```

Funcoes sao blocos reutilizaveis de comportamento.

## Objetos

Leia tambem: [[Arrays e Objetos]].

Objeto agrupa dados relacionados:

```js
const user = {
  id: "1",
  name: "Ana",
  email: "ana@email.com",
};

console.log(user.name);
```

Atualizacao imutavel:

```js
const updatedUser = {
  ...user,
  name: "Ana Silva",
};
```

## Arrays

Leia tambem: [[Arrays e Objetos]].

Array guarda lista de valores:

```js
const numbers = [1, 2, 3];
```

Metodos essenciais:

```js
numbers.map((number) => number * 2);
numbers.filter((number) => number > 1);
numbers.find((number) => number === 2);
numbers.reduce((total, number) => total + number, 0);
```

Esses metodos sao fundamentais em React.

## Condicionais

Leia tambem: [[Booleanos e Condicionais]] e [[Operadores e Comparacoes]].

```js
if (age >= 18) {
  console.log("Maior de idade");
} else {
  console.log("Menor de idade");
}
```

Ternario:

```js
const label = isLoading ? "Carregando" : "Enviar";
```

## Loops

Leia tambem: [[Loops]].

```js
for (const item of items) {
  console.log(item);
}
```

Em codigo de UI, muitas vezes `map`, `filter` e `reduce` sao mais comuns que `for`.

## Escopo e closures

Escopo define onde uma variavel existe.

Closure acontece quando uma funcao lembra o escopo onde foi criada.

```js
function createCounter() {
  let count = 0;

  return function increment() {
    count += 1;
    return count;
  };
}
```

Closures aparecem em callbacks, hooks, eventos e funcoes utilitarias.

## DOM e eventos

Leia tambem: [[DOM e Eventos]].

DOM e a representacao da pagina no navegador.

```js
const button = document.querySelector("button");

button.addEventListener("click", () => {
  console.log("clicou");
});
```

React abstrai parte disso, mas entender DOM ajuda muito.

## Assincronicidade

Leia tambem: [[Timers setTimeout setInterval]], [[Promises]] e [[Async Await]].

JavaScript lida muito com tarefas que terminam depois:

- requests HTTP;
- timers;
- leitura de arquivos;
- eventos do usuario.

Promise:

```js
fetch("/api/users")
  .then((response) => response.json())
  .then((data) => console.log(data));
```

Async/await:

```js
async function loadUsers() {
  const response = await fetch("/api/users");
  return response.json();
}
```

## Modules

Separe codigo em arquivos:

```js
export function formatCurrency(value) {
  return `R$ ${value.toFixed(2)}`;
}
```

```js
import { formatCurrency } from "./formatCurrency.js";
```

## Nivel avancado

Depois da base, estude:

- event loop;
- call stack;
- microtasks e macrotasks;
- prototypes;
- this;
- classes;
- generators;
- modules em profundidade;
- imutabilidade;
- padroes funcionais;
- performance;
- memory leaks.

## Ordem de estudo

1. Valores e tipos.
2. Variaveis.
3. Funcoes.
4. Objetos.
5. Arrays.
6. Condicionais.
7. Loops.
8. DOM.
9. Eventos.
10. Escopo.
11. Closures.
12. Promises.
13. Async/await.
14. Modules.
15. Event loop.
16. Padroes de codigo.

## Criterio de dominio

Voce esta ficando bom em JavaScript quando consegue:

- transformar dados com `map`, `filter`, `reduce`;
- explicar escopo e closure;
- entender codigo assincrono;
- manipular objetos sem mutacao desnecessaria;
- separar codigo em funcoes pequenas;
- ler erros no console;
- prever o fluxo de execucao.
