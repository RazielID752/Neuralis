# Loops

## Explicacao em uma frase

Loops repetem um bloco de codigo enquanto uma condicao permitir.

## `for`

Use `for` quando voce sabe quantas repeticoes quer.

```js
for (let i = 0; i < 5; i++) {
  console.log("Numero:", i);
}
```

Partes:

- `let i = 0`: inicio;
- `i < 5`: condicao para continuar;
- `i++`: atualizacao depois de cada repeticao.

## `while`

Use `while` quando a repeticao depende de uma condicao.

```js
let contador = 0;

while (contador < 5) {
  console.log("Contando...", contador);
  contador++;
}
```

## `for...of`

Bom para percorrer arrays.

```js
const frutas = ["Maca", "Banana", "Laranja"];

for (const fruta of frutas) {
  console.log(fruta);
}
```

## Array methods vs loops

Em JavaScript moderno, muitas transformacoes usam metodos de array.

```js
const numeros = [1, 2, 3, 4];

const dobrados = numeros.map((numero) => numero * 2);
const pares = numeros.filter((numero) => numero % 2 === 0);
```

Use `for` quando precisa de controle fino. Use `map`, `filter`, `reduce` quando esta transformando dados.

## Loop infinito

Cuidado com loops que nunca terminam:

```js
let contador = 0;

while (contador < 5) {
  console.log(contador);
  // faltou contador++
}
```

## Relacionado

- [[Arrays e Objetos]]
- [[JavaScript do Zero ao Avancado]]

