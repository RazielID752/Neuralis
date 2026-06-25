# Context API

## O que eu preciso lembrar

Context serve para compartilhar valor com varios componentes sem passar props manualmente por todos os niveis.

## Quando faz sentido

- tema;
- usuario autenticado;
- idioma;
- configuracao global;
- dependencias compartilhadas.

## Exemplo simples

```tsx
const ThemeContext = createContext<"light" | "dark">("light");
```

Provider:

```tsx
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Page />
    </ThemeContext.Provider>
  );
}
```

Uso:

```tsx
function Button() {
  const theme = useContext(ThemeContext);
  return <button>{theme}</button>;
}
```

## Quando nao usar

- para qualquer state local;
- para server state complexo;
- para evitar pensar em composição;
- para dados que poucos componentes usam.

## Pegadinhas

- Context pode causar renders em muitos filhos.
- Context grande demais vira estado global bagunçado.
- Nem todo prop drilling e problema.

## Resumo mental

Context e para dado realmente compartilhado, nao para todo state.

## Relacionado

- [[State]]
- [[Composicao em React]]

