# Validacao de Dados da API

## O que eu preciso lembrar

TypeScript nao garante que a API vai mandar o dado certo em tempo de execucao.

## O problema

Eu posso escrever:

```ts
type User = {
  id: string;
  name: string;
};
```

Mas a API pode mandar:

```json
{
  "id": 123,
  "nome": "Marcos"
}
```

TypeScript nao impede isso sozinho.

## Validacao manual simples

```ts
function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value
  );
}
```

## Com schema

Em projetos reais, bibliotecas como Zod podem validar formato.

Ideia mental:

```ts
const UserSchema = z.object({
  id: z.string(),
  name: z.string(),
});
```

## Pegadinhas

- Acreditar que `as User` valida algo. Nao valida.
- Confiar cegamente na API.
- Nao tratar campo ausente.
- Misturar tipo TypeScript com validacao runtime.

## Resumo mental

Tipo ajuda no editor. Validacao protege em runtime.

## Relacionado

- [[Any Unknown e Never]]
- [[Narrowing]]

