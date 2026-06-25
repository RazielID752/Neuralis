# Cache, Retry e Revalidacao

## O que eu preciso lembrar

Dados remotos podem ser reaproveitados, tentar de novo ou atualizar depois.

## Cache

Cache guarda uma resposta para evitar buscar de novo sem necessidade.

Exemplo mental:

```txt
Ja busquei usuario 1 -> guardo -> uso de novo
```

## Retry

Retry tenta novamente depois de falha.

Bom para:

- erro temporario;
- instabilidade de rede;
- servidor indisponivel por pouco tempo.

Ruim para:

- erro de validacao;
- 401/403;
- request que cria pagamento ou acao sensivel sem idempotencia.

## Revalidacao

Revalidar e buscar de novo para garantir dado atualizado.

## Pegadinhas

- Cache velho mostrando dado errado.
- Retry infinito.
- Retentar POST perigoso.
- Nao diferenciar erro temporario de erro permanente.

## Resumo mental

Cache melhora velocidade. Retry melhora resiliencia. Revalidacao melhora atualizacao.

## Relacionado

- [[Client State vs Server State]]
- [[Fetch API]]

