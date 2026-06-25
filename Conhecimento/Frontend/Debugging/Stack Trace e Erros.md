# Stack Trace e Erros

## O que eu preciso lembrar

Stack trace mostra o caminho do erro.

## Como ler

Normalmente olho:

1. mensagem do erro;
2. arquivo e linha;
3. primeira linha do meu codigo;
4. caminho de chamadas.

## Exemplo mental

```txt
TypeError: Cannot read properties of undefined
```

Isso geralmente significa que tentei acessar propriedade de algo que nao existe.

```js
user.name
```

Mas `user` estava `undefined`.

## Pegadinhas

- Ler so a ultima linha.
- Ignorar primeira linha do meu codigo.
- Nao entender se erro e build, runtime ou network.

## Resumo mental

Stack trace e mapa do erro. Eu procuro a primeira linha que aponta para meu codigo.

## Relacionado

- [[Metodo de Debugging]]

