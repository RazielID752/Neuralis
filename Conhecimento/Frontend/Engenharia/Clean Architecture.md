# Clean Architecture

## O que eu preciso lembrar

Clean Architecture e uma forma de separar regras importantes do app de detalhes externos.

Detalhe externo pode ser:

- React;
- API;
- localStorage;
- banco;
- biblioteca;
- framework;
- UI.

## Ideia central

Regra de negocio nao deveria depender de React.

Exemplo: calcular total do carrinho nao precisa saber se a tela usa React, Vue ou console.

## Camadas mentais

### Domain

Regras principais.

```ts
function calculateCartTotal(items: CartItem[]) {
  return items.reduce((total, item) => total + item.price * item.quantity, 0);
}
```

### Application

Casos de uso.

```ts
async function checkoutCart(cart: Cart, payment: PaymentService) {
  const total = calculateCartTotal(cart.items);
  return payment.pay(total);
}
```

### Infrastructure

Detalhes externos.

```ts
const stripePaymentService = {
  pay: (total: number) => stripe.pay(total),
};
```

### UI

React, componentes, telas.

```tsx
function CheckoutButton() {
  return <button>Finalizar compra</button>;
}
```

## Dependencia aponta para dentro

UI pode usar caso de uso.

Caso de uso pode usar regra.

Regra nao deveria depender da UI.

## Exemplo simples no frontend

Ruim:

```tsx
function CartSummary({ items }: { items: CartItem[] }) {
  const total = items.reduce((sum, item) => sum + item.price * item.quantity, 0);

  return <p>Total: {total}</p>;
}
```

Melhor:

```ts
export function calculateCartTotal(items: CartItem[]) {
  return items.reduce((sum, item) => sum + item.price * item.quantity, 0);
}
```

```tsx
function CartSummary({ items }: { items: CartItem[] }) {
  const total = calculateCartTotal(items);

  return <p>Total: {total}</p>;
}
```

## Pegadinhas

- Aplicar camadas demais em projeto pequeno.
- Criar pasta `domain` sem regra de negocio real.
- Transformar tudo em classe.
- Achar que Clean Architecture e obrigatoriamente backend.

## Resumo mental

Clean Architecture protege regras importantes dos detalhes que mudam.

## Relacionado

- [[Separando UI Regras e Infra]]
- [[Arquitetura na Pratica em React]]
- [[Tradeoffs de Arquitetura]]

