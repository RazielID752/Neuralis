# Estados de UI: Loading, Empty, Error, Success

## O que eu preciso lembrar

Toda tela que busca dados precisa pensar em quatro estados:

- carregando;
- vazio;
- erro;
- sucesso.

## Exemplo mental

```tsx
if (status === "loading") return <p>Carregando...</p>;
if (status === "error") return <p>Erro ao carregar.</p>;
if (items.length === 0) return <p>Nenhum item encontrado.</p>;

return <List items={items} />;
```

## Loading

O usuario precisa saber que algo esta acontecendo.

## Empty

Lista vazia nao e erro. E um estado.

## Error

Erro precisa orientar:

- o que aconteceu;
- se pode tentar de novo;
- o que fazer agora.

## Success

Mostra o conteudo esperado.

## Pegadinhas

- Tela ficar em branco.
- Mostrar erro tecnico para usuario.
- Tratar vazio como erro.
- Esquecer retry.

## Resumo mental

Interface boa nao desaparece quando algo da errado.

## Relacionado

- [[Tratamento de Erros no Frontend]]
- [[Client State vs Server State]]

