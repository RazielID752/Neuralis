# Mocks e Fixtures

## O que eu preciso lembrar

Mock simula uma dependencia. Fixture e dado falso reutilizavel.

## Mock

Exemplo mental:

```ts
const getUsersMock = () => [
  { id: "1", name: "Ana" },
];
```

## Fixture

```ts
export const userFixture = {
  id: "1",
  name: "Ana",
};
```

## Quando usar mock

- API externa;
- funcao cara;
- dependencia instavel;
- erro controlado.

## Pegadinhas

- Mockar tudo.
- Criar dado falso diferente da realidade.
- Fixture gigante impossivel de ler.

## Resumo mental

Mock ajuda a controlar o teste, mas mock demais pode esconder problema real.

## Relacionado

- [[Teste de Integracao]]

