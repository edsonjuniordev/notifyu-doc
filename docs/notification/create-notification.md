---
sidebar_position: 1
---

# Criar Notificação

A criação de notificações é um dos principais recursos da nossa API. Com essa funcionalidade, você pode configurar notificações personalizadas para serem enviadas aos destinatários no momento desejado. Este processo é realizado por meio de um endpoint dedicado da API.

## Endpoint para Criar Notificação

| Método | Endpoint         | Descrição                 |
| ------ | ---------------- | ------------------------- |
| POST   | `/notifications` | Cria uma nova notificação |

## Exemplo de Requisição

```http
POST /notifications HTTP/1.1
Authorization: Bearer <seu-token-jwt>
Content-Type: application/json

{
  "payload": {
    "ok": true
  },
  "notificationDate": "2025-05-22T10:00:00.000Z",
  "destination": "https://webhook.site/c0bc7fda-9133-482c-b16e-6791ba99ce48",
  "notificationType": "HTTP"
}
```

## Parâmetros do Body

| Parâmetro          | Tipo     | Obrigatório | Descrição                                                              |
| ------------------ | -------- | ----------- | ---------------------------------------------------------------------- |
| `payload`          | `object` | Sim         | O payload que será enviado no momento da notificação.                  |
| `notificationDate` | `string` | Sim         | A data da notificação no formato ISO 8601.                             |
| `destination`      | `string` | Sim         | O webhook de destino que receberá a notificação.                       |
| `notificationType` | `string` | Sim         | O tipo de notificação que será enviada (No momento existe apenas HTTP) |

## Exemplo de Resposta

```json
{
  "id": "01JVW1T773ZJV597BG2KHTYD3X",
  "accountId": "01JVF6DEK1J669P4TP2RGDSRY5",
  "payload": {
    "ok": true
  },
  "status": "CREATED",
  "notificationDate": "2025-05-22T10:11:00.000Z",
  "destination": "https://webhook.site/c0bc7fda-9133-482c-b16e-6791ba99ce48",
  "notificationType": "HTTP",
  "createdAt": "2025-05-22T13:09:39.683Z",
  "updatedAt": "2025-05-22T13:09:39.683Z"
}
```

## Cuidados Importantes

- **Validação de dados**

Certifique-se de fornecer valores válidos para os parâmetros obrigatórios.