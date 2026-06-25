# Entrada, Processamento e Saida

## O que eu preciso lembrar

Quase toda funcao pode ser pensada assim:

```txt
entrada -> processamento -> saida
```

## Exemplo simples

```ts
function double(number: number) {
  return number * 2;
}
```

Entrada: `number`.

Processamento: multiplicar por 2.

Saida: resultado.

## Exemplo com objeto

```ts
type User = {
  firstName: string;
  lastName: string;
};

function getFullName(user: User) {
  return `${user.firstName} ${user.lastName}`;
}
```

Entrada: user.

Processamento: juntar nomes.

Saida: string.

## Exemplo com validação

```ts
function isValidEmail(email: string) {
  return email.includes("@") && email.includes(".");
}
```

Entrada: email.

Processamento: verificar regras.

Saida: boolean.

## Pegadinha

Quando a funcao nao tem entrada clara nem saida clara, ela tende a virar bagunca.

## Resumo mental

Antes de escrever a funcao, eu pergunto: entra o que? sai o que?

## Relacionado

- [[Como Quebrar um Problema]]
- [[Como Criar Funcoes Pequenas]]

