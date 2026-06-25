# Teste de Componente

## O que eu preciso lembrar

Teste de componente verifica se uma parte da UI se comporta corretamente.

## Exemplo mental

Um componente `LoginForm` deve:

- renderizar email e senha;
- permitir digitar;
- chamar submit;
- mostrar erro se falhar.

## O que testar

- texto visivel;
- interacao do usuario;
- estado de loading;
- erro;
- callback chamado;
- acessibilidade basica.

## Pegadinhas

- Testar state interno diretamente.
- Procurar elemento por classe em vez de texto/role.
- Ignorar interacao real.

## Resumo mental

Teste componente como usuario usa, nao como o codigo foi escrito por dentro.

## Relacionado

- [[Forms em React]]
- [[O que Testar no Frontend]]

