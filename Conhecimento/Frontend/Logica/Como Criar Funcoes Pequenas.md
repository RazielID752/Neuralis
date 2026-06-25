# Como Criar Funcoes Pequenas

## O que eu preciso lembrar

Funcao pequena deve fazer uma coisa com nome claro.

## Sinal de funcao grande demais

- muitos `if`;
- muitas variaveis temporarias;
- muitos comentarios explicando blocos;
- nome generico tipo `handleData`;
- mistura validacao, transformação e efeito colateral.

## Tecnica: transformar comentario em funcao

Antes:

```ts
function handleProducts(products: Product[]) {
  // filtra produtos em estoque
  const available = products.filter((product) => product.inStock);

  // formata preco
  const formatted = available.map((product) => ({
    ...product,
    priceLabel: `R$ ${product.price.toFixed(2)}`,
  }));

  return formatted;
}
```

Depois:

```ts
function isAvailable(product: Product) {
  return product.inStock;
}

function formatPrice(price: number) {
  return `R$ ${price.toFixed(2)}`;
}

function toProductView(product: Product) {
  return {
    ...product,
    priceLabel: formatPrice(product.price),
  };
}

function getAvailableProductViews(products: Product[]) {
  return products.filter(isAvailable).map(toProductView);
}
```

## Beneficio

Agora eu consigo testar e entender cada parte.

## Pegadinhas

- Quebrar em funcoes pequenas demais sem ganho.
- Criar nome ruim.
- Separar codigo que so faz sentido junto.

## Resumo mental

Funcao pequena boa tem nome que explica a intencao.

## Relacionado

- [[Refatorando Funcao Grande]]
- [[Entrada Processamento Saida]]

