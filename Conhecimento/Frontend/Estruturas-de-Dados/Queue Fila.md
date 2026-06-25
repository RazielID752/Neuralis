# Queue: Fila

## O que eu preciso lembrar

Queue e uma fila: o primeiro que entra e o primeiro que sai.

Nome tecnico: FIFO.

```txt
First In, First Out
```

## Exemplo mental

Fila de atendimento:

- quem chega primeiro, sai primeiro.

## Em JavaScript

```ts
const queue: string[] = [];

queue.push("notificacao-1");
queue.push("notificacao-2");

const first = queue.shift(); // notificacao-1
```

## Quando aparece no frontend

- fila de notificacoes;
- tarefas pendentes;
- upload em ordem;
- processamento em background;
- event loop.

## Pegadinhas

- `shift` em arrays grandes pode ser custoso.
- Para fila grande, pode precisar de estrutura melhor.
- Para casos simples de frontend, array costuma bastar.

## Resumo mental

Queue e "primeiro entra, primeiro sai".

## Relacionado

- [[Stack Pilha]]
- [[Conhecimento/Frontend/JavaScript/Event Loop|Event Loop]]

