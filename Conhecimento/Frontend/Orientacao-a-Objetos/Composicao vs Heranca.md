# Composicao vs Heranca

## O que eu preciso lembrar

Composição geralmente é mais flexível que herança.

Herança pergunta: "isso é um tipo de quê?"

Composição pergunta: "isso é feito de quais partes?"

## Herança

```ts
class AdminUser extends User {}
```

## Composição

```ts
type User = {
  id: string;
  name: string;
  permissions: Permission[];
};
```

Ou em React:

```tsx
<Card>
  <UserInfo />
  <UserActions />
</Card>
```

## Exemplo prático

Em vez de:

```ts
class PrimaryButton extends Button {}
class DangerButton extends Button {}
```

Posso usar composição/configuração:

```tsx
<Button variant="primary">Salvar</Button>
<Button variant="danger">Remover</Button>
```

## Pegadinhas

- Herança para compartilhar estilo.
- Classe filha sobrescrevendo comportamento demais.
- Composição exagerada com componentes demais.

## Resumo mental

No frontend, antes de herdar, eu tento compor.

## Relacionado

- [[Heranca]]
- [[Conhecimento/Frontend/React/Composicao em React|Composicao em React]]

