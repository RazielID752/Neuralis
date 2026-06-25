# ISP: Interface Segregation Principle

## O que eu preciso lembrar

Nao obrigar um componente ou funcao a receber dados que nao usa.

No TypeScript, isso aparece muito em props grandes demais.

## Exemplo ruim

```ts
type FullUser = {
  id: string;
  name: string;
  email: string;
  permissions: string[];
  settings: {
    theme: string;
  };
};

type UserAvatarProps = {
  user: FullUser;
};
```

Se `UserAvatar` so usa `name` e `avatarUrl`, nao precisa receber usuario inteiro.

## Melhor

```ts
type UserAvatarProps = {
  user: {
    name: string;
    avatarUrl?: string;
  };
};
```

## Por que ajuda

- componente depende de menos coisa;
- fica mais facil testar;
- evita acoplamento;
- fica claro o que realmente precisa.

## Exemplo com funcao

Ruim:

```ts
function canShowAdminButton(user: FullUser) {
  return user.permissions.includes("admin");
}
```

Melhor:

```ts
function canShowAdminButton(permissions: string[]) {
  return permissions.includes("admin");
}
```

## Pegadinhas

- Passar objeto gigante por preguiça.
- Criar props muito genericas.
- Fazer componente depender do formato completo da API.

## Resumo mental

Receber so o que usa deixa o codigo menos preso.

## Relacionado

- [[SOLID]]
- [[Props]]
- [[TypeScript com React]]

