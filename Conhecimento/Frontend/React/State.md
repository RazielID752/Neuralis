# State

## Ideia central

State e a memoria interna de um componente React.

Quando alguma informacao muda e essa mudanca precisa aparecer na tela, essa informacao provavelmente deve estar em state.

Pense assim:

- `props` sao dados que o componente recebe de fora.
- `state` sao dados que o componente controla por dentro.
- a tela e resultado de `props + state`.

React nao atualiza a tela porque voce mudou uma variavel comum. React atualiza a tela quando voce muda state usando uma funcao de atualizacao, como `setCount`.

## Antes de React: o problema

Imagine um contador em JavaScript puro:

```js
let count = 0;

function increment() {
  count = count + 1;
  document.querySelector("#counter").textContent = count;
}
```

Aqui voce precisa fazer duas coisas manualmente:

1. mudar o dado;
2. atualizar a tela.

Em React, a ideia e diferente. Voce muda o state, e React recalcula a interface.

```tsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      {count}
    </button>
  );
}
```

Voce nao escreve "atualize o texto do botao". Voce descreve que o botao mostra `{count}`. Quando `count` muda, React renderiza de novo.

## O que é `useState`

`useState` e um Hook do React que cria uma informacao mutavel para o componente.

```tsx
const [value, setValue] = useState(initialValue);
```

- `value`: valor atual do state.
- `setValue`: funcao usada para pedir uma atualizacao.
- `initialValue`: valor usado na primeira renderizacao.

Exemplo:

```tsx
const [name, setName] = useState("");
const [age, setAge] = useState(18);
const [isOpen, setIsOpen] = useState(false);
```

## State causa renderização

Quando voce chama `setState`, React agenda uma nova renderização do componente.

```tsx
setCount(count + 1);
```

Fluxo mental:

1. usuario clica;
2. evento chama `setCount`;
3. React guarda o novo valor;
4. React executa o componente de novo;
5. JSX novo e comparado com a tela atual;
6. React atualiza o que mudou.

## Variavel comum vs state

Este codigo nao funciona como esperado:

```tsx
function Counter() {
  let count = 0;

  function increment() {
    count += 1;
  }

  return <button onClick={increment}>{count}</button>;
}
```

Problemas:

- mudar `count` nao avisa o React;
- o componente nao renderiza de novo;
- em cada renderizacao, `count` volta para `0`.

Use state quando o valor precisa sobreviver entre renderizacoes e aparecer na UI.

## Atualizacao baseada no valor anterior

Quando o novo valor depende do valor anterior, prefira a forma funcional:

```tsx
setCount((currentCount) => currentCount + 1);
```

Isso evita bugs quando varias atualizacoes acontecem perto uma da outra.

Exemplo ruim:

```tsx
setCount(count + 1);
setCount(count + 1);
setCount(count + 1);
```

Esse codigo pode nao somar 3, porque todas as linhas podem estar lendo o mesmo `count` antigo.

Exemplo melhor:

```tsx
setCount((count) => count + 1);
setCount((count) => count + 1);
setCount((count) => count + 1);
```

## State com string

Formulario simples:

```tsx
import { useState } from "react";

function NameForm() {
  const [name, setName] = useState("");

  return (
    <form>
      <label htmlFor="name">Nome</label>
      <input
        id="name"
        value={name}
        onChange={(event) => setName(event.target.value)}
      />

      <p>Ola, {name || "visitante"}.</p>
    </form>
  );
}
```

Aqui o input e controlado pelo React:

- o valor vem de `name`;
- a mudanca chama `setName`;
- a tela mostra o novo valor.

## State com boolean

Use boolean para estados ligados/desligados:

```tsx
function Disclosure() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <section>
      <button onClick={() => setIsOpen((open) => !open)}>
        {isOpen ? "Fechar" : "Abrir"}
      </button>

      {isOpen && <p>Conteudo escondido.</p>}
    </section>
  );
}
```

Boolean e bom para:

- modal aberto ou fechado;
- menu aberto ou fechado;
- checkbox marcado ou desmarcado;
- loading ativo ou inativo.

## State com array

Arrays em state devem ser tratados como imutaveis. Nao use `push` diretamente no array existente.

Errado:

```tsx
items.push(newItem);
setItems(items);
```

Correto:

```tsx
setItems((items) => [...items, newItem]);
```

Exemplo completo:

```tsx
type Task = {
  id: string;
  title: string;
  done: boolean;
};

function TaskList() {
  const [tasks, setTasks] = useState<Task[]>([]);

  function addTask(title: string) {
    const task = {
      id: crypto.randomUUID(),
      title,
      done: false,
    };

    setTasks((tasks) => [...tasks, task]);
  }

  function removeTask(id: string) {
    setTasks((tasks) => tasks.filter((task) => task.id !== id));
  }

  function toggleTask(id: string) {
    setTasks((tasks) =>
      tasks.map((task) =>
        task.id === id ? { ...task, done: !task.done } : task
      )
    );
  }

  return (
    <ul>
      {tasks.map((task) => (
        <li key={task.id}>
          <button onClick={() => toggleTask(task.id)}>
            {task.done ? "Concluida" : "Pendente"}
          </button>
          {task.title}
          <button onClick={() => removeTask(task.id)}>Remover</button>
        </li>
      ))}
    </ul>
  );
}
```

## State com objeto

Objetos tambem devem ser atualizados sem mutacao direta.

