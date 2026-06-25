# Encapsulamento

## O que eu preciso lembrar

Encapsulamento e esconder detalhes internos e expor formas seguras de usar algo.

## Exemplo

Ruim:

```ts
class BankAccount {
  balance = 0;
}

const account = new BankAccount();
account.balance = -999;
```

Melhor:

```ts
class BankAccount {
  private balance = 0;

  deposit(value: number) {
    if (value <= 0) {
      throw new Error("Valor invalido");
    }

    this.balance += value;
  }

  getBalance() {
    return this.balance;
  }
}
```

Agora eu controlo como o saldo muda.

## No frontend

Encapsulamento tambem aparece em hooks e componentes.

```tsx
function useToggle() {
  const [value, setValue] = useState(false);

  return {
    value,
    open: () => setValue(true),
    close: () => setValue(false),
    toggle: () => setValue((value) => !value),
  };
}
```

Quem usa nao precisa saber detalhes internos.

## Pegadinhas

- Esconder demais e dificultar teste.
- Expor estado interno mutavel.
- Criar getters/setters sem necessidade.

## Resumo mental

Encapsular e proteger a forma correta de usar algo.

## Relacionado

- [[Objeto e Classe]]
- [[Hooks Customizados]]

