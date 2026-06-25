# Tratamento de Erros em JavaScript

## O que eu preciso lembrar

Erro precisa ser previsto, capturado e transformado em feedback ou decisao.

## try/catch

```js
try {
  const data = JSON.parse(text);
  console.log(data);
} catch (error) {
  console.error("JSON invalido", error);
}
```

## Throw

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error("Nao pode dividir por zero");
  }

  return a / b;
}
```

## Com async/await

```js
async function loadUsers() {
  try {
    const response = await fetch("/api/users");

    if (!response.ok) {
      throw new Error("Erro ao buscar usuarios");
    }

    return response.json();
  } catch (error) {
    console.error(error);
    throw error;
  }
}
```

## Pegadinhas

- `catch` vazio esconde problema.
- Nem todo erro tem mensagem boa.
- Erro tecnico nem sempre deve aparecer para usuario.
- Em `fetch`, 404/500 nao caem no catch automaticamente.

## Resumo mental

Erro bom nao some. Ele vira decisao: tentar de novo, mostrar mensagem, registrar ou parar fluxo.

## Relacionado

- [[Conhecimento/Frontend/Dados/Fetch API|Fetch API]]
- [[Conhecimento/Frontend/Arquitetura/Tratamento de Erros no Frontend|Tratamento de Erros no Frontend]]

