# Type Alias vs Interface

## O que eu preciso lembrar

`type` e `interface` servem para descrever formatos, principalmente objetos.

Na maioria dos meus casos, posso usar `type` por padrao.

## Type alias

```ts
type Usuario = {
  id: string;
  nome: string;
};
```

`type` tambem pode representar unions:

```ts
type Status = "idle" | "loading" | "success" | "error";
```

E tipos de funcao:

```ts
type OnSelect = (id: string) => void;
```

## Interface

```ts
interface Usuario {
  id: string;
  nome: string;
}
```

Interface e muito usada para formato de objeto.

## Diferenca pratica

`interface` pode ser extendida:

```ts
interface Pessoa {
  nome: string;
}

interface Usuario extends Pessoa {
  id: string;
}
```

`type` pode compor com intersection:

```ts
type Pessoa = {
  nome: string;
};

type Usuario = Pessoa & {
  id: string;
};
```

## Qual eu uso?

Minha regra simples:

- uso `type` por padrao;
- uso `interface` se o projeto ja usa muito interface;
- uso `interface` se estou modelando algo que deve ser extendido;
- uso `type` para union, literal type e funcao.

## Pegadinhas

- Nao vale gastar energia demais brigando entre `type` e `interface` no comeco.
- O importante e o tipo deixar o codigo mais claro.
- Para unions, use `type`.

## Resumo mental

`type` e mais flexivel. `interface` e boa para objetos extensíveis. Para estudar e criar projetos pessoais, `type` como padrao e suficiente.

## Exercicios para fixar

1. Crie um `type Produto`.
2. Crie uma `interface Usuario`.
3. Crie um `type Status` com union.
4. Crie um tipo de funcao `OnClick`.

## Relacionado

- [[Arrays Objetos e Funcoes em TypeScript]]
- [[Union Types e Literal Types]]

