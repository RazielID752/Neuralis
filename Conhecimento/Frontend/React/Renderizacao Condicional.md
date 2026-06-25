# Renderizacao Condicional

## O que eu preciso lembrar

Renderizacao condicional e mostrar uma UI ou outra dependendo de uma condicao.

## Ternario

```tsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

Uso quando tenho duas possibilidades.

## E logico `&&`

```tsx
{error && <p role="alert">{error}</p>}
```

Uso quando quero mostrar algo apenas se existir.

## Retorno antecipado

```tsx
function Profile({ user }: { user: User | null }) {
  if (!user) {
    return <p>Carregando...</p>;
  }

  return <h1>{user.name}</h1>;
}
```

## Estados comuns

```tsx
if (status === "loading") return <p>Carregando...</p>;
if (status === "error") return <p>Erro ao carregar.</p>;
if (status === "empty") return <p>Nenhum item encontrado.</p>;

return <List items={items} />;
```

## Pegadinhas

- Condicional muito grande dentro do JSX fica dificil de ler.
- `0 && <p>` pode renderizar `0`.
- Esconder erro sem mostrar feedback deixa UI confusa.

## Resumo mental

UI quase sempre depende de estado: carregando, erro, vazio, sucesso.

## Relacionado

- [[State]]
- [[JSX]]

