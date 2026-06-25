# Tipos Basicos

## O que eu preciso lembrar

Tipo e uma forma de dizer para o TypeScript: "esse valor deve ter esse formato".

Tipos basicos:

- `string`: texto;
- `number`: numero;
- `boolean`: verdadeiro ou falso;
- `null`: vazio intencional;
- `undefined`: valor ausente;
- array: lista;
- object: conjunto de chaves e valores.

## Explicando do zero

Em JavaScript eu posso fazer:

```js
let idade = 25;
idade = "vinte e cinco";
```

JavaScript aceita, mas isso pode causar bug.

Em TypeScript:

```ts
let idade: number = 25;
idade = "vinte e cinco"; // erro
```

TypeScript me avisa antes.

## Primitivos

```ts
const nome: string = "Marcos";
const idade: number = 25;
const estudando: boolean = true;
```

Mas se o valor for obvio, posso deixar inferir:

```ts
const nome = "Marcos";
const idade = 25;
const estudando = true;
```

## Array

```ts
const nomes: string[] = ["Ana", "Marcos"];
const idades: number[] = [20, 25, 30];
```

Array de objetos:

```ts
type Usuario = {
  id: string;
  nome: string;
};

const usuarios: Usuario[] = [
  { id: "1", nome: "Ana" },
  { id: "2", nome: "Marcos" },
];
```

## Objeto

```ts
type Usuario = {
  id: string;
  nome: string;
  isAdmin: boolean;
};
```

Esse tipo diz que um usuario precisa ter:

- `id` como string;
- `nome` como string;
- `isAdmin` como boolean.

## Campo opcional

```ts
type Usuario = {
  id: string;
  nome: string;
  avatarUrl?: string;
};
```

`avatarUrl?` significa que pode existir ou nao.

## Null e undefined

```ts
let selecionado: string | null = null;
```

Uso `null` quando quero representar vazio de proposito.

`undefined` normalmente significa que algo nao foi definido.

## Exemplo mais real

```ts
type Produto = {
  id: string;
  nome: string;
  preco: number;
  emEstoque: boolean;
  descricao?: string;
};

const produto: Produto = {
  id: "p1",
  nome: "Teclado",
  preco: 199.9,
  emEstoque: true,
};
```

## Pegadinhas

- `String` com S maiusculo nao e o normal; use `string`.
- `Number` com N maiusculo nao e o normal; use `number`.
- Campo opcional pode ser `undefined`.
- Array vazio pode precisar de tipo.
- Nao use `any` como fuga.

## Resumo mental

Tipo basico e o vocabulario inicial do TypeScript. Antes de tipo avancado, eu preciso saber descrever texto, numero, booleano, lista e objeto.

## Exercicios para fixar

1. Crie um tipo `Pessoa` com `nome`, `idade` e `estudando`.
2. Crie um array `Pessoa[]`.
3. Adicione um campo opcional `avatarUrl`.
4. Crie uma variavel que pode ser `string` ou `null`.

## Como saber que eu entendi

- Eu sei diferenciar `string`, `number` e `boolean`.
- Eu sei criar tipo de objeto.
- Eu sei criar array tipado.
- Eu sei quando um campo e opcional.

## Relacionado

- [[Inferencia de Tipos]]
- [[Arrays Objetos e Funcoes em TypeScript]]

