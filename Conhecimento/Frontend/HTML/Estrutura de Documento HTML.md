# Estrutura de Documento HTML

## O que eu preciso lembrar

Todo HTML tem uma estrutura base: documento, cabeca e corpo.

## Explicando do zero

Um arquivo HTML e como uma pagina com duas partes:

- `head`: informacoes sobre a pagina;
- `body`: o que aparece para o usuario.

## Exemplo bem simples

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha pagina</title>
  </head>
  <body>
    <h1>Ola, mundo</h1>
  </body>
</html>
```

## O que cada parte faz

- `<!doctype html>`: diz que estou usando HTML moderno.
- `<html lang="pt-BR">`: raiz do documento e idioma da pagina.
- `<head>`: configuracoes e metadados.
- `<meta charset="UTF-8">`: aceita acentos corretamente.
- `<meta name="viewport">`: faz responsividade funcionar melhor em celular.
- `<title>`: titulo da aba do navegador.
- `<body>`: conteudo visivel.

## Pegadinhas

- Esquecer `lang`.
- Esquecer `viewport`.
- Colocar conteudo visual dentro do `head`.
- Achar que `title` e o mesmo que `h1`.

## Resumo mental

`head` configura. `body` aparece. `title` e aba. `h1` e titulo do conteudo.

## Exercicios para fixar

1. Crie um HTML minimo.
2. Coloque `lang="pt-BR"`.
3. Adicione `title`.
4. Adicione um `h1` e um paragrafo.

## Relacionado

- [[HTML]]
- [[HTML Semantico]]

