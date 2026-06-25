# Clean Code

## O que eu preciso lembrar

Clean Code e codigo facil de ler, entender, mudar e testar.

Nao e codigo "chique". E codigo claro.

## Nome bom

Ruim:

```ts
const d = users.filter((u) => u.a);
```

Melhor:

```ts
const activeUsers = users.filter((user) => user.active);
```

Nome bom reduz comentario desnecessario.

## Funcao pequena

Ruim:

```ts
function handleUsers(users: User[]) {
  const result = users
    .filter((user) => user.active && user.email.includes("@"))
    .map((user) => ({
      id: user.id,
      label: `${user.name} <${user.email}>`,
    }));

  return result;
}
```

Melhor:

```ts
function isActiveUser(user: User) {
  return user.active;
}

function hasValidEmail(user: User) {
  return user.email.includes("@");
}

function toUserOption(user: User) {
  return {
    id: user.id,
    label: `${user.name} <${user.email}>`,
  };
}

function getUserOptions(users: User[]) {
  return users.filter(isActiveUser).filter(hasValidEmail).map(toUserOption);
}
```

## Uma funcao, uma intencao

Funcao ruim mistura:

- validar;
- transformar;
- buscar API;
- atualizar tela;
- mostrar erro.

Funcao boa tem uma intencao clara.

## Comentario bom vs comentario ruim

Comentario ruim explica codigo confuso:

```ts
// verifica se usuario esta ativo
if (user.active) {}
```

Melhor usar nome claro.

Comentario bom explica motivo:

```ts
// A API antiga retorna preco em centavos.
const price = product.priceInCents / 100;
```

## Evitar booleano misterioso

Ruim:

```ts
createUser(data, true);
```

Melhor:

```ts
createUser(data, { sendWelcomeEmail: true });
```

## Pegadinhas

- Função pequena demais sem necessidade.
- Nome bonito mas mentiroso.
- Comentario tentando salvar codigo ruim.
- Abstração cedo demais.

## Aprofundar

- [[Code Smells no Frontend]]
- [[Refatoracao Guiada]]
- [[Padroes de Projeto no Frontend]]
- [[Decisoes Arquiteturais]]

## Resumo mental

Clean Code e gentileza com meu eu do futuro.

## Relacionado

- [[Como Criar Funcoes Pequenas]]
- [[Refatorando Funcao Grande]]
- [[Checklist de Codigo Limpo]]
