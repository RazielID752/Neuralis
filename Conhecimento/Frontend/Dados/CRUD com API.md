# CRUD com API

## O que eu preciso lembrar

CRUD e o conjunto basico de operacoes com dados:

- Create: criar;
- Read: ler;
- Update: atualizar;
- Delete: remover.

## Tipo base

```ts
type Task = {
  id: string;
  title: string;
  done: boolean;
};
```

## Read: listar

```ts
async function getTasks(): Promise<Task[]> {
  const response = await fetch("/api/tasks");

  if (!response.ok) {
    throw new Error("Erro ao buscar tarefas");
  }

  return response.json();
}
```

## Create: criar

```ts
type CreateTaskInput = {
  title: string;
};

async function createTask(input: CreateTaskInput): Promise<Task> {
  const response = await fetch("/api/tasks", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(input),
  });

  if (!response.ok) {
    throw new Error("Erro ao criar tarefa");
  }

  return response.json();
}
```

## Update: atualizar

```ts
type UpdateTaskInput = {
  title?: string;
  done?: boolean;
};

async function updateTask(id: string, input: UpdateTaskInput): Promise<Task> {
  const response = await fetch(`/api/tasks/${id}`, {
    method: "PATCH",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(input),
  });

  if (!response.ok) {
    throw new Error("Erro ao atualizar tarefa");
  }

  return response.json();
}
```

## Delete: remover

```ts
async function deleteTask(id: string): Promise<void> {
  const response = await fetch(`/api/tasks/${id}`, {
    method: "DELETE",
  });

  if (!response.ok) {
    throw new Error("Erro ao remover tarefa");
  }
}
```

## Pegadinhas

- `DELETE` pode nao retornar JSON.
- `PATCH` atualiza parte.
- `PUT` costuma substituir o recurso inteiro.
- Depois de criar/editar/remover, a UI precisa atualizar.
- Erro de API precisa aparecer para o usuario.

## Resumo mental

CRUD e o ciclo basico de qualquer recurso: listar, criar, editar e remover.

## Relacionado

- [[Exemplos de Consumo de API]]
- [[HTTP para Frontend]]

