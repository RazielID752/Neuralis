# Grid

## O que eu preciso lembrar

Grid organiza layout em linhas e colunas.

Se Flexbox e bom para uma direcao, Grid e bom para duas dimensoes.

## Exemplo simples

```css
.layout {
  display: grid;
  grid-template-columns: 240px 1fr;
  gap: 24px;
}
```

Isso cria:

- uma coluna fixa de `240px`;
- uma coluna que ocupa o resto (`1fr`);
- espaco de `24px`.

## Cards responsivos

```css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}
```

Esse padrao cria cards que se adaptam ao tamanho da tela.

## Propriedades que eu mais uso

```css
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 16px;
align-items: start;
```

## Quando usar

- Dashboard.
- Galeria.
- Layout de pagina.
- Cards responsivos.
- Estrutura com sidebar e conteudo.

## Pegadinhas

- Usar grid para alinhamento simples que flex resolveria.
- Criar coluna fixa que quebra no mobile.
- Esquecer `gap`.

## Resumo mental

Grid e para desenhar a estrutura maior da tela.

## Exercicios para fixar

1. Crie grid de 3 colunas.
2. Crie layout com sidebar.
3. Crie cards responsivos com `auto-fit`.

## Relacionado

- [[Flexbox]]
- [[Responsividade]]

