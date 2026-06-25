# O que Testar no Frontend

## O que eu preciso lembrar

Eu testo comportamento importante, nao cada linha de codigo.

## Coisas boas para testar

- usuario consegue enviar formulario;
- erro aparece quando API falha;
- botao fica disabled quando deve;
- lista renderiza itens;
- filtro muda resultado;
- permissao esconde/mostra acao;
- funcao transforma dado corretamente.

## Coisas ruins para testar

- detalhes internos sem impacto;
- nome de classe que pode mudar;
- estado privado diretamente;
- implementacao exata de hook sem necessidade;
- snapshot gigante sem leitura.

## Pergunta principal

Se isso quebrar, o usuario ou o negocio percebe?

Se sim, vale teste.

## Resumo mental

Teste e para proteger comportamento importante.

## Relacionado

- [[Teste de Componente]]
- [[Teste de Integracao]]

