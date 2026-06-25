# DOM e Eventos

## Explicacao em uma frase

DOM e a representacao da pagina no JavaScript, e eventos sao a forma de reagir ao usuario.

## O que e DOM

DOM significa Document Object Model.

Quando o navegador le seu HTML, ele cria uma arvore de objetos que o JavaScript consegue acessar.

HTML:

```html
<p id="mensagem">Texto original</p>
```

JavaScript:

```js
const mensagem = document.getElementById("mensagem");
console.log(mensagem.innerText);
```

## Alterando texto

```html
<button id="botao">Clique aqui</button>
<p id="mensagem">Texto original</p>
```

```js
const botao = document.getElementById("botao");
const mensagem = document.getElementById("mensagem");

botao.addEventListener("click", function () {
  mensagem.innerText = "Texto alterado!";
});
```

Prefira `addEventListener` em vez de `onclick` direto no HTML, porque separa estrutura de comportamento.

## Seletores comuns

```js
document.getElementById("mensagem");
document.querySelector(".card");
document.querySelectorAll("button");
```

## Eventos comuns

- `click`
- `input`
- `change`
- `submit`
- `keydown`
- `mouseover`

## Formulario com submit

```html
<form id="formulario">
  <input id="nome" />
  <button type="submit">Enviar</button>
</form>
```

```js
const formulario = document.getElementById("formulario");
const nome = document.getElementById("nome");

formulario.addEventListener("submit", function (event) {
  event.preventDefault();
  console.log(nome.value);
});
```

`event.preventDefault()` impede o comportamento padrao do formulario, que seria recarregar a pagina.

## Relacao com React

React tambem lida com eventos e DOM, mas voce normalmente nao manipula o DOM diretamente.

JavaScript puro:

```js
mensagem.innerText = "Texto alterado";
```

React:

```jsx
const [mensagem, setMensagem] = useState("Texto original");
```

Em React, a tela muda como resultado de state.

## Relacionado

- [[Funcoes e Callbacks]]
- [[Conhecimento/Frontend/React/State|State]]

