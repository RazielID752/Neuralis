# Forms em React

## O que eu preciso lembrar

Formulario em React geralmente usa state para controlar o valor dos inputs.

## Input controlado

```tsx
function NameForm() {
  const [name, setName] = useState("");

  return (
    <input
      value={name}
      onChange={(event) => setName(event.target.value)}
    />
  );
}
```

O valor vem do state. A mudanca atualiza o state.

## Submit

```tsx
function Form() {
  const [email, setEmail] = useState("");

  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault();
    console.log(email);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={email}
        onChange={(event) => setEmail(event.target.value)}
      />
      <button type="submit">Enviar</button>
    </form>
  );
}
```

## Multiplos campos

```tsx
type FormData = {
  name: string;
  email: string;
};

const [form, setForm] = useState<FormData>({
  name: "",
  email: "",
});
```

Atualizando um campo:

```tsx
setForm((form) => ({
  ...form,
  name: event.target.value,
}));
```

## Pegadinhas

- Esquecer `event.preventDefault()`.
- Input com `value` mas sem `onChange`.
- Guardar state duplicado desnecessario.
- Nao associar label ao input.

## Resumo mental

Formulario e state + eventos + submit.

## Relacionado

- [[State]]
- [[Eventos em React]]
- [[Conhecimento/Frontend/HTML/Formularios|Formularios]]

