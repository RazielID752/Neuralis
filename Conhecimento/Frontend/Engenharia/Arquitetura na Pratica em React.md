# Arquitetura na Pratica em React

## O que eu preciso lembrar

Arquitetura em React e separar tela, estado, dados, regra e componentes.

## Exemplo de feature

```txt
features/
  tasks/
    api/
      tasks-api.ts
    components/
      task-card.tsx
      task-form.tsx
    hooks/
      use-tasks.ts
    model/
      task-types.ts
      task-rules.ts
    pages/
      tasks-page.tsx
```

## O que fica onde

### api

Chamadas HTTP.

```ts
export async function getTasks() {}
```

### model

Tipos e regras.

```ts
export type Task = {
  id: string;
  title: string;
  done: boolean;
};
```

```ts
export function isTaskDone(task: Task) {
  return task.done;
}
```

### hooks

Logica React.

```ts
export function useTasks() {
  // state, effects, callbacks
}
```

### components

UI da feature.

```tsx
export function TaskCard({ task }: { task: Task }) {}
```

### pages

Compoe a tela.

```tsx
export function TasksPage() {}
```

## Fluxo mental

```txt
Page -> Hook -> API
Page -> Components
Components -> Model types
Rules -> Model
```

## Pegadinhas

- Hook fazendo regra de negocio demais.
- Componente chamando fetch direto.
- Pasta `shared` virando lixeira.
- Feature dependendo de detalhes internos de outra feature.

## Resumo mental

Feature boa junta o que muda junto e separa responsabilidades internas.

## Relacionado

- [[Exemplo de Estrutura de Projeto Frontend]]
- [[Componentes UI vs Feature]]
- [[Camada de API]]

