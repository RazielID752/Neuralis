# Hooks

## O que eu preciso lembrar

Hooks sao funcoes especiais do React para usar recursos como state, effects, refs e memoizacao.

Todo hook começa com `use`.

## Hooks comuns

- `useState`: memoria local do componente.
- `useEffect`: sincronizar com algo fora do React.
- `useRef`: guardar referencia que nao causa renderizacao.
- `useMemo`: memorizar valor calculado.
- `useCallback`: memorizar funcao.

## Regras dos hooks

Hooks devem ser chamados:

- no topo do componente;
- nunca dentro de `if`;
- nunca dentro de loop;
- nunca dentro de funcao comum aninhada.

Correto:

```tsx
function Counter() {
  const [count, setCount] = useState(0);
  return <button>{count}</button>;
}
```

Errado:

```tsx
if (open) {
  const [count, setCount] = useState(0);
}
```

## Hook customizado

Hook customizado extrai logica reutilizavel.

```tsx
function useToggle(initialValue = false) {
  const [value, setValue] = useState(initialValue);

  function toggle() {
    setValue((value) => !value);
  }

  return { value, toggle };
}
```

## Pegadinhas

- Usar `useEffect` sem precisar.
- Usar `useMemo` cedo demais.
- Quebrar regra dos hooks.
- Criar hook customizado para logica que so e usada uma vez.

## Resumo mental

Hook e uma forma de conectar componente a recursos do React. Nao e para enfeitar codigo.

## Relacionado

- [[State]]
- [[useEffect]]

