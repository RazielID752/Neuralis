# Composicao em React

## O que eu preciso lembrar

Composicao e montar componentes grandes usando componentes menores.

## Exemplo simples

```tsx
function Card({ children }: { children: React.ReactNode }) {
  return <section className="card">{children}</section>;
}

function Profile() {
  return (
    <Card>
      <h2>Marcos</h2>
      <p>Estudando frontend</p>
    </Card>
  );
}
```

`Card` nao precisa saber o conteudo. Ele so cria a estrutura.

## Por que isso existe

Para evitar componente gigante cheio de regras.

Em vez de um componente tentar controlar tudo, eu separo responsabilidades.

## Props vs children

Props nomeadas:

```tsx
<UserCard name="Ana" />
```

Children:

```tsx
<Card>
  <p>Conteudo livre</p>
</Card>
```

## Pegadinhas

- Criar componente pequeno demais sem necessidade.
- Criar componente grande demais que faz tudo.
- Passar props demais quando children resolveria melhor.

## Resumo mental

Composicao e encaixar pecas. Um componente bom tem responsabilidade clara.

## Relacionado

- [[Componentes]]
- [[Props]]

