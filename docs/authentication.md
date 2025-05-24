---
sidebar_position: 2
---
# Autenticação

Nossa API utiliza JWT (JSON Web Token) para autenticação, garantindo segurança e controle em cada requisição. Abaixo, explicamos como obter o token JWT e como utilizá-lo nas chamadas para os endpoints protegidos.

## Como funciona?

1. **Obtenha o Token JWT**

Para autenticar-se, envie uma requisição para o endpoint `/auth/signin`, fornecendo as credenciais necessárias:

- **Email e senha** no corpo da requisição **(body)**;
- Ou, alternativamente, forneça a sua **API Key** no cabeçalho (header) da requisição como `api-key`.

2. **Utilize o Token JWT nas Requisições**

Após receber o token, inclua-o no cabeçalho de todas as requisições para endpoints protegidos no formato:

```
Authorization: Bearer <seu-token-jwt>
```

## Endpoint de Autenticação

| Método | Endpoint       | Descrição                          |
|--------|----------------|------------------------------------|
| POST   | `/auth/signin` | Gera o token JWT para autenticação |

## Exemplo de Requisição

### Requisição com Email e Senha:

```http
POST /auth/signin HTTP/1.1
Host: sua-api.com
Content-Type: application/json

{
  "email": "usuario@exemplo.com",
  "password": "sua_senha"
}
```

### Requisição com API Key:

```http
POST /auth/signin HTTP/1.1
Host: sua-api.com
api-key: SUA_API_KEY
Content-Type: application/json
```

## Exemplo de Resposta

Se a autenticação for bem-sucedida, o servidor retornará uma resposta como esta:

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

O valor do campo `token` é o JWT que deverá ser usado nas próximas requisições.

