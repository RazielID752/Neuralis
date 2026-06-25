# Container Queries

## O que eu preciso lembrar

Container query permite aplicar estilo com base no tamanho do container, nao da tela inteira.

## Problema

Media query olha viewport:

```css
@media (min-width: 768px) {
  .card {
    display: grid;
  }
}
```

Mas as vezes o componente esta em um container pequeno mesmo numa tela grande.

## Container query

```css
.card-wrapper {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 120px 1fr;
  }
}
```

## Quando usar

- componentes reutilizaveis;
- cards;
- sidebars;
- layouts onde o espaço do componente varia.

## Pegadinhas

- Precisa definir container.
- Nao substitui toda media query.
- Pode complicar se usado sem criterio.

## Resumo mental

Media query responde a tela. Container query responde ao espaço do componente.

## Relacionado

- [[Responsividade]]

