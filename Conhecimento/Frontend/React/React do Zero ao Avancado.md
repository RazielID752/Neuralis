# React do Zero ao Avancado

## O que React resolve

React ajuda a construir interfaces que mudam com dados.

Sem React, voce costuma manipular o DOM manualmente:

```js
const button = document.querySelector("button");
button.textContent = "Salvar";
button.disabled = true;
```

Com React, voce descreve como a interface deve parecer para cada estado:

```tsx
function SaveButton({ isSaving }: { isSaving: boolean }) {
  return (
    <button disabled={isSaving}>
      {isSaving ? "Salvando..." : "Salvar"}
    </button>
  );
}
```

React e declarativo: voce descreve o resultado, nao cada passo manual para alterar a tela.

## Pre-requisitos reais

Antes de React fazer sentido, voce precisa conhecer:

- HTML: tags, formularios, acessibilidade basica.
- CSS: layout, responsividade, estados visuais.
- JavaScript: funcoes, objetos, arrays, modules, promises.
- TypeScript: tipos basicos, objetos, unions e generics.

Voce nao precisa dominar tudo antes, mas precisa saber que React nao substitui essas bases. React combina tudo.

## Modelo mental

Uma tela React e uma arvore de componentes.

```tsx
function App() {
  return (
    <main>
      <Header />
      <TaskList />
      <Footer />
    </main>
  );
}
```

Cada componente:

- recebe dados por props;
- pode ter state local;
- retorna JSX;
- pode reagir a eventos;
- pode sincronizar com sistemas externos usando efeitos.

## JSX

Leia tambem: [[JSX]].

JSX parece HTML, mas e sintaxe JavaScript.

```tsx
const name = "Ana";

function Greeting() {
  return <h1>Ola, {name}</h1>;
}
```

Dentro de `{}` voce escreve expressoes JavaScript:

```tsx
<p>{user.name.toUpperCase()}</p>
<p>{price * quantity}</p>
<p>{isAdmin ? "Admin" : "Usuario"}</p>
```

JSX deve retornar um elemento raiz:

```tsx
return (
  <>
    <h1>Titulo</h1>
    <p>Texto</p>
  </>
);
```

## Componentes

Componente e uma funcao que retorna UI.

```tsx
function Badge() {
  return <span>Novo</span>;
}
```

Com props:

```tsx
type BadgeProps = {
  label: string;
};

function Badge({ label }: BadgeProps) {
  return <span>{label}</span>;
}
```

Um bom componente tem uma responsabilidade clara.

## Props

Props sao parametros do componente.

```tsx
type ProductCardProps = {
  name: string;
  price: number;
};

function ProductCard({ name, price }: ProductCardProps) {
  return (
    <article>
      <h2>{name}</h2>
      <p>R$ {price}</p>
    </article>
  );
}
```

Use props para deixar componentes reutilizaveis.

## State

State e memoria interna do componente.

Veja [[State]] para a explicacao completa.

Exemplo curto:

```tsx
const [isOpen, setIsOpen] = useState(false);
```

Use state quando uma mudanca precisa sobreviver entre renderizacoes e aparecer na UI.

## Eventos

Leia tambem: [[Eventos em React]].

Eventos conectam acao do usuario a mudanca de estado.

```tsx
function LikeButton() {
  const [liked, setLiked] = useState(false);

  return (
    <button onClick={() => setLiked((liked) => !liked)}>
      {liked ? "Curtido" : "Curtir"}
    </button>
  );
}
```

Eventos comuns:

- `onClick`
- `onChange`
- `onSubmit`
- `onBlur`
- `onFocus`

## Renderizacao condicional

Leia tambem: [[Renderizacao Condicional]].

Mostrar algo dependendo de uma condicao:

```tsx
{isLoggedIn ? <Dashboard /> : <LoginForm />}
```

Mostrar apenas quando verdadeiro:

```tsx
{error && <p role="alert">{error}</p>}
```

## Listas e keys

Leia tambem: [[Listas e Keys]].

Para renderizar listas, use `map`.

```tsx
const users = [
  { id: "1", name: "Ana" },
  { id: "2", name: "Bruno" },
];

function UserList() {
  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

`key` ajuda React a identificar cada item. Prefira IDs estaveis. Evite indice do array quando a lista pode mudar.

## Forms

Leia tambem: [[Forms em React]].

Forms em React normalmente usam inputs controlados:

```tsx
function EmailForm() {
  const [email, setEmail] = useState("");

  function submit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault();
    console.log(email);
  }

  return (
    <form onSubmit={submit}>
      <input
        value={email}
        onChange={(event) => setEmail(event.target.value)}
      />
      <button type="submit">Enviar</button>
    </form>
  );
}
```

## Effects

`useEffect` serve para sincronizar o componente com algo fora do React:

- document title;
- subscriptions;
- timers;
- APIs externas;
- eventos globais.

```tsx
useEffect(() => {
  document.title = title;
}, [title]);
```

Nao use `useEffect` para calcular dados que poderiam ser calculados durante renderizacao.

## Composicao

Leia tambem: [[Composicao em React]].

Composicao e montar componentes pequenos para criar componentes maiores.

```tsx
function Card({ children }: { children: React.ReactNode }) {
  return <section className="card">{children}</section>;
}

function Profile() {
  return (
    <Card>
      <h2>Ana</h2>
      <p>Frontend developer</p>
    </Card>
  );
}
```

Composicao evita componentes gigantes e aumenta reutilizacao.

## TypeScript com React

Tipagem basica de props:

```tsx
type ButtonProps = {
  children: React.ReactNode;
  onClick: () => void;
  disabled?: boolean;
};

function Button({ children, onClick, disabled = false }: ButtonProps) {
  return (
    <button onClick={onClick} disabled={disabled}>
      {children}
    </button>
  );
}
```

Tipos comuns:

- `React.ReactNode`: qualquer conteudo renderizavel.
- `React.FormEvent<HTMLFormElement>`: submit de form.
- `React.ChangeEvent<HTMLInputElement>`: mudanca em input.
- `ComponentProps<"button">`: props nativas de botao.

## Padroes intermediarios

- Separar componentes por responsabilidade.
- Extrair hooks customizados quando uma logica se repete.
- Evitar prop drilling excessivo.
- Usar context para dependencias globais simples.
- Manter estado perto de onde e usado.

## Padroes avancados

- Server state separado de client state.
- Suspense e streaming quando o framework suporta.
- Memoizacao com criterio, nao por reflexo.
- Componentes compostos.
- Reducers para fluxos complexos.
- Error boundaries.
- Testes de comportamento.

## Ordem de estudo

1. JSX.
2. Componentes.
3. Props.
4. State.
5. Eventos.
6. Renderizacao condicional.
7. Listas.
8. Forms.
9. Effects.
10. Composicao.
11. Hooks customizados.
12. Context.
13. Performance.
14. Testes.
15. Arquitetura.

## Criterio de dominio

Voce esta ficando bom em React quando consegue responder:

- Qual componente deveria ter este state?
- Esse dado e client state ou server state?
- Essa logica pertence ao componente, a um hook ou a uma funcao comum?
- Este `useEffect` e realmente necessario?
- Este componente esta facil de usar sem saber sua implementacao interna?
