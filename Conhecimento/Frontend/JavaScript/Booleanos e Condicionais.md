# Booleanos e Condicionais

## Explicacao em uma frase

Booleanos representam verdadeiro ou falso, e condicionais fazem o codigo tomar decisoes.

## Booleanos

Existem dois valores booleanos:

```js
const possuiGraduacao = true;
const possuiDoutorado = false;
```

Voce usa booleanos para representar estados como:

- usuario logado ou nao;
- menu aberto ou fechado;
- formulario valido ou invalido;
- carregando ou parado;
- maior de idade ou menor de idade.

## `if` e `else`

`if` executa um bloco se a condicao for verdadeira.

```js
const possuiGraduacao = true;

if (possuiGraduacao) {
  console.log("Possui graduacao");
} else {
  console.log("Nao possui graduacao");
}
```

O valor dentro dos parenteses sempre e avaliado como verdadeiro ou falso.

## `else if`

Use quando existem mais de duas possibilidades.

```js
const minhaIdade = 25;
const idadeParente = 30;

if (minhaIdade > idadeParente) {
  console.log("E maior");
} else if (minhaIdade === idadeParente) {
  console.log("E igual");
} else {
  console.log("E menor");
}
```

## `switch`

`switch` compara um valor com varios casos.

```js
const corFavorita = "Azul";

switch (corFavorita) {
  case "Azul":
    console.log("Olhe para o ceu.");
    break;
  case "Vermelho":
    console.log("Olhe para rosas.");
    break;
  case "Amarelo":
    console.log("Olhe para o sol.");
    break;
  default:
    console.log("Feche os olhos.");
}
```

Use `break` para impedir que o JavaScript continue executando os proximos casos.

## Truthy e falsy

JavaScript avalia alguns valores como falso mesmo que eles nao sejam literalmente `false`.

Falsy:

```js
false;
0;
-0;
NaN;
null;
undefined;
"";
```

Truthy:

```js
true;
1;
" ";
"andre";
-5;
{};
[];
```

Pegadinha: array vazio e objeto vazio sao truthy.

```js
if ([]) {
  console.log("Array vazio e truthy");
}
```

## Condicional ternario

Use ternario para escolhas simples.

```js
const idade = 18;
const mensagem = idade >= 18 ? "Maior de idade" : "Menor de idade";
```

Evite ternarios grandes demais. Se ficar dificil de ler, use `if`.

## Exercicio

O que aparece?

```js
if (("Gato" === "gato") && (5 > 2)) {
  console.log("Verdadeiro");
} else {
  console.log("Falso");
}
```

Resposta: `"Falso"`, porque `"Gato" === "gato"` e `false`. JavaScript diferencia maiusculas e minusculas.

## Exercicio

O que aparece?

```js
if (("Gato" === "gato") || (5 > 2)) {
  console.log("Gato" && "Cao");
} else {
  console.log("Falso");
}
```

Resposta: `"Cao"`.

Por que?

- `"Gato" === "gato"` e `false`;
- `5 > 2` e `true`;
- `false || true` e `true`;
- `"Gato" && "Cao"` retorna o ultimo truthy: `"Cao"`.

## Relacionado

- [[Operadores e Comparacoes]]
- [[JavaScript do Zero ao Avancado]]

