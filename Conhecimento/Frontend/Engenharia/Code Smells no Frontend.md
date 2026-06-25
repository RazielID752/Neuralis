# Code Smells no Frontend

## O que eu preciso lembrar

Code smell e cheiro de problema. Nao significa bug imediato, mas indica que algo pode piorar.

## Componente gigante

Sinais:

- muitas responsabilidades;
- muitos states;
- muitos effects;
- JSX enorme;
- varias regras no mesmo arquivo.

Possivel solucao:

- extrair componentes;
- extrair hooks;
- extrair funcoes puras;
- separar API.

## Props demais

```tsx
<UserCard
  name={name}
  email={email}
  avatar={avatar}
  permissions={permissions}
  settings={settings}
  onEdit={onEdit}
  onDelete={onDelete}
/>
```

Talvez o componente esteja fazendo coisa demais.

## useEffect demais

Se quase tudo vira `useEffect`, talvez esteja faltando entender:

- state derivado;
- eventos;
- data fetching;
- composição.

## Utils gigante

Arquivo `utils.ts` com tudo dentro vira gaveta bagunçada.

Melhor separar por contexto:

```txt
format-currency.ts
filter-users.ts
date-utils.ts
```

## Booleanos demais

```ts
const [isLoading, setIsLoading] = useState(false);
const [isError, setIsError] = useState(false);
const [isSuccess, setIsSuccess] = useState(false);
```

Pode virar union:

```ts
type Status = "idle" | "loading" | "error" | "success";
```

## Pegadinhas

- Refatorar smell sem entender o problema.
- Criar abstração só porque "parece feio".
- Confundir codigo simples com codigo ruim.

## Resumo mental

Code smell e convite para investigar, nao ordem automatica para refatorar.

## Relacionado

- [[Refatoracao Guiada]]
- [[Clean Code]]
- [[Discriminated Unions]]

