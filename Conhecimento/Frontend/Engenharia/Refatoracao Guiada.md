# Refatoracao Guiada

## O que eu preciso lembrar

Refatorar e melhorar estrutura sem mudar comportamento.

## Passo a passo seguro

1. Entender comportamento atual.
2. Se possivel, criar teste ou exemplo manual.
3. Escolher um problema pequeno.
4. Fazer uma mudanca.
5. Verificar se continua funcionando.
6. Repetir.

## Tecnicas comuns

### Extrair funcao

Antes:

```ts
const label = `${user.name} <${user.email}>`;
```

Depois:

```ts
function formatUserLabel(user: User) {
  return `${user.name} <${user.email}>`;
}
```

### Extrair componente

Antes:

```tsx
<article>
  <h2>{task.title}</h2>
  <p>{task.done ? "Concluida" : "Pendente"}</p>
</article>
```

Depois:

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

### Substituir booleanos por status

Antes:

```ts
isLoading;
isError;
isSuccess;
```

Depois:

```ts
type Status = "loading" | "error" | "success";
```

## Ordem boa para refatorar componente grande

1. Extrair funções puras.
2. Extrair componentes visuais.
3. Extrair hook se tiver lógica React reutilizável.
4. Separar API.
5. Melhorar tipos.

## Pegadinhas

- Refatorar tudo de uma vez.
- Mudar comportamento sem perceber.
- Criar abstração antes de remover duplicação real.

## Resumo mental

Refatoração boa é pequena, verificável e guiada por um problema claro.

## Relacionado

- [[Code Smells no Frontend]]
- [[Clean Code]]
- [[Refatorando Funcao Grande]]

