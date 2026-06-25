# Tarefas CRUD

## Objetivo

Praticar CRUD com funcoes pequenas.

## Recurso

```ts
type Task = {
  id: string;
  title: string;
  done: boolean;
};
```

## Funcoes de API

```ts
async function getTasks(): Promise<Task[]> {}
async function createTask(title: string): Promise<Task> {}
async function toggleTask(task: Task): Promise<Task> {}
async function deleteTask(id: string): Promise<void> {}
```

## Funcoes de logica

```ts
function getPendingTasks(tasks: Task[]) {
  return tasks.filter((task) => !task.done);
}

function getDoneTasks(tasks: Task[]) {
  return tasks.filter((task) => task.done);
}

function sortTasksByTitle(tasks: Task[]) {
  return [...tasks].sort((a, b) => a.title.localeCompare(b.title));
}
```

## Regra do exercicio

Nao colocar toda logica dentro do componente.

Separar:

- API;
- transformacao;
- filtro;
- renderizacao.

## Relacionado

- [[Conhecimento/Frontend/Dados/CRUD com API|CRUD com API]]
- [[Conhecimento/Frontend/Logica/Refatorando Funcao Grande|Refatorando Funcao Grande]]

