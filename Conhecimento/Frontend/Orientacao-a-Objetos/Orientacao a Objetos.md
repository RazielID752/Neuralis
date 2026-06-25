# Orientacao a Objetos

## O que eu preciso lembrar

Orientacao a objetos e uma forma de organizar codigo em torno de objetos que juntam dados e comportamentos.

No JavaScript/TypeScript, eu posso usar OOP, mas nao preciso usar para tudo.

## Ordem recomendada

- [[Objeto e Classe]]
- [[Encapsulamento]]
- [[Heranca]]
- [[Composicao vs Heranca]]
- [[Polimorfismo]]
- [[OOP no Frontend]]

## Ideia simples

Objeto:

```ts
const user = {
  name: "Marcos",
  sayHello() {
    return `Ola, ${this.name}`;
  },
};
```

Classe:

```ts
class User {
  constructor(public name: string) {}

  sayHello() {
    return `Ola, ${this.name}`;
  }
}
```

## Perguntas que eu sempre devo fazer

- Isso precisa ser classe?
- Uma função simples resolveria?
- Esse objeto tem comportamento ou so dados?
- Estou usando herança sem necessidade?
- Composição seria mais simples?

## Pegadinhas grandes

- Usar classe para tudo.
- Criar herança profunda.
- Misturar estado mutavel demais.
- Achar que OOP e obrigatoria para arquitetura.

## Resumo mental

OOP e uma ferramenta. Em frontend moderno, eu uso quando ajuda a organizar comportamento, nao por obrigação.

