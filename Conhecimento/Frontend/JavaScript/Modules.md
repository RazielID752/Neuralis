# Modules

## Ideia central

Modulos permitem separar codigo em arquivos com importacoes e exportacoes explicitas.

## Exemplo minimo

```js
export function sum(a, b) {
  return a + b;
}
```

```js
import { sum } from "./sum.js";
```

