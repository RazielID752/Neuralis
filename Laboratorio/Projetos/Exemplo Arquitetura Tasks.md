# Exemplo Arquitetura Tasks

## Objetivo

Praticar uma estrutura de projeto frontend com separacao entre UI, regras e API.

## Estrutura sugerida

```txt
src/
  features/
    tasks/
      api/
        tasks-api.ts
      model/
        task-types.ts
        task-rules.ts
      hooks/
        use-tasks.ts
      components/
        task-card.tsx
        task-list.tsx
        task-form.tsx
      pages/
        tasks-page.tsx
  shared/
    components/
      button.tsx
      input.tsx
```

## Model: tipos

```ts
export type Task = {
  id: string;
  title: string;
  done: boolean;
};
```

## Model: regras

```ts
import { Task } from "./task-types";

export function isTaskDone(task: Task) {
  return task.done;
}

export function getPendingTasks(tasks: Task[]) {
  return tasks.filter((task) => !task.done);
}

export function getDoneTasks(tasks: Task[]) {
  return tasks.filter(isTaskDone);
}
```

## API

```ts
import { Task } from "../model/task-types";

export async function getTasks(): Promise<Task[]> {
  const response = await fetch("/api/tasks");

  if (!response.ok) {
    throw new Error("Erro ao buscar tarefas");
  }

  return response.json();
}
```

## Hook

```tsx
import { useEffect, useState } from "react";
import { getTasks } from "../api/tasks-api";
import { Task } from "../model/task-types";

export function useTasks() {
  const [tasks, setTasks] = useState<Task[]>([]);
  const [isLoading, setIsLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);

  useEffect(() => {
    async function loadTasks() {
      try {
        setIsLoading(true);
        setError(null);

        const data = await getTasks();
        setTasks(data);
      } catch {
        setError("Nao foi possivel carregar tarefas.");
      } finally {
        setIsLoading(false);
      }
    }

    loadTasks();
  }, []);

  return { tasks, isLoading, error };
}
```

## Component

```tsx
import { Task } from "../model/task-types";

type TaskCardProps = {
  task: Task;
};

export function TaskCard({ task }: TaskCardProps) {
  return (
    <article>
      <h2>{task.title}</h2>
      <p>{task.done ? "Concluida" : "Pendente"}</p>
    </article>
  );
}
```

## Page

```tsx
import { useTasks } from "../hooks/use-tasks";
import { TaskCard } from "../components/task-card";

export function TasksPage() {
  const { tasks, isLoading, error } = useTasks();

  if (isLoading) return <p>Carregando...</p>;
  if (error) return <p role="alert">{error}</p>;
  if (tasks.length === 0) return <p>Nenhuma tarefa encontrada.</p>;

  return (
    <main>
      {tasks.map((task) => (
        <TaskCard key={task.id} task={task} />
      ))}
    </main>
  );
}
```

## O que essa arquitetura separa

- `api`: como buscar dados.
- `model`: o que e tarefa e quais regras ela tem.
- `hooks`: estado e ciclo de vida React.
- `components`: UI da feature.
- `pages`: composicao da tela.

## Pegadinhas

- Nao colocar regra de tarefa dentro do card.
- Nao chamar fetch dentro de todo componente.
- Nao colocar componente especifico de tarefa em `shared`.
- Nao criar camada demais se o app for minusculo.

## Relacionado

- [[Conhecimento/Frontend/Engenharia/Arquitetura na Pratica em React|Arquitetura na Pratica em React]]
- [[Conhecimento/Frontend/Engenharia/Clean Architecture|Clean Architecture]]
- [[Conhecimento/Frontend/Engenharia/SOLID|SOLID]]

