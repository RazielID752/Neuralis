# JSX

## O que eu preciso lembrar

JSX parece HTML, mas e JavaScript escrevendo interface.

## Explicando do zero

Em React, componente retorna JSX:

```tsx
function Title() {
  return <h1>Ola</h1>;
}
```

Dentro de `{}` eu posso usar expressao JavaScript:

```tsx
const name = "Marcos";

function Greeting() {
  return <h1>Ola, {name}</h1>;
}
```

## Regras importantes

### Precisa fechar tags

```tsx
<img src="/avatar.png" alt="Avatar" />
```

### Usa `className`, nao `class`

```tsx
<div className="card">Conteudo</div>
```

### Retorna um elemento raiz

```tsx
return (
  <>
    <h1>Titulo</h1>
    <p>Texto</p>
  </>
);
```

## Condicional em JSX

```tsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

```tsx
{error && <p>{error}</p>}
```

## Pegadinhas

- JSX nao aceita `if` direto dentro do retorno.
- `class` vira `className`.
- `for` em label vira `htmlFor`.
- Precisa fechar tag.

## Resumo mental

JSX e JavaScript com cara de HTML. Dentro de `{}` entra expressao, nao bloco solto de codigo.

## Exercicios para fixar

1. Crie um componente que renderiza um nome.
2. Use uma variavel dentro de `{}`.
3. Renderize algo com ternario.
4. Renderize algo com `&&`.

## Relacionado

- [[Componentes]]
- [[Renderizacao Condicional]]

