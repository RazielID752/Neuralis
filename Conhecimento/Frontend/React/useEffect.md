# useEffect

## O que eu preciso lembrar

`useEffect` serve para sincronizar o componente com algo fora do React.

Nao e para calcular qualquer coisa.

## Exemplo simples

```tsx
import { useEffect } from "react";

function PageTitle({ title }: { title: string }) {
  useEffect(() => {
    document.title = title;
  }, [title]);

  return null;
}
```

Aqui o React sincroniza o titulo do documento com a prop `title`.

## Quando usar

- alterar `document.title`;
- escutar evento global;
- iniciar/parar timer;
- conectar com API externa;
- sincronizar com localStorage;
- subscriptions.

## Quando nao usar

Nao use effect para calcular algo que pode ser calculado durante renderizacao.

Ruim:

```tsx
const [fullName, setFullName] = useState("");

useEffect(() => {
  setFullName(firstName + " " + lastName);
}, [firstName, lastName]);
```

Melhor:

```tsx
const fullName = `${firstName} ${lastName}`.trim();
```

## Cleanup

Se o effect cria algo que precisa ser removido, retorno uma funcao.

```tsx
useEffect(() => {
  const id = setInterval(() => {
    console.log("tick");
  }, 1000);

  return () => clearInterval(id);
}, []);
```

## Dependencias

```tsx
useEffect(() => {
  document.title = title;
}, [title]);
```

O array diz quando o effect deve rodar de novo.

## Pegadinhas

- Esquecer dependencia.
- Colocar dependencia que muda toda hora.
- Fazer fetch sem pensar em loading/erro.
- Usar effect para derivar state.

## Resumo mental

`useEffect` e ponte com o mundo fora do React. Se tudo esta dentro do React, talvez nao precise dele.

## Relacionado

- [[Hooks]]
- [[State]]
- [[Timers setTimeout setInterval]]

