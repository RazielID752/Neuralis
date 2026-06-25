# Utility Types

## O que eu preciso lembrar

Utility types sao tipos prontos do TypeScript para transformar outros tipos.

Eles evitam que eu copie e cole tipos parecidos.

## Tipo base

```ts
type Usuario = {
  id: string;
  nome: string;
  email: string;
  idade: number;
};
```

## `Partial`

Deixa todos os campos opcionais.

```ts
type UsuarioUpdate = Partial<Usuario>;
```

Resultado mental:

```ts
type UsuarioUpdate = {
  id?: string;
  nome?: string;
  email?: string;
  idade?: number;
};
```

Bom para formulario de edicao parcial.

## `Pick`

Escolhe alguns campos.

```ts
type UsuarioResumo = Pick<Usuario, "id" | "nome">;
```

Resultado:

```ts
type UsuarioResumo = {
  id: string;
  nome: string;
};
```

## `Omit`

Remove alguns campos.

```ts
type UsuarioSemEmail = Omit<Usuario, "email">;
```

Bom quando quero esconder campo sensivel.

## `Record`

Cria um objeto com chaves e valores tipados.

```ts
type UsuariosPorId = Record<string, Usuario>;
```

Exemplo:

```ts
const usuarios: UsuariosPorId = {
  "1": {
    id: "1",
    nome: "Ana",
    email: "ana@email.com",
    idade: 25,
  },
};
```

## `Required`

Faz todos os campos virarem obrigatorios.

```ts
type UsuarioCompleto = Required<Partial<Usuario>>;
```

## Pegadinhas

- Utility type demais pode deixar o tipo dificil de ler.
- Se ficar confuso, crie um tipo manual explicito.
- `Partial` e util, mas pode deixar campos importantes opcionais demais.

## Resumo mental

Utility types sao atalhos para reaproveitar tipos sem duplicar codigo.

## Exercicios para fixar

1. Crie um tipo `Produto`.
2. Use `Pick` para criar `ProdutoCard`.
3. Use `Omit` para remover `descricao`.
4. Use `Partial` para criar `ProdutoUpdate`.
5. Use `Record` para mapear produtos por id.

## Relacionado

- [[Type Alias vs Interface]]
- [[Generics]]

