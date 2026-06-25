# Separacao de Responsabilidades

## O que eu preciso lembrar

Cada parte do codigo deveria ter um trabalho claro.

Quando uma coisa faz tudo, ela fica dificil de mudar.

## Exemplo de responsabilidades

- componente: renderizar UI;
- hook: organizar logica reutilizavel de React;
- funcao utilitaria: transformar dado;
- camada de API: buscar/enviar dados;
- schema: validar formato;
- tipo: descrever dado;
- pagina: compor a tela.

## Exemplo ruim

```tsx
function UserPage() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("/api/users")
      .then((response) => response.json())
      .then((data) => setUsers(data));
  }, []);

  return <div>{users.length}</div>;
}
```

Funciona, mas mistura:

- tela;
- busca de dados;
- estado;
- tratamento de resposta.

## Melhorando

```ts
async function getUsers() {
  const response = await fetch("/api/users");
  return response.json();
}
```

```tsx
function UserPage() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    getUsers().then(setUsers);
  }, []);

  return <div>{users.length}</div>;
}
```

Ainda simples, mas a chamada de API saiu do componente.

## Pegadinhas

- Separar demais e dificultar leitura.
- Separar de menos e criar componente enorme.
- Colocar regra de negocio dentro de componente visual.
- Colocar fetch em varios lugares repetidos.

## Resumo mental

Se eu nao consigo explicar o trabalho de um arquivo em uma frase, talvez ele esteja fazendo coisa demais.

## Relacionado

- [[Camada de API]]
- [[Organizacao de Pastas]]

