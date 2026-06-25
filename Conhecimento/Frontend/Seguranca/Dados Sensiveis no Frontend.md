# Dados Sensiveis no Frontend

## O que eu preciso lembrar

Tudo que chega no frontend pode ser visto pelo usuario.

Nao mando para o navegador dado que o usuario nao deveria ver.

## Exemplos de dados sensiveis

- token;
- documento;
- email privado;
- dados financeiros;
- permissoes internas;
- segredo de API;
- chave privada;
- dados de outro usuario.

## Regra importante

Nao confie em esconder com CSS ou condicional.

Ruim:

```tsx
{isAdmin && <p>{secret}</p>}
```

Se `secret` chegou no frontend, pode ser inspecionado.

## Variaveis de ambiente

Variavel publica de frontend nao e segredo.

Se aparece no bundle, usuario pode ver.

## Pegadinhas

- Enviar lista completa e esconder parte na UI.
- Retornar campos sensiveis da API sem necessidade.
- Colocar chave secreta em app frontend.
- Logar dado privado.

## Resumo mental

Se o usuario nao pode saber, nao envie para o frontend.

## Relacionado

- [[Tokens no Frontend]]
- [[Seguranca Frontend]]

