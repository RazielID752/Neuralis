# Union Types e Literal Types

## O que eu preciso lembrar

Union e quando um valor pode ser uma coisa ou outra.

Literal type e quando eu limito o valor a textos ou numeros especificos.

## Explicando do zero

Em JavaScript, eu posso ter:

```js
let status = "loading";
status = "success";
status = "qualquer coisa";
```

Em TypeScript, posso limitar:

```ts
type Status = "idle" | "loading" | "success" | "error";

let status: Status = "loading";

status = "success";
status = "qualquer coisa"; // erro
```

Isso impede estados que nao deveriam existir.

## Union com tipos diferentes

```ts
function formatar(valor: string | number) {
  if (typeof valor === "string") {
    return valor.trim();
  }

  return valor.toFixed(2);
}
```

`valor` pode ser string ou number.

## Literal types

```ts
type ButtonVariant = "primary" | "secondary" | "danger";
```

Isso e melhor que:

```ts
type ButtonVariant = string;
```

Porque `string` aceita qualquer texto.

## Exemplo em React

```tsx
type AlertProps = {
  type: "success" | "error" | "warning";
  message: string;
};

function Alert({ type, message }: AlertProps) {
  return <div data-type={type}>{message}</div>;
}
```

Agora eu nao consigo passar:

```tsx
<Alert type="banana" message="Erro" />
```

## Discriminated union

Esse e um padrao muito importante.

```ts
type RequestState =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: string[] }
  | { status: "error"; message: string };
```

Agora cada status tem os campos certos.

```ts
function render(state: RequestState) {
  if (state.status === "success") {
    return state.data.join(", ");
  }

  if (state.status === "error") {
    return state.message;
  }

  return state.status;
}
```

## Pegadinhas

- Union muito grande pode ficar dificil de ler.
- `string | number` exige checagem antes de usar metodos especificos.
- Literal types sao otimos para status, variantes e modos.

## Resumo mental

Union me deixa dizer: "esse valor so pode ser uma dessas possibilidades".

## Exercicios para fixar

1. Crie um tipo `Tema = "light" | "dark"`.
2. Crie um tipo `Status = "idle" | "loading" | "success" | "error"`.
3. Crie uma funcao que recebe `string | number` e formata cada caso.
4. Crie uma discriminated union para uma resposta de API.

## Relacionado

- [[Narrowing]]
- [[TypeScript com React]]

