# Narrowing

## O que eu preciso lembrar

Narrowing e quando eu ajudo o TypeScript a entender qual tipo exato eu tenho em determinado ponto do codigo.

Traduzindo mentalmente: "afunilar o tipo".

## Explicando do zero

Se uma funcao recebe `string | number`, TypeScript nao sabe qual dos dois chegou.

```ts
function formatar(valor: string | number) {
  return valor.toUpperCase(); // erro
}
```

Erro porque `number` nao tem `toUpperCase`.

Preciso checar antes:

```ts
function formatar(valor: string | number) {
  if (typeof valor === "string") {
    return valor.toUpperCase();
  }

  return valor.toFixed(2);
}
```

Dentro do `if`, TypeScript sabe que e string. Depois, sabe que sobrou number.

## `typeof`

Uso para tipos primitivos:

```ts
function mostrar(valor: string | number | boolean) {
  if (typeof valor === "string") {
    return valor.trim();
  }

  if (typeof valor === "number") {
    return valor.toFixed(2);
  }

  return valor ? "sim" : "nao";
}
```

## Checando campo em objeto

```ts
type Usuario = {
  nome: string;
  email?: string;
};

function mostrarEmail(usuario: Usuario) {
  if (usuario.email) {
    return usuario.email.toLowerCase();
  }

  return "Sem email";
}
```

## Discriminated union

Esse e o narrowing mais importante em apps.

```ts
type State =
  | { status: "loading" }
  | { status: "success"; data: string[] }
  | { status: "error"; message: string };

function render(state: State) {
  if (state.status === "success") {
    return state.data.join(", ");
  }

  if (state.status === "error") {
    return state.message;
  }

  return "Carregando...";
}
```

Quando `status` e `"success"`, TypeScript sabe que existe `data`.

Quando `status` e `"error"`, sabe que existe `message`.

## Type guard

Type guard e uma funcao que verifica um tipo.

```ts
type User = {
  id: string;
  name: string;
};

function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value
  );
}
```

Uso:

```ts
function handle(value: unknown) {
  if (isUser(value)) {
    console.log(value.name);
  }
}
```

## Pegadinhas

- `typeof null` retorna `"object"`, entao cuidado.
- Checar truthy pode remover `""` e `0`, nao so `null` e `undefined`.
- Narrowing nao valida API inteira magicamente.
- Para dados externos, schemas como Zod podem ajudar.

## Resumo mental

Narrowing e checar antes de usar. Eu provo para o TypeScript que aquele valor e mais especifico.

## Exercicios para fixar

1. Crie uma funcao que recebe `string | number`.
2. Use `typeof` para tratar cada caso.
3. Crie uma union com `status`.
4. Acesse campos diferentes dependendo do status.

## Como saber que eu entendi

- Eu sei por que `string | number` precisa de checagem.
- Eu sei usar `typeof`.
- Eu entendo discriminated union.
- Eu sei que dados externos ainda precisam ser validados.

## Relacionado

- [[Union Types e Literal Types]]
- [[Any Unknown e Never]]

