---
sidebar_position: 1
---

# Buscar uma conta

O endpoint para buscar uma conta permite que você obtenha informações detalhadas sobre uma conta específica em sua aplicação. Esse recurso é útil para visualizar dados como quantidade de notificações disponíveis e outras informações relevantes associadas à conta.

## Endpoint para Buscar uma Conta

| Método | Endpoint        | Descrição                                    |
| ------ | --------------- | -------------------------------------------- |
| GET    | `/accounts`     | Retorna os detalhes de uma conta específica. |

## Exemplo de Requisição

```http
GET /accounts HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

## Exemplo de Resposta

```json
{
  "id": "01JW9RM5DFDVJ611GVY4JGERWU",
  "name": "John Doe",
  "email": "john@doe.com",
  "document": "12345678910",
  "httpNotificationQuantity": 100,
  "createdAt": "2025-05-27T20:58:26.095Z"
}
```

## Observações

- Certifique-se de passar um token JWT válido no cabeçalho da requisição para autenticação.