Errado:

```tsx
user.name = "Ana";
setUser(user);
```

Correto:

```tsx
setUser((user) => ({
  ...user,
  name: "Ana",
}));
```

Exemplo:

```tsx
type Profile = {
  name: string;
  email: string;
};

function ProfileForm() {
  const [profile, setProfile] = useState<Profile>({
    name: "",
    email: "",
  });

  return (
    <form>
      <input
        value={profile.name}
        onChange={(event) =>
          setProfile((profile) => ({
            ...profile,
            name: event.target.value,
          }))
        }
      />

      <input
        value={profile.email}
        onChange={(event) =>
          setProfile((profile) => ({
            ...profile,
            email: event.target.value,
          }))
        }
      />
    </form>
  );
}
```

## State derivado

State derivado e um valor que pode ser calculado a partir de outro state ou props.

Evite isto:

```tsx
const [firstName, setFirstName] = useState("");
const [lastName, setLastName] = useState("");
const [fullName, setFullName] = useState("");
```

`fullName` nao precisa ser state, porque pode ser calculado:

```tsx
const fullName = `${firstName} ${lastName}`.trim();
```

Regra pratica:

Se voce consegue calcular durante a renderizacao, provavelmente nao precisa guardar em state.

## Onde colocar state

Coloque o state no componente mais baixo possivel, mas alto o suficiente para todos que precisam dele.

Exemplo:

- se apenas um botao precisa saber se esta aberto, state fica no botao ou no componente pai direto;
- se dois componentes irmaos precisam do mesmo valor, state sobe para o pai comum;
- se muitas paginas precisam do mesmo dado, talvez seja contexto, URL, cache de servidor ou store externa.

## Client state vs server state

Nem todo dado em React deve ser `useState`.

Client state:

- modal aberto;
- texto digitado no input;
- aba selecionada;
- filtro local;
- tema claro/escuro.

Server state:

- usuario vindo da API;
- lista de produtos;
- pedidos;
- permissoes;
- dados que podem mudar fora da tela.

Para server state, normalmente ferramentas como TanStack Query, SWR ou data fetching do framework fazem mais sentido do que `useState` puro.

## Loading, erro e sucesso

Um padrao comum e representar estados de uma operacao:

```tsx
type Status = "idle" | "loading" | "success" | "error";

function SaveButton() {
  const [status, setStatus] = useState<Status>("idle");

  async function save() {
    try {
      setStatus("loading");
      await fakeSave();
      setStatus("success");
    } catch {
      setStatus("error");
    }
  }

  return (
    <button onClick={save} disabled={status === "loading"}>
      {status === "loading" ? "Salvando..." : "Salvar"}
    </button>
  );
}
```

Isso e melhor do que varios booleans soltos:

```tsx
const [isLoading, setIsLoading] = useState(false);
const [isSuccess, setIsSuccess] = useState(false);
const [isError, setIsError] = useState(false);
```

Quando os estados sao mutuamente exclusivos, uma union costuma ser mais clara.

## Erros comuns

### 1. Criar state demais

Nem tudo precisa virar state.

Se o valor pode ser calculado a partir de props ou outro state, calcule.

### 2. Mutar array ou objeto

React depende de novas referencias para perceber mudancas com consistencia.

Use:

- spread: `{ ...obj }`, `[...array]`;
- `map`;
- `filter`;
- `slice`;
- bibliotecas como Immer em casos complexos.

### 3. Esperar que `setState` mude o valor imediatamente

Este log pode mostrar o valor antigo:

```tsx
setCount(count + 1);
console.log(count);
```

`setState` agenda a proxima renderizacao. O valor atualizado aparece na proxima execucao do componente.

### 4. Colocar state alto demais

State alto demais faz componentes renderizarem sem necessidade e espalha responsabilidade.

### 5. Colocar state baixo demais

State baixo demais impede outros componentes de acessarem o dado sem gambiarras.

## Como saber se algo deve ser state

Pergunte:

1. Esse valor muda com o tempo?
2. Essa mudanca precisa aparecer na tela?
3. O valor nao pode ser calculado a partir de outro valor?
4. O valor pertence a interacao local da interface?

Se as respostas forem sim, provavelmente e state.

## Nivel avancado

Em componentes grandes, muitos `useState` podem virar ruido. Nesses casos, considere:

- `useReducer` quando transicoes de estado sao complexas;
- context quando varios componentes precisam do mesmo estado;
- estado na URL quando precisa ser compartilhavel;
- bibliotecas de server state para dados remotos;
- stores externas apenas quando ha necessidade real.

Exemplo de quando `useReducer` pode ser melhor:

```tsx
type State = {
  count: number;
};

type Action =
  | { type: "increment" }
  | { type: "decrement" }
  | { type: "reset" };

function reducer(state: State, action: Action): State {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    case "reset":
      return { count: 0 };
  }
}
```

## Resumo mental

State e a memoria da UI.

Use state para dados que mudam, sobrevivem entre renderizacoes e alteram o que o usuario ve. Evite guardar o que pode ser calculado. Atualize objetos e arrays sem mutacao direta. Coloque o state no menor lugar que ainda atende todos os componentes que precisam dele.

## Relacionado

- [[React]]
- [[Hooks]]
- [[useEffect]]
- [[Props]]
- [[Conhecimento/Frontend/TypeScript/Tipos Basicos|Tipos Basicos]]

