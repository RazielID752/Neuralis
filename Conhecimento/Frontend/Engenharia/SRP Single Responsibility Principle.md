# SRP: Single Responsibility Principle

## O que eu preciso lembrar

Uma unidade de codigo deve ter uma responsabilidade principal.

No frontend, isso vale para:

- funcao;
- componente;
- hook;
- arquivo;
- feature.

## Explicando do zero

Se um componente busca API, transforma dados, controla modal, valida formulario e renderiza tabela, ele tem motivos demais para mudar.

Cada motivo para mudar aumenta chance de quebrar algo.

## Exemplo ruim

```tsx
function UsersPage() {
  const [users, setUsers] = useState<User[]>([]);
  const [search, setSearch] = useState("");
  const [isModalOpen, setIsModalOpen] = useState(false);

  useEffect(() => {
    fetch("/api/users")
      .then((response) => response.json())
      .then(setUsers);
  }, []);

  const filteredUsers = users.filter((user) =>
    user.name.toLowerCase().includes(search.toLowerCase())
  );

  return (
    <main>
      <input value={search} onChange={(event) => setSearch(event.target.value)} />
      <button onClick={() => setIsModalOpen(true)}>Novo usuario</button>
      {filteredUsers.map((user) => (
        <div key={user.id}>{user.name}</div>
      ))}
      {isModalOpen && <div>Modal</div>}
    </main>
  );
}
```

Esse componente faz muitas coisas.

## Melhorando

Separar:

- `users-api.ts`: buscar usuarios;
- `use-users.ts`: controlar dados;
- `filter-users.ts`: filtrar;
- `users-list.tsx`: renderizar lista;
- `create-user-modal.tsx`: modal.

## Exemplo de regra separada

```ts
export function filterUsers(users: User[], search: string) {
  const normalizedSearch = search.trim().toLowerCase();

  if (!normalizedSearch) {
    return users;
  }

  return users.filter((user) =>
    user.name.toLowerCase().includes(normalizedSearch)
  );
}
```

## Como identificar violacao de SRP

Pergunto:

- quantas coisas esse arquivo faz?
- quantos motivos ele tem para mudar?
- o nome dele explica tudo que ele faz?
- tem comentario separando blocos de responsabilidade?

## Pegadinhas

- Separar demais e deixar o fluxo dificil.
- Achar que SRP significa uma função de uma linha.
- Criar abstração antes de entender a responsabilidade.

## Resumo mental

SRP e diminuir motivos para mudar.

## Relacionado

- [[Separacao de Responsabilidades]]
- [[Clean Code]]

