# Componentes

## O que eu preciso lembrar

Componente e uma parte reutilizavel da interface.

Em React, componente normalmente e uma funcao que retorna JSX.

## Exemplo simples

```tsx
function Button() {
  return <button>Salvar</button>;
}
```

## Com props

```tsx
type ButtonProps = {
  children: React.ReactNode;
};

function Button({ children }: ButtonProps) {
  return <button>{children}</button>;
}
```

## Por que componentes existem

Para quebrar a tela em partes menores.

Exemplo:

```tsx
function App() {
  return (
    <main>
      <Header />
      <TaskList />
      <Footer />
    </main>
  );
}
```

## Componente bom

Um componente bom:

- tem responsabilidade clara;
- recebe dados por props;
- nao faz coisas demais;
- tem nome que explica o que ele representa;
- pode ser entendido isoladamente.

## Pegadinhas

- Criar componente gigante.
- Criar componente pequeno demais sem necessidade.
- Misturar regra de negocio com visual simples.
- Nomear componente de forma vaga, tipo `Box2`.

## Resumo mental

Componente e uma peca da tela. Peca boa tem nome claro e responsabilidade clara.

## Relacionado

- [[JSX]]
- [[Props]]
- [[Composicao em React]]

