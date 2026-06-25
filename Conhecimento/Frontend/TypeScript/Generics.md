# Generics

## O que eu preciso lembrar

Generic e uma forma de criar tipo reutilizavel sem perder a informacao do tipo original.

Resumo simples: generic e uma variavel de tipo.

## Explicando do zero

Sem generic, eu poderia fazer:

```ts
function primeiroString(items: string[]) {
  return items[0];
}

function primeiroNumber(items: number[]) {
  return items[0];
}
```

Isso repete a mesma ideia para tipos diferentes.

Com generic:

```ts
function primeiro<T>(items: T[]): T | undefined {
  return items[0];
}
```

Agora funciona com qualquer tipo:

```ts
const nome = primeiro(["Ana", "Marcos"]);
const numero = primeiro([1, 2, 3]);
```

TypeScript entende:

- `nome` e `string | undefined`;
- `numero` e `number | undefined`.

## O que significa `<T>`

`T` e so um nome.

Poderia ser:

```ts
function primeiro<Item>(items: Item[]): Item | undefined {
  return items[0];
}
```

Muita gente usa `T` por convencao.

## Exemplo com resposta de API

```ts
type ApiResponse<T> = {
  data: T;
  error: string | null;
};
```

Uso com usuario:

```ts
type User = {
  id: string;
  name: string;
};

const userResponse: ApiResponse<User> = {
  data: { id: "1", name: "Ana" },
  error: null,
};
```

Uso com produtos:

```ts
type Product = {
  id: string;
  name: string;
  price: number;
};

const productsResponse: ApiResponse<Product[]> = {
  data: [{ id: "1", name: "Teclado", price: 199 }],
  error: null,
};
```

Mesma estrutura, dados diferentes.

## Generic com constraint

As vezes eu preciso garantir que o tipo tenha algum campo.

```ts
function getId<T extends { id: string }>(item: T) {
  return item.id;
}
```

Agora qualquer coisa pode entrar, desde que tenha `id: string`.

## Quando usar

- Funcoes utilitarias.
- Respostas de API.
- Componentes reutilizaveis.
- Hooks customizados.
- Estruturas que preservam o tipo recebido.

## Quando nao usar

- Quando um tipo simples resolve.
- Quando o generic nao adiciona seguranca.
- Quando deixa a leitura mais dificil sem necessidade.

## Pegadinhas

- Generic nao e para "deixar avancado"; e para preservar relacao entre tipos.
- Se voce usa `<T>` mas nao reaproveita `T`, provavelmente nao precisa de generic.
- Nome bom ajuda: `Item`, `Data`, `Value` podem ser melhores que `T` em casos maiores.

## Resumo mental

Generic e tipo flexivel com memoria. Ele deixa a funcao aceitar varios tipos, mas sem esquecer qual tipo entrou.

## Exercicios para fixar

1. Crie uma funcao `ultimo<T>` que retorna o ultimo item de um array.
2. Crie um tipo `ApiResponse<T>`.
3. Use `ApiResponse<User>`.
4. Use `ApiResponse<Product[]>`.
5. Crie uma funcao `getId<T extends { id: string }>`.

## Como saber que eu entendi

- Eu sei explicar `<T>` sem decorar.
- Eu sei criar uma funcao generic simples.
- Eu sei usar generic em resposta de API.
- Eu sei quando generic e exagero.

## Relacionado

- [[Utility Types]]
- [[TypeScript com React]]

