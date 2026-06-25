# OOP no Frontend

## O que eu preciso lembrar

Frontend moderno usa muita função e composição, mas OOP ainda aparece.

## Onde OOP aparece

- classes JavaScript;
- instancias de bibliotecas;
- serviços;
- SDKs;
- Error customizado;
- models de domínio em projetos maiores.

## Exemplo de Error customizado

```ts
class ApiError extends Error {
  constructor(
    message: string,
    public status: number
  ) {
    super(message);
  }
}
```

Uso:

```ts
throw new ApiError("Nao autorizado", 401);
```

## Exemplo de serviço

```ts
class UsersService {
  async getUsers() {
    const response = await fetch("/api/users");
    return response.json();
  }
}
```

## Quando usar OOP

- estado interno controlado;
- instancia com configuração;
- integração com biblioteca;
- domínio com comportamento forte.

## Quando evitar

- transformações simples;
- componentes React comuns;
- função pura resolveria melhor;
- classe só para agrupar funções.

## Resumo mental

OOP é útil, mas no frontend eu misturo com funções e composição.

## Relacionado

- [[Clean Architecture]]
- [[Composicao vs Heranca]]

