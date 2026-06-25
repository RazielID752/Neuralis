# Tratamento de Erros no Frontend

## O que eu preciso lembrar

Erro nao e so `console.log`. Erro e parte da experiencia.

## Tipos de erro

- erro de validacao;
- erro de rede;
- erro de permissao;
- erro inesperado;
- erro de servidor;
- erro de estado impossivel.

## Exemplo simples

```ts
async function getUsers() {
  const response = await fetch("/api/users");

  if (!response.ok) {
    throw new Error("Nao foi possivel buscar usuarios");
  }

  return response.json();
}
```

## Na UI

```tsx
if (error) {
  return (
    <div role="alert">
      <p>Nao foi possivel carregar.</p>
      <button onClick={retry}>Tentar novamente</button>
    </div>
  );
}
```

## Pegadinhas

- Engolir erro com `catch` vazio.
- Mostrar erro tecnico cru para usuario.
- Nao ter estado de retry.
- Tratar todos os erros iguais.

## Resumo mental

Erro bom ajuda o usuario a continuar.

## Relacionado

- [[Estados de UI Loading Empty Error Success]]
- [[Camada de API]]

