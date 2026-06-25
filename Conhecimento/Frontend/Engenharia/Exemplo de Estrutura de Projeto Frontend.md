# Exemplo de Estrutura de Projeto Frontend

## O que eu preciso lembrar

Nao existe estrutura perfeita. Existe estrutura que ajuda o projeto atual.

## Estrutura para projeto medio

```txt
src/
  app/
    routes/
    providers/
  features/
    auth/
    tasks/
    dashboard/
  shared/
    components/
    hooks/
    lib/
    utils/
    types/
  styles/
```

## app

Coisas globais:

- rotas;
- providers;
- layout raiz;
- configuracoes globais.

## features

Funcionalidades do produto:

- autenticação;
- tarefas;
- dashboard;
- perfil;
- pagamentos.

## shared

Coisas realmente compartilhadas:

- `Button`;
- `Input`;
- `formatCurrency`;
- `cn`;
- hooks genericos.

## Exemplo de feature tasks

```txt
features/tasks/
  api/
    tasks-api.ts
  components/
    task-card.tsx
    task-list.tsx
  hooks/
    use-tasks.ts
  model/
    task-types.ts
    task-rules.ts
  pages/
    tasks-page.tsx
```

## Pegadinhas

- Criar `shared` cedo demais.
- Separar por feature quando o projeto ainda e pequeno.
- Colocar tudo em `utils`.
- Ter `components` global com componentes especificos.

## Resumo mental

Eu separo por feature quando contexto junto importa mais que tipo de arquivo.

## Relacionado

- [[Organizacao de Pastas]]
- [[Arquitetura na Pratica em React]]

