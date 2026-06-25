# Dados e APIs

## O que eu preciso lembrar

Frontend quase sempre conversa com dados que vêm de fora.

Meu trabalho nao e so "dar fetch". Eu preciso entender:

- de onde o dado vem;
- qual formato ele tem;
- quanto tempo demora;
- o que acontece se falhar;
- como mostrar loading, erro, vazio e sucesso;
- se posso confiar nesse dado.

## Ordem recomendada

### 1. Base da web

- [[HTTP para Frontend]]
- [[JSON]]
- [[Status Codes]]

Objetivo: entender como frontend conversa com servidor.

### 2. Buscar dados

- [[Fetch API]]
- [[Exemplos de Consumo de API]]
- [[CRUD com API]]
- [[Headers e Autenticacao]]

Objetivo: fazer requests com clareza.

### 3. Confiabilidade

- [[Validacao de Dados da API]]
- [[Cache Retry e Revalidacao]]

Objetivo: lidar com dados reais, que falham, atrasam ou vêm errados.

## Perguntas que eu sempre devo fazer

- Essa chamada pode falhar?
- O que mostro enquanto carrega?
- O que mostro se vier vazio?
- O que mostro se der erro?
- Eu validei o formato da resposta?
- Esse dado precisa de cache?

## Pegadinhas grandes

- Achar que `fetch` da erro automaticamente em 404/500.
- Confiar cegamente no JSON da API.
- Misturar regra de API dentro de componente visual.
- Esquecer loading e error.
- Duplicar chamada em varias telas.

## Resumo mental

Dado de API e incerto: pode demorar, falhar, vir vazio ou vir diferente do esperado.
