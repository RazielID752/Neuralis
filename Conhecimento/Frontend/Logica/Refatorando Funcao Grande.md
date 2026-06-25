# Refatorando Funcao Grande

## O que eu preciso lembrar

Refatorar e mudar a forma sem mudar o comportamento.

## Funcao embolada

```ts
function processUsers(users: User[]) {
  const result = [];

  for (const user of users) {
    if (user.active && user.email.includes("@")) {
      result.push({
        id: user.id,
        label: `${user.name} <${user.email}>`,
      });
    }
  }

  return result;
}
```

Funciona, mas mistura:

- verificar ativo;
- validar email;
- montar label;
- transformar usuario.

## Separando

```ts
function isActive(user: User) {
  return user.active;
}

function hasValidEmail(user: User) {
  return user.email.includes("@");
}

function formatUserLabel(user: User) {
  return `${user.name} <${user.email}>`;
}

function toUserOption(user: User) {
  return {
    id: user.id,
    label: formatUserLabel(user),
  };
}

function processUsers(users: User[]) {
  return users.filter(isActive).filter(hasValidEmail).map(toUserOption);
}
```

## O que melhorou

- cada regra tem nome;
- cada parte pode ser testada;
- o fluxo principal ficou legivel;
- menos chance de se perder.

## Passo a passo para refatorar

1. Nao mude tudo de uma vez.
2. Ache um bloco com responsabilidade clara.
3. Extraia para funcao.
4. Dê nome bom.
5. Rode/teste.
6. Repita.

## Resumo mental

Eu extraio intenção, nao só linhas.

## Relacionado

- [[Como Criar Funcoes Pequenas]]
- [[Teste Unitario]]

