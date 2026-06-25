# Operadores e Comparacoes

## Explicacao em uma frase

Operadores servem para calcular, comparar e combinar valores.

## Operadores aritmeticos

```js
const a = 10;
const b = 5;

console.log(a + b); // soma: 15
console.log(a - b); // subtracao: 5
console.log(a * b); // multiplicacao: 50
console.log(a / b); // divisao: 2
console.log(a % b); // resto da divisao: 0
```

O operador `%` e muito usado para descobrir se um numero e par:

```js
const numero = 10;
const ehPar = numero % 2 === 0;
```

## Operadores de comparacao

Comparacoes retornam booleanos: `true` ou `false`.

```js
console.log(10 > 5); // true
console.log(5 > 10); // false
console.log(20 < 10); // false
console.log(10 <= 10); // true
console.log(10 >= 11); // false
```

## Igualdade estrita

Prefira `===` e `!==`.

```js
console.log(10 == "10"); // true
console.log(10 === "10"); // false
console.log(10 !== "10"); // true
```

`==` tenta converter tipos antes de comparar. Isso pode esconder bugs.

`===` compara valor e tipo.

## Operador logico E: `&&`

`&&` retorna o primeiro valor falsy encontrado. Se todos forem truthy, retorna o ultimo.

```js
console.log(true && true); // true
console.log(true && false); // false
console.log("Gato" && "Cao"); // "Cao"
console.log(0 && 10); // 0
```

Uso comum em React:

```jsx
{error && <p>{error}</p>}
```

Se `error` existir, mostra o paragrafo. Se nao existir, nao mostra nada.

## Operador logico OU: `||`

`||` retorna o primeiro valor truthy encontrado.

```js
console.log(true || false); // true
console.log("Gato" || "Cao"); // "Gato"
console.log(0 || 10); // 10
```

Uso comum:

```js
const nomeExibido = nome || "Visitante";
```

## Operador de negacao: `!`

`!` inverte o valor booleano.

```js
console.log(!true); // false
console.log(!false); // true
console.log(!""); // true
console.log(!"texto"); // false
```

Dois sinais `!!` convertem um valor para booleano:

```js
console.log(!!"texto"); // true
console.log(!!""); // false
console.log(!!0); // false
console.log(!!1); // true
```

## Exercicio

Qual valor aparece?

```js
const expressao = (5 - 2) && (5 - " ") && (5 - 2);
console.log(expressao);
```

Resposta: `3`.

Por que?

- `5 - 2` vira `3`, truthy;
- `5 - " "` vira `5`, porque string vazia com espaco pode ser convertida para `0`;
- `5 - 2` vira `3`;
- como todos sao truthy, `&&` retorna o ultimo valor.

## Relacionado

- [[Booleanos e Condicionais]]
- [[JavaScript do Zero ao Avancado]]

