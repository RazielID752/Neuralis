# JavaScript

## O que eu preciso lembrar

JavaScript e a linguagem que faz a pagina ter comportamento.

HTML monta a estrutura. CSS deixa visual. JavaScript faz as coisas acontecerem: clique, formulario, menu, API, dados, interacao.

## Como eu vou estudar JavaScript

O ideal para mim e misturar duas coisas:

- explicacao do zero, sem pular base;
- resumo pessoal, para eu bater o olho e lembrar.

Cada nota deve ter exemplos pequenos, pegadinhas e exercicios.

## Guia principal

- [[JavaScript do Zero ao Avancado]]

## Ordem recomendada

### 1. Base da linguagem

- [[Variaveis var let const]]
- [[Operadores e Comparacoes]]
- [[Booleanos e Condicionais]]
- [[Loops]]

Objetivo: entender como o codigo guarda valores, compara coisas e toma decisoes.

### 2. Reutilizar codigo

- [[Funcoes e Callbacks]]
- [[Closures]]

Objetivo: entender funcoes, parametros, retorno, callbacks e como funcoes lembram valores.

### 3. Trabalhar com dados

- [[Arrays e Objetos]]

Objetivo: saber guardar listas e informacoes estruturadas, porque quase tudo em React e API vira array ou objeto.

### 4. Mexer com pagina

- [[DOM e Eventos]]

Objetivo: entender como JavaScript conversa com HTML antes de ir fundo em React.

### 5. Codigo assincrono

- [[Timers setTimeout setInterval]]
- [[Promises]]
- [[Async Await]]

Objetivo: entender codigo que nao termina imediatamente: timers, APIs, fetch, carregamento e erro.

### 6. Organizar codigo

- [[Modules]]

Objetivo: separar codigo em arquivos e importar/exportar funcoes.

## Perguntas que eu sempre devo fazer

- Esse valor muda ou e fixo?
- Esse codigo precisa repetir?
- Esse dado e uma lista ou um objeto?
- Essa condicao retorna `true` ou `false`?
- Esse codigo roda agora ou depois?
- Esse erro e de sintaxe, tipo de dado ou ordem de execucao?

## Pegadinhas grandes de JavaScript

- `const` nao torna objeto congelado.
- `==` converte tipo; prefira `===`.
- `[]` e `{}` sao truthy.
- `setTimeout` nao pausa o codigo inteiro.
- `this` muda dependendo de como a funcao e chamada.
- `map` retorna um novo array; `forEach` nao.
- `async/await` ainda usa promises por baixo.

## Resumo mental

JavaScript e sobre fluxo: guardar valores, transformar dados, tomar decisoes, reagir a eventos e lidar com coisas que acontecem depois.

