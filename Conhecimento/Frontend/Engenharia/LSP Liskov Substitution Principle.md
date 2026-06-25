# LSP: Liskov Substitution Principle

## O que eu preciso lembrar

Se uma coisa promete se comportar como outra, ela nao pode quebrar essa expectativa.

No frontend, isso aparece muito em componentes reutilizaveis.

## Exemplo mental

Se meu componente `Button` aceita props de `button`, ele deve se comportar como botao.

Ruim:

```tsx
function Button({ onClick, disabled, children }: ButtonProps) {
  return (
    <div onClick={disabled ? undefined : onClick}>
      {children}
    </div>
  );
}
```

Esse componente parece botao, mas nao tem comportamento nativo de botao.

Melhor:

```tsx
type ButtonProps = React.ComponentProps<"button">;

function Button(props: ButtonProps) {
  return <button {...props} />;
}
```

## Outro exemplo

Se um componente recebe `href`, talvez ele seja link, nao botao.

```tsx
function LinkButton({ href, children }: { href: string; children: React.ReactNode }) {
  return <a href={href}>{children}</a>;
}
```

## Sinais de quebra de LSP

- componente parece um, mas age como outro;
- prop existe mas e ignorada;
- `disabled` visual mas ainda clicavel;
- `onClick` funciona diferente do esperado;
- componente reutilizavel tem surpresa.

## Pegadinhas

- Fazer `div` clicavel no lugar de button.
- Criar componente "Button" que renderiza link sem avisar.
- Ignorar props nativas importantes.

## Resumo mental

Se parece botao, deve agir como botao. Se parece link, deve agir como link.

## Relacionado

- [[SOLID]]
- [[Acessibilidade em HTML]]
- [[TypeScript com React]]

