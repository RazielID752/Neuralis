# Dark Mode no Tailwind

## O que eu preciso lembrar

Dark mode no Tailwind normalmente usa a variante `dark:`.

## Exemplo

```html
<div class="bg-white text-black dark:bg-black dark:text-white">
  Conteudo
</div>
```

## Por classe

Muitos projetos ativam dark mode adicionando `class="dark"` no `html`.

```html
<html class="dark">
```

## Pegadinhas

- Esquecer contraste no modo escuro.
- Ajustar fundo e esquecer borda.
- Ajustar texto e esquecer ícones.
- Misturar cores fixas fora do tema.

## Resumo mental

Dark mode nao e inverter cor. E criar outro estado visual legivel.

## Relacionado

- [[Tema e Configuracao do Tailwind]]

