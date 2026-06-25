# SOLID

## O que eu preciso lembrar

SOLID e um conjunto de principios para criar codigo mais facil de mudar.

No frontend, eu uso como guia, nao como religiao.

## S: Single Responsibility Principle

Leia tambem: [[SRP Single Responsibility Principle]].

Uma coisa deve ter uma responsabilidade principal.

Ruim:

```tsx
function UserPage() {
  // busca API
  // valida dados
  // transforma dados
  // renderiza tabela
  // controla modal
}
```

Melhor separar:

- API;
- hook;
- componente de tabela;
- componente de modal;
- funcoes de transformacao.

## O: Open Closed Principle

Leia tambem: [[OCP Open Closed Principle]].

Aberto para extensao, fechado para modificacao.

Exemplo simples:

Ruim:

```ts
function getButtonClass(variant: string) {
  if (variant === "primary") return "bg-black";
  if (variant === "danger") return "bg-red";
  return "bg-white";
}
```

Melhor:

```ts
const buttonVariants = {
  primary: "bg-black",
  danger: "bg-red",
  secondary: "bg-white",
};
```

Para adicionar variante, adiciono no mapa.

## L: Liskov Substitution Principle

Leia tambem: [[LSP Liskov Substitution Principle]].

Se algo promete se comportar de um jeito, suas variacoes nao devem quebrar essa promessa.

No frontend, penso assim:

Se um componente aceita as mesmas props de botao, ele deve se comportar como botao.

## I: Interface Segregation Principle

Leia tambem: [[ISP Interface Segregation Principle]].

Nao obrigar alguem a depender do que nao usa.

Ruim:

```ts
type UserCardProps = {
  user: FullUserWithPermissionsAndSettings;
};
```

Melhor:

```ts
type UserCardProps = {
  user: {
    name: string;
    avatarUrl?: string;
  };
};
```

O componente recebe so o que precisa.

## D: Dependency Inversion Principle

Leia tambem: [[DIP Dependency Inversion Principle]].

Codigo de regra nao deveria depender diretamente de detalhe externo.

Ruim:

```ts
async function saveUser(user: User) {
  return fetch("/api/users", {
    method: "POST",
    body: JSON.stringify(user),
  });
}
```

Melhor mentalmente:

```ts
type UserRepository = {
  save: (user: User) => Promise<void>;
};

async function createUser(user: User, repository: UserRepository) {
  return repository.save(user);
}
```

## Pegadinhas

- Tentar aplicar SOLID em tudo.
- Criar abstrações antes da necessidade.
- Achar que SOLID exige classe.
- Complicar codigo simples.

## Resumo mental

SOLID me ajuda a perguntar: esse codigo vai ser facil de mudar sem quebrar tudo?

## Relacionado

- [[Separacao de Responsabilidades]]
- [[Clean Architecture]]
- [[Clean Code]]
