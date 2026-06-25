# Props

## O que eu preciso lembrar

Props sao dados que um componente recebe de fora.

Se componente fosse uma funcao, props seriam os parametros.

## Exemplo simples

```tsx
type UserCardProps = {
  name: string;
};

function UserCard({ name }: UserCardProps) {
  return <p>{name}</p>;
}
```

Uso:

```tsx
<UserCard name="Marcos" />
```

## Por que props existem

Para o componente ser reutilizavel.

Sem props, o componente fica preso a um valor:

```tsx
function UserCard() {
  return <p>Marcos</p>;
}
```

Com props, muda por fora:

```tsx
<UserCard name="Ana" />
<UserCard name="Marcos" />
```

## Props opcionais

```tsx
type BadgeProps = {
  label: string;
  color?: "blue" | "green";
};
```

Valor padrao:

```tsx
function Badge({ label, color = "blue" }: BadgeProps) {
  return <span data-color={color}>{label}</span>;
}
```

## Children

`children` e conteudo dentro do componente.

```tsx
type CardProps = {
  children: React.ReactNode;
};

function Card({ children }: CardProps) {
  return <section>{children}</section>;
}
```

Uso:

```tsx
<Card>
  <h2>Titulo</h2>
  <p>Texto</p>
</Card>
```

## Pegadinhas

- Passar props demais.
- Componente filho tentar alterar props diretamente.
- Esquecer de tipar `children`.
- Misturar props de configuracao com state interno.

## Resumo mental

Props entram. Componente renderiza. Props nao pertencem ao componente, elas vêm do pai.

## Relacionado

- [[Componentes]]
- [[State]]
- [[Conhecimento/Frontend/TypeScript/TypeScript com React|TypeScript com React]]
