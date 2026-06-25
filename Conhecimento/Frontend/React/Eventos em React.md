# Eventos em React

## O que eu preciso lembrar

Eventos sao a forma da interface reagir ao usuario.

Clique, digitar, enviar formulario: tudo isso vira evento.

## Click

```tsx
function Button() {
  function handleClick() {
    console.log("clicou");
  }

  return <button onClick={handleClick}>Clique</button>;
}
```

## Evento mudando state

```tsx
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount((count) => count + 1)}>
      {count}
    </button>
  );
}
```

## Input

```tsx
function Search() {
  const [search, setSearch] = useState("");

  return (
    <input
      value={search}
      onChange={(event) => setSearch(event.target.value)}
    />
  );
}
```

## Com TypeScript

```tsx
function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
  console.log(event.target.value);
}
```

## Pegadinhas

- Nao chamar a funcao direto sem querer: `onClick={handleClick()}` executa na renderizacao.
- Para passar parametro, use arrow: `onClick={() => remove(id)}`.
- Form precisa de `event.preventDefault()` se nao quiser recarregar.

## Resumo mental

Evento e o ponto onde o usuario mexe na tela e meu codigo responde.

## Relacionado

- [[State]]
- [[Forms em React]]

