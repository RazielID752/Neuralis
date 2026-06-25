# TypeScript do Zero ao Avancado

## O que e TypeScript

TypeScript e JavaScript com um sistema de tipos por cima.

JavaScript roda no navegador e no Node.js. TypeScript nao roda diretamente: ele e analisado e transformado em JavaScript.

Objetivo principal:

- encontrar erros antes de executar;
- documentar a intencao dos dados;
- melhorar autocomplete e refatoracao;
- deixar projetos grandes mais seguros.

## O problema que TypeScript resolve

Em JavaScript, este erro so aparece em tempo de execucao:

```js
function greet(user) {
  return user.name.toUpperCase();
}

greet(null);
```

Em TypeScript, voce descreve o formato esperado:

```ts
type User = {
  name: string;
};

function greet(user: User) {
  return user.name.toUpperCase();
}
```

Agora o editor consegue avisar quando voce passa algo errado.

## Tipos primitivos

Leia tambem: [[Tipos Basicos]] e [[Inferencia de Tipos]].

```ts
const name: string = "Ana";
const age: number = 30;
const isAdmin: boolean = false;
const nothing: null = null;
const notDefined: undefined = undefined;
```

Na pratica, voce raramente precisa tipar valores obvios:

```ts
const name = "Ana";
const age = 30;
```

TypeScript infere o tipo.

## Arrays

Leia tambem: [[Arrays Objetos e Funcoes em TypeScript]].

```ts
const names: string[] = ["Ana", "Bruno"];
const scores: Array<number> = [10, 8, 9];
```

Array de objetos:

```ts
type Product = {
  id: string;
  name: string;
  price: number;
};

const products: Product[] = [];
```

## Objetos

Leia tambem: [[Arrays Objetos e Funcoes em TypeScript]].

```ts
type User = {
  id: string;
  name: string;
  email: string;
  isAdmin: boolean;
};
```

Campos opcionais:

```ts
type User = {
  id: string;
  name: string;
  avatarUrl?: string;
};
```

`avatarUrl?: string` significa: pode existir como string ou pode estar ausente.

## Funcoes

Leia tambem: [[Arrays Objetos e Funcoes em TypeScript]].

```ts
function sum(a: number, b: number): number {
  return a + b;
}
```

Muitas vezes o retorno pode ser inferido:

```ts
function sum(a: number, b: number) {
  return a + b;
}
```

Funcao como valor:

```ts
type OnSelect = (id: string) => void;
```

## Union types

Leia tambem: [[Union Types e Literal Types]].

Union permite mais de uma possibilidade:

```ts
type Status = "idle" | "loading" | "success" | "error";

let status: Status = "idle";
```

Isso e muito melhor que `string`, porque limita os valores aceitos.

```ts
status = "banana"; // erro
```

## Literal types

Tipos literais representam valores exatos:

```ts
type ButtonVariant = "primary" | "secondary" | "danger";
```

Muito usado em componentes:

```ts
type ButtonProps = {
  variant: "primary" | "secondary";
};
```

## Narrowing

Leia tambem: [[Narrowing]].

Narrowing e quando TypeScript reduz um tipo amplo para um tipo mais especifico.

```ts
function format(value: string | number) {
  if (typeof value === "string") {
    return value.trim();
  }

  return value.toFixed(2);
}
```

Dentro do `if`, TypeScript sabe que `value` e string. Fora dele, no `return`, sabe que e number.

## Type aliases vs interfaces

Leia tambem: [[Type Alias vs Interface]].

`type`:

```ts
type User = {
  id: string;
  name: string;
};
```

`interface`:

```ts
interface User {
  id: string;
  name: string;
}
```

Regra simples:

- use `type` por padrao;
- use `interface` quando estiver modelando APIs extensivas ou seguindo padrao do projeto.

## Generics

Leia tambem: [[Generics]].

Generics permitem preservar informacao de tipo sem saber o tipo antes.

```ts
function identity<T>(value: T): T {
  return value;
}

const a = identity("texto"); // string
const b = identity(123); // number
```

Exemplo real com API:

```ts
type ApiResponse<T> = {
  data: T;
  error: string | null;
};

type User = {
  id: string;
  name: string;
};

const response: ApiResponse<User> = {
  data: { id: "1", name: "Ana" },
  error: null,
};
```

## Utility types

Leia tambem: [[Utility Types]].

TypeScript vem com tipos utilitarios.

`Partial` deixa campos opcionais:

```ts
type UserUpdate = Partial<User>;
```

`Pick` escolhe campos:

```ts
type UserPreview = Pick<User, "id" | "name">;
```

`Omit` remove campos:

```ts
type PublicUser = Omit<User, "email">;
```

`Record` cria mapas:

```ts
type UsersById = Record<string, User>;
```

## Tipando componentes React

Leia tambem: [[TypeScript com React]].

```tsx
type ButtonProps = {
  children: React.ReactNode;
  onClick: () => void;
  disabled?: boolean;
};

function Button({ children, onClick, disabled = false }: ButtonProps) {
  return (
    <button onClick={onClick} disabled={disabled}>
      {children}
    </button>
  );
}
```

Evento de input:

```tsx
function SearchInput() {
  function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
    console.log(event.target.value);
  }

  return <input onChange={handleChange} />;
}
```

Submit:

```tsx
function Form() {
  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault();
  }

  return <form onSubmit={handleSubmit} />;
}
```

## `any`, `unknown` e `never`

Leia tambem: [[Any Unknown e Never]].

`any` desliga o TypeScript:

```ts
let value: any = "texto";
value.foo.bar.baz();
```

Evite `any` quando possivel.

`unknown` significa "nao sei o tipo ainda":

```ts
function parse(value: unknown) {
  if (typeof value === "string") {
    return value.toUpperCase();
  }
}
```

`never` representa algo que nao deveria acontecer:

```ts
function assertNever(value: never): never {
  throw new Error(`Valor inesperado: ${value}`);
}
```

## Nivel avancado

Topicos avancados para estudar depois:

- generics com constraints;
- conditional types;
- mapped types;
- template literal types;
- discriminated unions;
- type guards;
- inferencia profunda;
- `satisfies`;
- tipagem de bibliotecas;
- tipos para APIs e schemas.

Exemplo de discriminated union:

```ts
type Result =
  | { status: "success"; data: string }
  | { status: "error"; message: string };

function render(result: Result) {
  if (result.status === "success") {
    return result.data;
  }

  return result.message;
}
```

## Ordem de estudo

1. Tipos primitivos.
2. Arrays e objetos.
3. Funcoes.
4. Type aliases.
5. Campos opcionais.
6. Union types.
7. Narrowing.
8. Interfaces.
9. Generics.
10. Utility types.
11. Tipagem de React.
12. Discriminated unions.
13. Type guards.
14. Mapped types.
15. Conditional types.

## Erros comuns

- Usar `any` para fugir do problema.
- Tipar tudo manualmente sem aproveitar inferencia.
- Criar tipos genericos demais.
- Confundir tipo do dado da API com tipo usado na UI.
- Nao representar estados impossiveis como impossiveis.

## Criterio de dominio

Voce esta ficando bom em TypeScript quando consegue:

- modelar dados com clareza;
- evitar `any`;
- usar unions para estados;
- criar generics simples;
- entender mensagens de erro;
- tipar componentes sem brigar com o compilador;
- simplificar tipos quando eles ficam complexos demais.
