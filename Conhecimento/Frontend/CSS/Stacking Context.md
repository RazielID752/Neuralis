# Stacking Context

## O que eu preciso lembrar

Stacking context explica por que `z-index` as vezes nao funciona como eu espero.

## Ideia

Elementos podem criar contextos de empilhamento próprios.

Dentro de um contexto, `z-index` compete com irmãos daquele contexto, nao com a pagina inteira.

## Coisas que podem criar stacking context

- `position` com `z-index`;
- `opacity` menor que 1;
- `transform`;
- `filter`;
- `isolation`;
- alguns modos de contain.

## Exemplo mental

Um modal com `z-index: 9999` pode ficar atras se estiver preso dentro de um pai que criou stacking context baixo.

## Pegadinhas

- Aumentar `z-index` infinitamente sem resolver.
- Esquecer que `transform` cria contexto.
- Modal dentro de container errado.

## Resumo mental

Se `z-index` nao funciona, talvez o problema seja o contexto, nao o numero.

## Relacionado

- [[Display Position e Z Index]]

