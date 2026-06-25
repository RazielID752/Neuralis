# Funcoes e Callbacks

## Explicacao em uma frase

Funcoes sao blocos reutilizaveis de codigo, e callbacks sao funcoes passadas para outras funcoes.

## Funcao basica

```js
function saudacao(nome) {
  return "Ola, " + nome + "!";
}

console.log(saudacao("Marcos"));
```

Partes:

- `function`: palavra para declarar funcao;
- `saudacao`: nome da funcao;
- `nome`: parametro;
- `return`: valor devolvido.

## Parametros e argumentos

Parametro e o nome na definicao:

```js
function dobrar(numero) {
  return numero * 2;
}
```

Argumento e o valor passado na chamada:

```js
dobrar(10);
```

## Funcao anonima

Funcao anonima nao tem nome.

```js
setTimeout(function () {
  console.log("Executou depois de 1 segundo");
}, 1000);
```

## Arrow function

Arrow function e uma forma mais curta de escrever funcao.

```js
const soma = (a, b) => a + b;

console.log(soma(5, 3)); // 8
```

Com corpo maior:

```js
const saudacao = (nome) => {
  const mensagem = "Ola, " + nome;
  return mensagem;
};
```

## Callback

Callback e uma funcao passada como argumento para outra funcao.

```js
function saudacao(nome, callback) {
  console.log("Ola, " + nome);
  callback();
}

function despedida() {
  console.log("Ate logo!");
}

saudacao("Marcos", despedida);
```

Fluxo:

1. chama `saudacao`;
2. mostra `"Ola, Marcos"`;
3. executa a funcao recebida em `callback`;
4. mostra `"Ate logo!"`.

## Callbacks em arrays

`map`, `filter` e `forEach` recebem callbacks.

```js
const frutas = ["Maca", "Banana", "Laranja"];

const frutasMaiusculas = frutas.map((fruta) => fruta.toUpperCase());

console.log(frutasMaiusculas);
```

Aqui, `(fruta) => fruta.toUpperCase()` e um callback.

## `this`

`this` aponta para o contexto de execucao. O valor muda dependendo de como a funcao e chamada.

Em objeto:

```js
const pessoa = {
  nome: "Marcos",
  saudacao: function () {
    console.log("Ola, " + this.nome);
  },
};

pessoa.saudacao();
```

Em arrow function, `this` nao e criado pela propria funcao. Ele vem do contexto onde a arrow foi criada.

```js
const pessoa = {
  nome: "Marcos",
  saudacao: function () {
    setTimeout(() => {
      console.log("Ola, meu nome e " + this.nome);
    }, 1000);
  },
};

pessoa.saudacao();
```

## Erros comuns

- Criar funcoes grandes demais.
- Usar callback sem entender quando ele executa.
- Confundir parametro com argumento.
- Usar arrow function em metodo de objeto quando precisa de `this` do objeto.

## Relacionado

- [[Closures]]
- [[Timers setTimeout setInterval]]
- [[Arrays e Objetos]]

