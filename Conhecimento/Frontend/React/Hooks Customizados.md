# Hooks Customizados

## O que eu preciso lembrar

Hook customizado extrai lógica de React reutilizável.

## Exemplo

```tsx
function useToggle(initialValue = false) {
  const [value, setValue] = useState(initialValue);

  function toggle() {
    setValue((value) => !value);
  }

  return { value, toggle };
}
```

Uso:

```tsx
const { value: isOpen, toggle } = useToggle();
```

## Quando criar

- a lógica usa hooks;
- a lógica se repete;
- o componente ficou dificil de ler;
- o nome do hook explica a intenção.

## Quando nao criar

- lógica usada uma vez;
- função comum resolveria;
- o hook esconde coisa demais.

## Pegadinhas

- Hook customizado nao compartilha estado sozinho entre componentes.
- Precisa começar com `use`.
- Ainda precisa seguir regras dos hooks.

## Resumo mental

Hook customizado e uma função que organiza lógica de React.

## Relacionado

- [[Hooks]]
- [[Como Criar Funcoes Pequenas]]

