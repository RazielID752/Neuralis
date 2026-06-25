# OCP: Open Closed Principle

## O que eu preciso lembrar

O codigo deve ser facil de estender sem precisar ficar alterando a mesma funcao toda hora.

## Explicando do zero

Se toda nova variante exige adicionar mais um `if`, talvez eu precise trocar condicionais por um mapa ou composição.

## Exemplo ruim

```ts
function getBadgeClass(status: string) {
  if (status === "success") return "bg-green-100 text-green-800";
  if (status === "error") return "bg-red-100 text-red-800";
  if (status === "warning") return "bg-yellow-100 text-yellow-800";
  return "bg-gray-100 text-gray-800";
}
```

Funciona, mas cresce com `if`.

## Melhor com mapa

```ts
const badgeClasses = {
  success: "bg-green-100 text-green-800",
  error: "bg-red-100 text-red-800",
  warning: "bg-yellow-100 text-yellow-800",
  default: "bg-gray-100 text-gray-800",
};

type BadgeStatus = keyof typeof badgeClasses;

function getBadgeClass(status: BadgeStatus) {
  return badgeClasses[status];
}
```

Para adicionar novo status, adiciono no mapa.

## Exemplo com componentes

```tsx
const fieldRenderers = {
  text: TextField,
  email: EmailField,
  password: PasswordField,
};
```

Em vez de um componente gigante com vários `if`, posso mapear tipo para componente.

## Quando nao aplicar

Se existem so dois casos e nao vao crescer, `if` simples e ok.

OCP nao e desculpa para complicar.

## Pegadinhas

- Criar sistema extensivel para problema fixo.
- Usar mapa quando `if` e mais claro.
- Tipar status como `string` e perder seguranca.

## Resumo mental

OCP me ajuda quando o codigo cresce por variantes.

## Relacionado

- [[SOLID]]
- [[Variantes com clsx]]

