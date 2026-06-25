# Variaveis: var, let e const

## O que eu preciso lembrar

Variavel e um nome que guarda um valor.

No JavaScript moderno:

- uso `const` primeiro;
- uso `let` se o valor precisar mudar;
- evito `var`.

## Explicando do zero

Pensa em variavel como uma caixinha com etiqueta.

```js
const nome = "Marcos";
```

Aqui:

- `nome` e o nome da caixinha;
- `"Marcos"` e o valor guardado;
- `const` diz que essa caixinha nao vai receber outro valor.

Quando eu escrevo:

```js
console.log(nome);
```

O JavaScript pega o valor que esta guardado em `nome` e mostra no console.

## Por que variavel existe

Variavel existe para eu nao precisar repetir valores e para conseguir dar nome para as coisas.

Sem variavel:

```js
console.log("Marcos");
console.log("Ola, Marcos");
console.log("Marcos esta estudando JavaScript");
```

Com variavel:

```js
const nome = "Marcos";

console.log(nome);
console.log("Ola, " + nome);
console.log(nome + " esta estudando JavaScript");
```

Fica mais facil mudar depois.

## `const`

`const` e para valores que nao serao reatribuidos.

```js
const idade = 25;
```

Isso da erro:

```js
const idade = 25;
idade = 26;
```

Eu uso `const` quando quero dizer: "essa variavel nao deve apontar para outro valor".

## Pegadinha do `const`

`const` nao significa que tudo dentro e congelado.

Com objeto:

```js
const pessoa = {
  nome: "Carlos",
  idade: 28,
};

pessoa.idade = 29;

console.log(pessoa);
```

Isso funciona porque a variavel `pessoa` continua apontando para o mesmo objeto. O que mudou foi uma propriedade dentro dele.

Com array:

```js
const numeros = [1, 2, 3];

numeros.push(4);

console.log(numeros);
```

Isso tambem funciona.

O que nao pode e trocar a referencia inteira:

```js
const numeros = [1, 2, 3];

numeros = [1, 2, 3, 4]; // erro
```

## `let`

`let` e para valores que precisam mudar.

```js
let contador = 0;

contador = contador + 1;
contador++;
```

Eu uso `let` quando o proprio valor da variavel vai ser reatribuido.

Exemplo:

```js
let mensagem = "Carregando...";

mensagem = "Dados carregados";
```

## Escopo de bloco

`let` e `const` respeitam blocos `{}`.

```js
function exemploLet() {
  let idade = 30;

  if (true) {
    let idade = 25;
    console.log(idade); // 25
  }

  console.log(idade); // 30
}
```

Resumo: a `idade` de dentro do `if` nao e a mesma `idade` de fora.

## `var`

`var` e antigo e pode confundir.

O problema e que `var` nao respeita bloco do jeito que eu espero.

```js
function exemploVar() {
  var nome = "Marcos";

  if (true) {
    var nome = "Joao";
    console.log(nome); // Joao
  }

  console.log(nome); // Joao
}
```

O `var nome` dentro do `if` sobrescreveu o `nome` de fora.

Por isso, regra simples: nao usar `var` em codigo novo.

## Hoisting

Hoisting e quando o JavaScript "conhece" uma declaracao antes da linha onde ela aparece.

Com `var`:

```js
console.log(nome); // undefined

var nome = "Marcos";
```

Ele nao da erro, mas mostra `undefined`. Isso pode esconder bug.

Com `let` e `const`:

```js
console.log(nome); // erro

const nome = "Marcos";
```

Aqui o erro e melhor, porque me avisa que estou usando a variavel antes da hora.

## Como isso aparece em React/TypeScript

Em React, uso `const` o tempo todo:

```tsx
const [count, setCount] = useState(0);
const title = "Contador";
```

Uso `let` menos, geralmente dentro de uma funcao quando preciso montar algum valor passo a passo.

Em TypeScript, alem de declarar a variavel, eu tambem posso ter tipo:

```ts
const nome: string = "Marcos";
let idade: number = 25;
```

Mas quando o TypeScript consegue entender sozinho, nao preciso escrever o tipo:

```ts
const nome = "Marcos";
let idade = 25;
```

## Erros que eu posso cometer

- Usar `var` sem necessidade.
- Usar `let` para tudo, mesmo quando `const` bastava.
- Achar que `const` congela objeto ou array.
- Usar a variavel antes de declarar.
- Dar nome ruim para variavel, tipo `x`, `coisa`, `dados`, sem contexto.

## Resumo mental

`const` e minha escolha padrao. `let` e para valor que muda. `var` fica no passado.

Se for objeto ou array com `const`, eu nao posso trocar a referencia, mas ainda posso mexer no conteudo interno.

## Exercicios para fixar

1. Crie uma variavel `nome` com `const` e mostre no console.
2. Crie uma variavel `contador` com `let` e some `1` tres vezes.
3. Crie um objeto `pessoa` com `const` e altere a idade.
4. Crie um array `tarefas` com `const` e adicione uma nova tarefa.
5. Escreva um exemplo onde `var` causa confusao dentro de um `if`.

## Como saber que eu entendi

- Eu sei explicar quando usar `const`.
- Eu sei explicar quando usar `let`.
- Eu sei por que evitar `var`.
- Eu sei que `const` nao congela objetos.
- Eu sei o que significa escopo de bloco.

## Relacionado

- [[JavaScript do Zero ao Avancado]]
- [[Operadores e Comparacoes]]
- [[Conhecimento/Frontend/React/State|State]]

