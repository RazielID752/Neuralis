# Exercicios de Logica para Frontend

## O que eu preciso lembrar

Logica melhora praticando problemas pequenos com dados parecidos com frontend.

## Exercicio 1: filtrar usuarios ativos

Entrada:

```ts
type User = {
  id: string;
  name: string;
  active: boolean;
};
```

Objetivo:

Retornar apenas usuarios ativos.

## Exercicio 2: formatar preco

Entrada:

```ts
const price = 199.9;
```

Objetivo:

Retornar:

```txt
R$ 199.90
```

## Exercicio 3: agrupar tarefas por status

Entrada:

```ts
type Task = {
  id: string;
  title: string;
  done: boolean;
};
```

Objetivo:

Retornar:

```ts
{
  done: Task[];
  pending: Task[];
}
```

## Exercicio 4: criar opcoes para select

Entrada:

```ts
type User = {
  id: string;
  name: string;
};
```

Objetivo:

Retornar:

```ts
type Option = {
  value: string;
  label: string;
};
```

## Exercicio 5: validar formulario

Entrada:

```ts
type FormData = {
  name: string;
  email: string;
};
```

Objetivo:

Retornar lista de erros.

## Como praticar

Para cada exercicio:

1. escreva entrada;
2. escreva saida esperada;
3. liste passos;
4. crie funcoes pequenas;
5. teste com 2 ou 3 exemplos.

## Relacionado

- [[Como Quebrar um Problema]]
- [[Refatorando Funcao Grande]]

