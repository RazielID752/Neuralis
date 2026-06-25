# Polimorfismo

## O que eu preciso lembrar

Polimorfismo é usar coisas diferentes através da mesma interface.

## Exemplo simples

```ts
type PaymentMethod = {
  pay: (amount: number) => Promise<void>;
};

async function checkout(payment: PaymentMethod) {
  await payment.pay(100);
}
```

Agora posso passar formas diferentes de pagamento:

```ts
const creditCardPayment = {
  pay: async (amount: number) => {
    console.log("Pagando no cartao", amount);
  },
};

const pixPayment = {
  pay: async (amount: number) => {
    console.log("Pagando com pix", amount);
  },
};
```

Ambos funcionam porque têm `pay`.

## No frontend

Componentes também podem ter comportamento polimórfico:

```tsx
function Action({ as: Component = "button", ...props }) {
  return <Component {...props} />;
}
```

Mas isso pode complicar, então usar com cuidado.

## Pegadinhas

- Criar abstração sem precisar.
- Interface generica demais.
- Usar polimorfismo onde um simples mapa resolveria.

## Resumo mental

Polimorfismo é trocar implementação mantendo o mesmo contrato.

## Relacionado

- [[DIP Dependency Inversion Principle]]
- [[TypeScript/Type Alias vs Interface]]

