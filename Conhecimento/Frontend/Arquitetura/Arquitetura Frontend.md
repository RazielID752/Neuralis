# Arquitetura Frontend

## O que eu preciso lembrar

Arquitetura frontend e como eu organizo código para conseguir entender, mudar e crescer um projeto sem virar bagunça.

Nao e sobre criar pasta bonita. E sobre reduzir confusão.

## Explicando do zero

Quando um projeto e pequeno, qualquer organização parece funcionar.

Mas conforme cresce, aparecem perguntas:

- onde fica esse componente?
- essa função pertence a UI, regra de negocio ou API?
- esse state deveria estar aqui?
- quem trata erro?
- onde coloco loading?
- esse componente e reutilizável ou e especifico de uma tela?

Arquitetura ajuda a responder isso.

## Ordem recomendada

### 1. Organizar arquivos

- [[Organizacao de Pastas]]
- [[Separacao de Responsabilidades]]

Objetivo: saber onde cada coisa mora.

### 2. Organizar componentes

- [[Componentes UI vs Feature]]
- [[Composicao e Reutilizacao]]

Objetivo: evitar componente gigante e reaproveitar sem forcar abstração.

### 3. Organizar estado e dados

- [[Client State vs Server State]]
- [[Camada de API]]

Objetivo: entender o que fica no React, o que vem do servidor e onde buscar dados.

### 4. Organizar experiencia

- [[Estados de UI Loading Empty Error Success]]
- [[Tratamento de Erros no Frontend]]

Objetivo: não deixar a interface quebrar ou ficar muda.

### 5. Pensar em crescimento

- [[Tradeoffs de Arquitetura]]
- [[Checklist de Arquitetura Frontend]]
- [[Conhecimento/Frontend/Engenharia/Clean Code|Clean Code]]
- [[Conhecimento/Frontend/Engenharia/Clean Architecture|Clean Architecture]]
- [[Conhecimento/Frontend/Engenharia/SOLID|SOLID]]
- [[Conhecimento/Frontend/Engenharia/Arquitetura na Pratica em React|Arquitetura na Pratica em React]]

Objetivo: tomar decisoes melhores sem exagerar.

## Perguntas que eu sempre devo fazer

- Essa pasta ajuda ou so enfeita?
- Esse componente sabe coisa demais?
- Essa logica deveria estar em hook, funcao, componente ou API?
- Esse dado e client state ou server state?
- O usuario ve loading, vazio e erro?
- Se eu mudar essa feature, quantos lugares preciso mexer?

## Pegadinhas grandes

- Criar arquitetura complexa para projeto pequeno.
- Misturar chamada de API dentro de qualquer componente.
- Criar componente "reutilizavel" antes de existir repeticao real.
- Guardar server state em `useState` sem criterio.
- Ignorar estados de erro e vazio.
- Separar por tipo de arquivo e perder contexto de feature.

## Resumo mental

Arquitetura boa faz o proximo passo ficar obvio. Se eu sempre preciso pensar "onde coloco isso?", a arquitetura ainda nao esta clara.
