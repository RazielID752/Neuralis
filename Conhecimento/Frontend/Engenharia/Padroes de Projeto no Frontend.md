# Padroes de Projeto no Frontend

## O que eu preciso lembrar

Padroes de projeto sao soluções recorrentes para problemas recorrentes.

No frontend, eu uso padroes de forma simples, sem forçar nomes bonitos.

## Container e Presentation

Container cuida de dados/logica.

Presentation cuida de UI.

```tsx
function UsersContainer() {
  const { users, isLoading } = useUsers();

  return <UsersList users={users} isLoading={isLoading} />;
}
```

```tsx
function UsersList({ users, isLoading }: Props) {
  if (isLoading) return <p>Carregando...</p>;
  return users.map((user) => <p key={user.id}>{user.name}</p>);
}
```

## Adapter

Adapter transforma dado externo em formato interno.

```ts
function userApiToUserView(user: ApiUser): UserView {
  return {
    id: user.id,
    name: user.full_name,
  };
}
```

## Factory simples

Cria objeto padronizado.

```ts
function createEmptyTask(): Task {
  return {
    id: crypto.randomUUID(),
    title: "",
    done: false,
  };
}
```

## Strategy simples

Troca comportamento por mapa.

```ts
const sortStrategies = {
  name: (a: User, b: User) => a.name.localeCompare(b.name),
  email: (a: User, b: User) => a.email.localeCompare(b.email),
};
```

## Pegadinhas

- Decorar nomes sem entender problema.
- Aplicar pattern em problema pequeno.
- Criar camada demais.

## Resumo mental

Padrao bom resolve dor real. Se nao tem dor, talvez seja teatro.

## Relacionado

- [[Clean Architecture]]
- [[OCP Open Closed Principle]]
- [[Separando UI Regras e Infra]]

