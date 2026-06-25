# Componentizacao com Tailwind

## O que eu preciso lembrar

Se as classes se repetem muito, provavelmente deve virar componente.

## Exemplo em React

```tsx
type ButtonProps = {
  children: React.ReactNode;
};

function Button({ children }: ButtonProps) {
  return (
    <button className="rounded bg-black px-4 py-2 text-sm font-medium text-white hover:bg-neutral-800 focus-visible:outline focus-visible:outline-2">
      {children}
    </button>
  );
}
```

## Variante

```tsx
type ButtonProps = {
  children: React.ReactNode;
  variant?: "primary" | "secondary";
};

function Button({ children, variant = "primary" }: ButtonProps) {
  const className =
    variant === "primary"
      ? "bg-black text-white hover:bg-neutral-800"
      : "bg-white text-black border border-neutral-300 hover:bg-neutral-50";

  return <button className={`rounded px-4 py-2 ${className}`}>{children}</button>;
}
```

## Pegadinhas

- Repetir a mesma lista enorme de classes em varios lugares.
- Criar componente antes de saber o padrao.
- Misturar regra de negocio com componente visual.

## Resumo mental

Tailwind fica organizado quando repeticao vira componente.

## Relacionado

- [[Conhecimento/Frontend/React/Componentes|Componentes]]
- [[Tema e Configuracao do Tailwind]]

