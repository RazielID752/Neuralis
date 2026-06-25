# DIP: Dependency Inversion Principle

## O que eu preciso lembrar

Regra importante nao deveria depender diretamente de detalhe externo.

No frontend, detalhe externo pode ser:

- `fetch`;
- localStorage;
- analytics;
- biblioteca de pagamento;
- SDK externo.

## Exemplo ruim

```ts
async function createUser(user: User) {
  const response = await fetch("/api/users", {
    method: "POST",
    body: JSON.stringify(user),
  });

  return response.json();
}
```

A regra esta presa ao `fetch`.

## Melhor com dependencia injetada

```ts
type UserRepository = {
  create: (user: User) => Promise<User>;
};

async function createUser(user: User, repository: UserRepository) {
  if (!user.name.trim()) {
    throw new Error("Nome obrigatorio");
  }

  return repository.create(user);
}
```

Implementacao com fetch:

```ts
const userRepository: UserRepository = {
  async create(user) {
    const response = await fetch("/api/users", {
      method: "POST",
      body: JSON.stringify(user),
    });

    return response.json();
  },
};
```

## Por que ajuda

Agora posso testar regra sem chamar API real.

```ts
const fakeRepository = {
  create: async (user: User) => user,
};
```

## Quando nao usar

Nao preciso disso para todo fetch simples.

Use quando:

- regra e importante;
- precisa testar isolado;
- dependencia externa pode trocar;
- codigo esta acoplado demais.

## Pegadinhas

- Criar interface para tudo.
- Complicar feature simples.
- Confundir DIP com "usar classe".

## Resumo mental

DIP e fazer regra depender de contrato, nao de detalhe.

## Relacionado

- [[Clean Architecture]]
- [[Camada de API]]

