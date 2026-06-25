# Seguranca Frontend

## O que eu preciso lembrar

Frontend nao e lugar seguro para segredo.

Tudo que vai para o navegador pode ser visto, inspecionado ou manipulado pelo usuario.

## Ordem recomendada

- [[XSS]]
- [[Tokens no Frontend]]
- [[LocalStorage vs Cookies]]
- [[Dados Sensiveis no Frontend]]
- [[Dependencias e Supply Chain]]

## Perguntas que eu sempre devo fazer

- Estou colocando segredo no frontend?
- Esse dado veio de usuario?
- Esse HTML pode executar script?
- Onde estou guardando token?
- Essa dependencia e confiavel?
- O backend tambem valida isso?

## Pegadinhas grandes

- Achar que esconder no frontend protege.
- Guardar token sensivel em qualquer lugar sem pensar.
- Renderizar HTML vindo de usuario.
- Confiar em validacao so no frontend.
- Expor chave privada em `.env` publico.

## Resumo mental

Frontend melhora experiencia e reduz erro, mas seguranca real precisa considerar que o navegador nao e ambiente confiavel.

