# React

## O que eu preciso lembrar

React e uma forma de construir tela com componentes.

Eu penso em React assim:

- componente e um pedaco da interface;
- props sao dados que entram;
- state e memoria local;
- eventos mudam state;
- a UI e recalculada a partir de props e state.

## Como eu vou estudar React

React fica mais facil quando eu nao tento aprender tudo junto.

O caminho e:

1. JSX;
2. componentes;
3. props;
4. state;
5. eventos;
6. condicionais;
7. listas;
8. forms;
9. effects;
10. hooks e composicao.

## Guia principal

- [[React do Zero ao Avancado]]

## Ordem recomendada

### 1. Base

- [[JSX]]
- [[Componentes]]
- [[Props]]

Objetivo: criar componentes e passar dados.

### 2. Interacao

- [[State]]
- [[Eventos em React]]
- [[Renderizacao Condicional]]
- [[Listas e Keys]]

Objetivo: fazer a tela mudar conforme dados e acoes do usuario.

### 3. Formularios e efeitos

- [[Forms em React]]
- [[useEffect]]

Objetivo: controlar inputs e sincronizar com coisas fora do React.

### 4. Organizacao

- [[Hooks]]
- [[Hooks Customizados]]
- [[useReducer]]
- [[Context API]]
- [[Composicao em React]]

Objetivo: organizar logica e UI sem criar componentes gigantes.

## Perguntas que eu sempre devo fazer

- Esse dado vem de props ou state?
- Quem precisa desse state?
- Esse componente esta fazendo coisa demais?
- Esse `useEffect` e realmente necessario?
- Essa lista tem `key` estavel?
- Esse input esta controlado?

## Pegadinhas grandes de React

- Criar state para valor que pode ser calculado.
- Usar `useEffect` para tudo.
- Usar indice como key em lista que muda.
- Mutar array/objeto direto no state.
- Passar props demais porque faltou composicao.

## Resumo mental

React e sobre descrever a tela a partir de dados. Quando os dados mudam, React redesenha o que precisa.
