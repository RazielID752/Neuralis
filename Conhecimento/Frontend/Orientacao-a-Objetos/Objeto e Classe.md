# Objeto e Classe

## O que eu preciso lembrar

Objeto e uma coisa com dados.

Classe e um molde para criar objetos.

## Objeto simples

```ts
const user = {
  name: "Marcos",
  age: 25,
};
```

## Objeto com metodo

```ts
const user = {
  name: "Marcos",
  sayHello() {
    return `Ola, ${this.name}`;
  },
};
```

## Classe

```ts
class User {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  sayHello() {
    return `Ola, ${this.name}`;
  }
}

const user = new User("Marcos");
```

## Com TypeScript mais curto

```ts
class User {
  constructor(public name: string) {}

  sayHello() {
    return `Ola, ${this.name}`;
  }
}
```

## Quando usar classe

- quando faz sentido juntar estado e comportamento;
- quando preciso criar varias instancias parecidas;
- quando uma biblioteca/framework usa classes;
- quando modela entidade com regras.

## Quando nao usar

- para objeto simples de dados;
- para função utilitaria simples;
- so para parecer "mais profissional".

## Resumo mental

Classe e molde. Objeto e instancia ou valor real.

## Relacionado

- [[Encapsulamento]]
- [[Conhecimento/Frontend/JavaScript/Arrays e Objetos|Arrays e Objetos]]

