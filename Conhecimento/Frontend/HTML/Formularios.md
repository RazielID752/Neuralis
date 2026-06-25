# Formularios

## O que eu preciso lembrar

Formulario serve para coletar dados do usuario.

Um formulario bom precisa ser claro, acessivel e facil de validar.

## Exemplo bem simples

```html
<form>
  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>

  <button type="submit">Enviar</button>
</form>
```

## O que cada parte faz

- `form`: agrupa campos e envio.
- `label`: texto que explica o campo.
- `for`: conecta label ao input pelo id.
- `input`: campo de entrada.
- `name`: nome usado no envio dos dados.
- `type`: tipo do campo.
- `required`: torna obrigatorio.
- `button type="submit"`: envia o formulario.

## Tipos comuns de input

```html
<input type="text">
<input type="email">
<input type="password">
<input type="number">
<input type="checkbox">
<input type="radio">
```

## Textarea e select

```html
<label for="bio">Bio</label>
<textarea id="bio" name="bio"></textarea>
```

```html
<label for="stack">Stack</label>
<select id="stack" name="stack">
  <option value="react">React</option>
  <option value="vue">Vue</option>
</select>
```

## Pegadinhas

- Input sem label.
- Botao sem `type`.
- Usar placeholder como se fosse label.
- Nao mostrar mensagem de erro.
- Nao indicar campo obrigatorio.

## Como isso aparece em React

Em React, o input normalmente vira controlado por state:

```tsx
const [email, setEmail] = useState("");

<input
  value={email}
  onChange={(event) => setEmail(event.target.value)}
/>;
```

## Resumo mental

Formulario e conversa com o usuario. Label explica, input recebe, erro orienta, botao envia.

## Exercicios para fixar

1. Crie um formulario com nome e email.
2. Adicione labels corretos.
3. Adicione um campo obrigatorio.
4. Crie uma mensagem de erro simples.

## Relacionado

- [[Acessibilidade em HTML]]
- [[Conhecimento/Frontend/React/Forms em React|Forms em React]]

