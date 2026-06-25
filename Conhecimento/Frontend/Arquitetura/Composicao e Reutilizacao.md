# Composicao e Reutilizacao

## O que eu preciso lembrar

Reutilizacao boa nasce de repeticao real, nao de adivinhacao.

## Composicao

```tsx
function Card({ children }: { children: React.ReactNode }) {
  return <section className="card">{children}</section>;
}
```

Uso:

```tsx
<Card>
  <h2>Titulo</h2>
  <p>Conteudo</p>
</Card>
```

## Quando extrair componente

Extraio quando:

- repeti o mesmo bloco;
- o JSX ficou grande;
- existe uma responsabilidade clara;
- o nome do componente melhora a leitura.

## Quando nao extrair

Nao extraio quando:

- so usei uma vez;
- o componente fica mais dificil que o JSX original;
- estou tentando prever futuro.

## Pegadinhas

- Criar abstracao cedo demais.
- Criar componente com 20 props.
- Reutilizar visual e misturar regra de negocio.

## Resumo mental

Nao reutilizar por ansiedade. Reutilizar quando a repeticao mostrou o padrao.

## Relacionado

- [[Componentes UI vs Feature]]
- [[Conhecimento/Frontend/React/Composicao em React|Composicao em React]]

