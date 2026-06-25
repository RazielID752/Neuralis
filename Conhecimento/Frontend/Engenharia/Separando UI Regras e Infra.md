# Separando UI, Regras e Infra

## O que eu preciso lembrar

Um jeito simples de organizar pensamento:

- UI: o que aparece;
- Regras: o que deve acontecer;
- Infra: como conversa com mundo externo.

## UI

React components.

```tsx
function TaskCard({ task }: { task: Task }) {
  return <article>{task.title}</article>;
}
```

## Regras

Funcoes puras.

```ts
function canCompleteTask(task: Task) {
  return !task.done;
}
```

## Infra

API, storage, analytics.

```ts
async function updateTask(task: Task) {
  return fetch(`/api/tasks/${task.id}`, {
    method: "PATCH",
    body: JSON.stringify(task),
  });
}
```

## Por que separar

Se regra fica dentro da UI, fica dificil testar e reutilizar.

Se API fica espalhada na UI, fica dificil trocar endpoint ou tratar erro.

## Exemplo de fluxo

```txt
Usuario clica -> UI chama handler -> regra decide -> infra salva -> UI atualiza
```

## Pegadinhas

- Colocar regra de negocio em componente visual.
- Colocar fetch dentro de qualquer botao.
- Colocar regra importante em arquivo de estilo/visual.

## Resumo mental

UI mostra. Regra decide. Infra conecta.

## Relacionado

- [[Clean Architecture]]
- [[Separacao de Responsabilidades]]

