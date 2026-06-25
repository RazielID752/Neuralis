# Objeto

## O que eu preciso lembrar

Objeto guarda informacao em pares de chave e valor.

## Exemplo simples

```ts
const usuario = {
  id: "1",
  nome: "Marcos",
  ativo: true,
};
```

## Acessar valor

```ts
console.log(usuario.nome);
```

## Atualizar sem mutar

```ts
const usuarioAtualizado = {
  ...usuario,
  ativo: false,
};
```

## Quando usar objeto

- representar uma entidade;
- agrupar dados relacionados;
- guardar estado de formulario;
- criar mapa simples.

## Objeto como mapa

```ts
const usersById = {
  "1": { id: "1", name: "Ana" },
  "2": { id: "2", name: "Marcos" },
};
```

Uso:

```ts
const user = usersById["1"];
```

## Pegadinhas

- Objeto nao e lista.
- Ordem das chaves nao deve ser base principal da logica.
- Spread faz copia rasa.
- Chaves viram string.

## Resumo mental

Objeto e bom para representar "uma coisa" com propriedades.

## Relacionado

- [[Array]]
- [[Map]]
- [[Conhecimento/Frontend/TypeScript/Arrays Objetos e Funcoes em TypeScript|Arrays Objetos e Funcoes em TypeScript]]

