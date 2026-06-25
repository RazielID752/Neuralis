# Como Quebrar um Problema

## O que eu preciso lembrar

Antes de criar codigo, eu preciso escrever o problema em passos.

## Metodo simples

1. Escrever o objetivo.
2. Descobrir entrada.
3. Descobrir saida.
4. Listar regras.
5. Criar exemplos.
6. Quebrar em passos.
7. Transformar passos em funcoes.

## Exemplo

Problema:

```txt
Tenho uma lista de produtos e quero mostrar apenas os produtos em estoque com preco formatado.
```

Entrada:

```ts
type Product = {
  id: string;
  name: string;
  price: number;
  inStock: boolean;
};
```

Saida:

```ts
type ProductView = {
  id: string;
  name: string;
  priceLabel: string;
};
```

Passos:

1. filtrar produtos em estoque;
2. formatar preco;
3. retornar novo formato.

Codigo:

```ts
function formatPrice(price: number) {
  return `R$ ${price.toFixed(2)}`;
}

function toProductView(product: Product): ProductView {
  return {
    id: product.id,
    name: product.name,
    priceLabel: formatPrice(product.price),
  };
}

function getAvailableProducts(products: Product[]) {
  return products.filter((product) => product.inStock).map(toProductView);
}
```

## O que aconteceu

Em vez de uma funcao fazer tudo, cada funcao ganhou um nome:

- `formatPrice`;
- `toProductView`;
- `getAvailableProducts`.

## Pegadinhas

- Pular direto para codigo.
- Nao saber qual saida espero.
- Criar funcao sem nome claro.
- Tentar resolver regra, API e UI na mesma funcao.

## Resumo mental

Se eu nao consigo listar os passos, ainda nao entendi o problema.

## Exercicios para fixar

1. Pegue uma lista de usuarios e filtre ativos.
2. Formate o nome em maiusculo.
3. Retorne apenas `id` e `name`.
4. Separe cada passo em uma funcao.

## Relacionado

- [[Como Criar Funcoes Pequenas]]
- [[Entrada Processamento Saida]]

