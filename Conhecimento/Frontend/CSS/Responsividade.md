# Responsividade

## O que eu preciso lembrar

Responsividade e fazer a interface funcionar bem em telas diferentes.

Nao e so "caber no celular". Precisa continuar legivel e usavel.

## Mobile first

Escrevo primeiro o estilo base para telas pequenas.

```css
.cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}
```

Depois aumento:

```css
@media (min-width: 768px) {
  .cards {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

## Layout fluido

Evito largura fixa demais.

```css
.container {
  width: min(100% - 32px, 1120px);
  margin-inline: auto;
}
```

## Imagens responsivas

```css
img {
  max-width: 100%;
  height: auto;
}
```

## Pegadinhas

- Fazer desktop primeiro e tentar remendar mobile.
- Usar `width: 1200px` sem limite responsivo.
- Texto pequeno demais no celular.
- Botao dificil de tocar.
- Esquecer espaco lateral.

## Resumo mental

Responsivo e pensar em fluidez: largura flexivel, layout adaptavel e texto legivel.

## Exercicios para fixar

1. Crie uma grid que vira 3 colunas em telas maiores.
2. Crie um container com largura maxima.
3. Teste uma imagem grande dentro de uma tela pequena.

## Relacionado

- [[Grid]]
- [[Design Responsivo com Tailwind]]

