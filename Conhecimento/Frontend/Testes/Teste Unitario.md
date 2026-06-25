# Teste Unitario

## O que eu preciso lembrar

Teste unitario testa uma unidade pequena, geralmente uma funcao.

## Exemplo

Funcao:

```ts
export function sum(a: number, b: number) {
  return a + b;
}
```

Teste:

```ts
expect(sum(2, 3)).toBe(5);
```

## Bom para

- formatadores;
- validadores;
- funcoes puras;
- regras pequenas;
- transformacoes de dados.

## Ruim para

- fluxo completo de usuario;
- integracao com API;
- comportamento visual complexo.

## Resumo mental

Teste unitario e lupa: pequeno, rapido e focado.

## Relacionado

- [[O que Testar no Frontend]]

