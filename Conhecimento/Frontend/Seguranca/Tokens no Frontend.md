# Tokens no Frontend

## O que eu preciso lembrar

Token e uma credencial. Se alguem pega, pode se passar pelo usuario dependendo do tipo de token.

## Bearer token

```ts
fetch("/api/me", {
  headers: {
    Authorization: `Bearer ${token}`,
  },
});
```

Bearer significa: quem carrega esse token consegue usar.

## Onde guardar?

Nao existe resposta perfeita. Tem tradeoff.

### Memory

Guardar em memoria:

- menos persistente;
- perde ao recarregar;
- reduz exposicao em storage.

### localStorage

- persiste;
- facil de usar;
- acessivel por JavaScript;
- perigoso em caso de XSS.

### Cookie httpOnly

- nao acessivel por JavaScript;
- melhor contra roubo via XSS;
- precisa configurar SameSite/Secure;
- envolve cuidado com CSRF dependendo do caso.

## Pegadinhas

- Colocar token em URL.
- Logar token no console.
- Guardar refresh token sem pensar.
- Expor chave privada no frontend.

## Resumo mental

Token e chave de acesso. Eu trato como sensivel.

## Relacionado

- [[LocalStorage vs Cookies]]
- [[Headers e Autenticacao]]

