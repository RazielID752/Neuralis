# Decisoes Arquiteturais

## O que eu preciso lembrar

Arquitetura e feita de decisoes e tradeoffs.

Uma decisao boa precisa registrar contexto, motivo e consequencia.

## Template simples

```md
# Decisao: usar estrutura por feature

## Contexto

O projeto esta crescendo e arquivos de uma mesma funcionalidade estao espalhados.

## Decisao

Vamos organizar novas telas dentro de `features/`.

## Consequencias positivas

- codigo relacionado fica perto;
- fica mais facil remover uma feature;
- reduz busca por arquivos.

## Consequencias negativas

- exige disciplina;
- pode duplicar componentes se shared nao for bem definido.
```

## Quando registrar

- estrutura de pastas;
- biblioteca importante;
- estrategia de estado;
- padrao de API;
- forma de autenticação;
- estrategia de testes.

## Pegadinhas

- Decisao sem contexto.
- Copiar decisao de outro projeto.
- Nao revisar decisao antiga.

## Resumo mental

Decisao arquitetural boa explica por que escolhi um caminho e qual custo aceitei.

## Relacionado

- [[Tradeoffs de Arquitetura]]
- [[Exemplo de Estrutura de Projeto Frontend]]

