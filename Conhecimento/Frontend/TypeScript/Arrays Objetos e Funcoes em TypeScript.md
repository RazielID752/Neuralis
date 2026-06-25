# Arrays, Objetos e Funcoes em TypeScript

## O que eu preciso lembrar

TypeScript fica mais util quando eu uso tipos para explicar formato de dados e entrada/saida de funcoes.

## Arrays

Array de strings:

```ts
const nomes: string[] = ["Ana", "Marcos"];
```

Array de numeros:

```ts
const notas: number[] = [10, 8, 9];
```

Outra forma:

```ts
const notas: Array<number> = [10, 8, 9];
```

Eu prefiro `number[]` por ser mais direto.

## Objetos

Objeto simples:

```ts
const usuario = {
  id: "1",
  nome: "Marcos",
  ativo: true,
};
```

Com tipo separado:

```ts
type Usuario = {
  id: string;
  nome: string;
  ativo: boolean;
};

const usuario: Usuario = {
  id: "1",
  nome: "Marcos",
  ativo: true,
};
```

## Campo opcional

`?` significa que o campo pode nao existir.

```ts
type Usuario = {
  id: string;
  nome: string;
  avatarUrl?: string;
};
```

Se eu tentar usar direto, preciso lembrar que pode ser `undefined`.

```ts
function mostrarAvatar(usuario: Usuario) {
  if (usuario.avatarUrl) {
    console.log(usuario.avatarUrl);
  }
}
```

## Funcoes

Parametros precisam de tipo quando o TypeScript nao consegue inferir.

```ts
function somar(a: number, b: number) {
  return a + b;
}
```

O retorno foi inferido como number.

Tambem posso escrever o retorno:

```ts
function somar(a: number, b: number): number {
  return a + b;
}
```

## Funcao que nao retorna nada

```ts
function logarMensagem(mensagem: string): void {
  console.log(mensagem);
}
```

`void` significa que a funcao nao devolve um valor util.

## Funcao como tipo

```ts
type OnSelect = (id: string) => void;

function executar(onSelect: OnSelect) {
  onSelect("123");
}
```

Isso aparece muito em React com props:

```tsx
type ButtonProps = {
  onClick: () => void;
};
```

## Exemplo mais real

```ts
type Produto = {
  id: string;
  nome: string;
  preco: number;
  emEstoque: boolean;
};

function formatarPreco(produto: Produto) {
  return `R$ ${produto.preco.toFixed(2)}`;
}

function filtrarDisponiveis(produtos: Produto[]) {
  return produtos.filter((produto) => produto.emEstoque);
}
```

## Pegadinhas

- Array vazio geralmente precisa de tipo.
- Campo opcional pode ser `undefined`.
- Nem toda funcao precisa ter retorno escrito manualmente.
- `void` nao e a mesma coisa que `undefined` na pratica do dia a dia.

## Resumo mental

Objeto e formato. Array e lista de formatos. Funcao e contrato de entrada e saida.

## Exercicios para fixar

1. Crie um tipo `Pessoa` com `nome`, `idade` e `email`.
2. Crie um array `Pessoa[]`.
3. Crie uma funcao que recebe `Pessoa` e retorna uma string.
4. Crie uma funcao que recebe `Pessoa[]` e filtra maiores de idade.

## Relacionado

- [[Tipos Basicos]]
- [[Type Alias vs Interface]]
- [[TypeScript com React]]

