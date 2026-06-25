# Heranca

## O que eu preciso lembrar

Herança permite uma classe herdar comportamento de outra.

## Exemplo

```ts
class Animal {
  constructor(public name: string) {}

  eat() {
    return `${this.name} esta comendo`;
  }
}

class Dog extends Animal {
  bark() {
    return `${this.name} latiu`;
  }
}
```

## Problema

Herança pode parecer boa no começo, mas criar hierarquia profunda costuma complicar.

```txt
Component
  FormComponent
    ValidatedFormComponent
      AsyncValidatedFormComponent
```

Isso fica dificil de mudar.

## No frontend moderno

React moderno prefere composição em vez de herança.

Em vez de herdar, eu componho componentes e funções.

## Pegadinhas

- Usar herança para reutilizar pouco codigo.
- Criar árvore de classes grande.
- Filho quebrar expectativa do pai.

## Resumo mental

Herança é "é um tipo de". Use pouco e com cuidado.

## Relacionado

- [[Composicao vs Heranca]]
- [[LSP Liskov Substitution Principle]]

