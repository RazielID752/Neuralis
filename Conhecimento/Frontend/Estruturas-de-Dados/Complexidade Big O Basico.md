# Complexidade Big O Basico

## O que eu preciso lembrar

Big O e uma forma de pensar quanto o custo cresce quando a quantidade de dados aumenta.

Nao preciso virar matematico. Preciso entender o basico para nao fazer codigo muito lento sem perceber.

## O(1): constante

Buscar em objeto por chave:

```ts
const user = usersById[id];
```

O custo nao cresce muito com o tamanho.

## O(n): linear

Percorrer lista:

```ts
const user = users.find((user) => user.id === id);
```

Se tem mais itens, pode demorar mais.

## O(n²): dois loops

```ts
for (const user of users) {
  for (const post of posts) {
    // compara
  }
}
```

Pode crescer rapido e ficar pesado.

## Exemplo pratico

Se eu preciso buscar usuario por id muitas vezes:

Ruim:

```ts
function getUserName(userId: string, users: User[]) {
  return users.find((user) => user.id === userId)?.name;
}
```

Melhor criar mapa:

```ts
const usersById = new Map(users.map((user) => [user.id, user]));

function getUserName(userId: string) {
  return usersById.get(userId)?.name;
}
```

## Pegadinhas

- Otimizar antes de precisar.
- Ignorar listas grandes.
- Fazer `find` dentro de `map` sem perceber.

## Resumo mental

Big O me ajuda a perceber quando meu codigo vai piorar com muitos dados.

## Relacionado

- [[Array]]
- [[Map]]

