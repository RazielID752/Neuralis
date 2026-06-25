# Type Guards

## O que eu preciso lembrar

Type guard e uma checagem que ensina o TypeScript a confiar em um tipo mais especifico.

## Exemplo simples

```ts
function isString(value: unknown): value is string {
  return typeof value === "string";
}
```

Uso:

```ts
function format(value: unknown) {
  if (isString(value)) {
    return value.toUpperCase();
  }

  return "Valor invalido";
}
```

## Objeto

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

## Pegadinhas

- Type guard mal feito engana o TypeScript.
- `"id" in value` nao garante sozinho que `id` e string.
- Para validação forte de API, schema costuma ser melhor.

## Resumo mental

Type guard e uma ponte entre dado desconhecido e tipo confiavel.

## Relacionado

- [[Any Unknown e Never]]
- [[Validacao de Dados da API]]

