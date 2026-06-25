# Inferencia de Tipos

## O que eu preciso lembrar

Inferencia e quando o TypeScript entende o tipo sozinho.

Eu nao preciso escrever tipo em tudo.

## Explicando do zero

Quando eu escrevo:

```ts
const nome = "Marcos";
```

TypeScript ja entende que `nome` e uma string.

Quando escrevo:

```ts
let idade = 25;
```

Ele entende que `idade` e number.

Ou seja: o TypeScript olha para o valor e deduz o tipo.

## Exemplo ruim

```ts
const nome: string = "Marcos";
const idade: number = 25;
const ativo: boolean = true;
```

Isso funciona, mas e repetitivo. O TypeScript ja sabia esses tipos.

## Exemplo melhor

```ts
const nome = "Marcos";
const idade = 25;
const ativo = true;
```

Menos codigo, mesma seguranca.

## Quando eu devo escrever o tipo

Escrevo o tipo quando:

- o valor inicial nao deixa claro;
- quero limitar possibilidades;
- estou criando objeto importante;
- estou tipando parametro de funcao;
- estou modelando resposta de API;
- quero documentar intencao.

Exemplo:

```ts
type Status = "idle" | "loading" | "success" | "error";

let status: Status = "idle";
```

Aqui vale escrever o tipo porque nao quero qualquer string.

## Pegadinha com array vazio

```ts
const items = [];
```

Dependendo da configuracao, TypeScript pode nao saber que tipo de item esse array deve guardar.

Melhor:

```ts
const names: string[] = [];
```

ou:

```ts
type User = {
  id: string;
  name: string;
};

const users: User[] = [];
```

## Como isso aparece em React

Com `useState`, as vezes o TypeScript entende:

```tsx
const [count, setCount] = useState(0);
```

Ele sabe que `count` e number.

Mas com array vazio, preciso ajudar:

```tsx
type Task = {
  id: string;
  title: string;
};

const [tasks, setTasks] = useState<Task[]>([]);
```

## Resumo mental

Se o TypeScript ja entendeu, nao preciso repetir. Eu escrevo tipos quando quero guiar, limitar ou explicar melhor.

## Exercicios para fixar

1. Crie `const nome = "Ana"` e observe o tipo.
2. Crie `let status = "loading"` e depois tente mudar para outro texto.
3. Crie um array vazio tipado como `string[]`.
4. Crie um `useState` de array tipado.

## Relacionado

- [[Tipos Basicos]]
- [[TypeScript com React]]

