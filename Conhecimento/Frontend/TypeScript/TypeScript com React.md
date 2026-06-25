# TypeScript com React

## O que eu preciso lembrar

TypeScript em React serve principalmente para tipar props, eventos, state e dados.

O objetivo nao e escrever tipo bonito. E evitar passar coisa errada para componente.

## Props

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

O que isso diz:

- `children` pode ser qualquer coisa renderizavel;
- `onClick` e uma funcao sem retorno util;
- `disabled` e opcional.

## State simples

```tsx
const [count, setCount] = useState(0);
```

TypeScript infere `number`.

```tsx
const [name, setName] = useState("");
```

TypeScript infere `string`.

## State com array

Array vazio precisa de ajuda.

```tsx
type Task = {
  id: string;
  title: string;
  done: boolean;
};

const [tasks, setTasks] = useState<Task[]>([]);
```

## Evento de input

```tsx
function SearchInput() {
  function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
    console.log(event.target.value);
  }

  return <input onChange={handleChange} />;
}
```

## Evento de form

```tsx
function Form() {
  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault();
  }

  return <form onSubmit={handleSubmit} />;
}
```

## Props nativas de elemento

Quando quero criar um componente que aceita props de um botao HTML:

```tsx
type ButtonProps = React.ComponentProps<"button">;

function Button(props: ButtonProps) {
  return <button {...props} />;
}
```

Com customizacao:

```tsx
type ButtonProps = React.ComponentProps<"button"> & {
  variant?: "primary" | "secondary";
};
```

## Pegadinhas

- Nao precisa usar `React.FC` sempre.
- `children` precisa ser tipado se o componente recebe conteudo.
- Array vazio em state geralmente precisa de tipo.
- Evento depende do elemento: input, form, button etc.
- Nao use `any` em props so para parar erro.

## Resumo mental

Em React, TypeScript e contrato entre componentes. Props dizem o que entra. State diz o que o componente guarda. Eventos dizem de onde veio a acao.

## Exercicios para fixar

1. Crie um componente `Card` com `title` e `children`.
2. Crie um `Button` com `variant`.
3. Crie um state `Task[]`.
4. Tipe um `onChange` de input.
5. Tipe um `onSubmit` de form.

## Relacionado

- [[Conhecimento/Frontend/React/Props|Props]]
- [[Conhecimento/Frontend/React/State|State]]
- [[Union Types e Literal Types]]

