# Console e Logs

## O que eu preciso lembrar

Console mostra erros, avisos e valores durante execucao.

## Logs uteis

```js
console.log("valor", value);
console.warn("aviso");
console.error("erro");
```

## Log bom

```js
console.log("user antes do submit", user);
```

Log ruim:

```js
console.log(user);
```

Sem contexto fica dificil.

## Pegadinhas

- Deixar log demais.
- Logar dado sensivel.
- Achar que log antigo ainda representa state atual.

## Resumo mental

Log bom tem contexto e responde uma pergunta.

## Relacionado

- [[Metodo de Debugging]]

