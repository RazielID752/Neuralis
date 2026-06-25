# TypeScript

## O que eu preciso lembrar

TypeScript e JavaScript com tipos.

Ele nao muda o que o JavaScript faz no navegador. Ele me ajuda antes, no editor, mostrando quando estou passando dado errado, esquecendo campo ou usando uma funcao de forma errada.

## Como eu vou estudar TypeScript

Eu nao preciso decorar todos os tipos avancados de uma vez.

O caminho e:

1. entender tipos basicos;
2. aprender a tipar objetos e funcoes;
3. entender unions;
4. entender narrowing;
5. usar generics quando fizer sentido;
6. aplicar isso em React.

## Guia principal

- [[TypeScript do Zero ao Avancado]]

## Ordem recomendada

### 1. Base

- [[Tipos Basicos]]
- [[Inferencia de Tipos]]
- [[Arrays Objetos e Funcoes em TypeScript]]

Objetivo: entender como TypeScript enxerga valores comuns.

### 2. Modelar possibilidades

- [[Union Types e Literal Types]]
- [[Discriminated Unions]]
- [[Narrowing]]
- [[Type Guards]]
- [[Any Unknown e Never]]

Objetivo: representar valores que podem ter mais de uma forma sem perder seguranca.

### 3. Organizar tipos

- [[Type Alias vs Interface]]
- [[Utility Types]]

Objetivo: criar tipos reutilizaveis sem deixar tudo confuso.

### 4. Reutilizar tipos

- [[Generics]]
- [[Satisfies]]

Objetivo: criar funcoes e estruturas que funcionam com varios tipos sem usar `any`.

### 5. Usar com React

- [[TypeScript com React]]

Objetivo: tipar props, children, eventos, state e componentes sem brigar com o TypeScript.

## Perguntas que eu sempre devo fazer

- Qual e o formato desse dado?
- Esse campo sempre existe ou e opcional?
- Esse valor pode ter quais possibilidades?
- Eu preciso escrever o tipo ou o TypeScript ja consegue inferir?
- Estou usando `any` porque faz sentido ou porque estou fugindo do erro?
- Esse tipo ajuda a entender o codigo ou esta complicando?

## Pegadinhas grandes de TypeScript

- TypeScript nao valida dados em tempo de execucao sozinho.
- `any` desliga a protecao.
- `unknown` e mais seguro que `any`.
- Tipo opcional `?` nao e a mesma coisa que `null`.
- `type` e `interface` sao parecidos, mas nao exatamente iguais.
- Generics nao sao magia; eles so guardam relacao entre tipos.
- As vezes o melhor tipo e o mais simples.

## Resumo mental

TypeScript serve para explicar ao codigo qual formato os dados devem ter. Se o tipo fica mais confuso que o problema, eu provavelmente modelei demais.
