# Any, Unknown e Never

## O que eu preciso lembrar

`any` desliga o TypeScript.

`unknown` diz: "eu ainda nao sei o tipo, preciso verificar".

`never` representa algo que nunca deveria acontecer.

## `any`

```ts
let valor: any = "texto";

valor.toUpperCase();
valor.nao.existe.e.mesmo.assim.nao.reclama();
```

Com `any`, TypeScript para de me proteger.

Use apenas quando:

- estou migrando codigo antigo;
- nao tenho alternativa no momento;
- vou trocar por tipo melhor depois.

## `unknown`

`unknown` e mais seguro.

```ts
function processar(valor: unknown) {
  if (typeof valor === "string") {
    return valor.toUpperCase();
  }

  if (typeof valor === "number") {
    return valor.toFixed(2);
  }

  return "Valor desconhecido";
}
```

Antes de usar, preciso checar.

## `never`

`never` aparece quando algo nao deve existir.

```ts
type Status = "success" | "error";

function assertNever(value: never): never {
  throw new Error(`Valor inesperado: ${value}`);
}
```

Uso comum com switch:

```ts
function render(status: Status) {
  switch (status) {
    case "success":
      return "Sucesso";
    case "error":
      return "Erro";
    default:
      return assertNever(status);
  }
}
```

Se eu adicionar outro status depois, TypeScript pode me avisar que faltou tratar.

## Pegadinhas

- `any` parece resolver, mas so esconde o problema.
- `unknown` obriga checagem, por isso e mais seguro.
- `never` e avancado; no comeco, basta saber que significa impossivel.

## Resumo mental

Se eu nao sei o tipo, melhor `unknown` do que `any`. `any` e uma porta aberta para bug.

## Exercicios para fixar

1. Crie uma funcao que recebe `unknown`.
2. Verifique se o valor e string antes de usar `toUpperCase`.
3. Crie um exemplo de union com `assertNever`.

## Relacionado

- [[Narrowing]]
- [[Union Types e Literal Types]]

