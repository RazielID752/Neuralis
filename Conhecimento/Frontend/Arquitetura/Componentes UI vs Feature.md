# Componentes UI vs Feature

## O que eu preciso lembrar

Componente de UI e generico. Componente de feature conhece uma parte especifica do produto.

## Componente UI

Exemplo:

```tsx
function Button({ children }: { children: React.ReactNode }) {
  return <button>{children}</button>;
}
```

Ele nao sabe se esta em login, dashboard ou checkout.

## Componente de feature

```tsx
function TaskCard({ task }: { task: Task }) {
  return (
    <article>
      <h2>{task.title}</h2>
      <p>{task.done ? "Concluida" : "Pendente"}</p>
    </article>
  );
}
```

Ele conhece o dominio de tarefas.

## Onde colocar

UI generico:

```txt
shared/components/Button.tsx
```

Feature:

```txt
features/tasks/components/TaskCard.tsx
```

## Pegadinhas

- Colocar `TaskCard` em shared.
- Fazer `Button` saber regra de negocio.
- Criar componente generico antes de ter mais de um uso.

## Resumo mental

UI generico nao conhece negocio. Feature conhece o contexto.

## Relacionado

- [[Composicao e Reutilizacao]]
- [[Organizacao de Pastas]]

