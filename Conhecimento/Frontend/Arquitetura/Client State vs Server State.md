# Client State vs Server State

## O que eu preciso lembrar

Client state e estado da interface.

Server state e dado que vem de fora, normalmente API/banco.

## Client state

Exemplos:

- modal aberto;
- aba selecionada;
- texto digitado;
- filtro local;
- menu aberto;
- tema.

Normalmente uso `useState`, `useReducer` ou contexto.

## Server state

Exemplos:

- usuario logado vindo da API;
- lista de produtos;
- pedidos;
- permissoes;
- comentarios.

Esse dado pode mudar fora da tela, entao precisa de estrategia de cache, loading, erro e revalidacao.

## Pegadinha comum

Guardar dado de API em `useState` funciona no comeco, mas pode ficar ruim quando preciso de:

- cache;
- refetch;
- loading padronizado;
- erro padronizado;
- sincronizacao entre telas.

## Resumo mental

Se o dado pertence a UI, e client state. Se o dado pertence ao servidor, e server state.

## Relacionado

- [[Camada de API]]
- [[Estados de UI Loading Empty Error Success]]
- [[Conhecimento/Frontend/React/State|State]]

