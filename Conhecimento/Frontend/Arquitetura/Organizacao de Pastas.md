# Organizacao de Pastas

## O que eu preciso lembrar

Pasta serve para eu encontrar codigo e entender contexto.

Organizacao boa nao e a mais bonita. E a que reduz duvida.

## Por tipo de arquivo

Exemplo:

```txt
src/
  components/
  hooks/
  services/
  utils/
  pages/
```

Vantagem:

- simples de entender no comeco.

Problema:

- quando cresce, uma feature fica espalhada em varias pastas.

## Por feature

Exemplo:

```txt
src/
  features/
    auth/
      components/
      hooks/
      api/
      types.ts
    dashboard/
      components/
      hooks/
      api/
      types.ts
  shared/
    components/
    utils/
```

Vantagem:

- tudo de uma feature fica perto.

Problema:

- pode ser exagero para projeto pequeno.

## Minha regra mental

Projeto pequeno:

```txt
src/
  components/
  pages/
  lib/
  hooks/
```

Projeto crescendo:

```txt
src/
  features/
  shared/
  app/
```

## O que vai em shared

Use `shared` para coisas realmente compartilhadas:

- botao generico;
- input generico;
- formatadores;
- helpers;
- hooks reutilizaveis.

Nao jogue tudo em shared so porque ficou em duvida.

## Pegadinhas

- Criar pasta demais cedo demais.
- Colocar tudo em `utils`.
- Colocar componente especifico em `shared`.
- Ter tres lugares possiveis para o mesmo arquivo.

## Resumo mental

Se uma pasta nao ajuda a decidir onde colocar algo, ela talvez esteja mal definida.

## Exercicios para fixar

1. Desenhe a estrutura de um app de tarefas.
2. Separe o que e feature e o que e shared.
3. Pegue um componente e decida onde ele deveria morar.

## Relacionado

- [[Separacao de Responsabilidades]]
- [[Componentes UI vs Feature]]

