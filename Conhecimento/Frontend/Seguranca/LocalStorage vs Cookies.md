# LocalStorage vs Cookies

## O que eu preciso lembrar

localStorage e acessivel por JavaScript. Cookie pode ser configurado para nao ser.

## localStorage

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");
```

Bom para:

- tema;
- preferencia local;
- dado nao sensivel.

Ruim para:

- token sensivel;
- dado privado;
- segredo.

## Cookies

Cookies sao enviados automaticamente em requests para o dominio.

Com `httpOnly`, JavaScript nao consegue ler.

Configuracoes importantes:

- `httpOnly`;
- `secure`;
- `sameSite`.

## Pegadinhas

- localStorage nao expira sozinho.
- XSS pode ler localStorage.
- Cookie mal configurado pode abrir risco.
- Nunca guardar segredo de backend no frontend.

## Resumo mental

Preferencia pode ir no localStorage. Credencial exige muito mais cuidado.

## Relacionado

- [[Tokens no Frontend]]
- [[XSS]]

