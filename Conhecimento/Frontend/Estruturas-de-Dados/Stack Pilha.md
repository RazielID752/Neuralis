# Stack: Pilha

## O que eu preciso lembrar

Stack e uma pilha: o ultimo que entra e o primeiro que sai.

Nome tecnico: LIFO.

```txt
Last In, First Out
```

## Exemplo mental

Pilha de pratos:

- coloco prato em cima;
- tiro o prato de cima primeiro.

## Em JavaScript

```ts
const stack: string[] = [];

stack.push("pagina-1");
stack.push("pagina-2");

const last = stack.pop(); // pagina-2
```

## Quando aparece no frontend

- historico;
- undo/redo;
- navegação;
- pilha de modais;
- call stack do JavaScript.

## Exemplo undo simples

```ts
const history: string[] = [];

history.push("texto inicial");
history.push("texto editado");

const previous = history.pop();
```

## Pegadinhas

- Stack nao e boa para buscar item no meio.
- Se preciso acessar qualquer item por id, talvez Map seja melhor.

## Resumo mental

Stack e "ultimo entra, primeiro sai".

## Relacionado

- [[Queue Fila]]
- [[Conhecimento/Frontend/JavaScript/Event Loop|Event Loop]]

