---
sidebar_position: 1
---

# Listar notificações

Com o endpoint de listagem, você pode consultar todas as notificações criadas em sua conta. É possível utilizar parâmetros para paginação e filtragem por status, garantindo uma consulta eficiente e personalizada.

Nosso método de paginação é baseado no conceito de paginação infinita. Nesse modelo, o parâmetro `page` recebe um registro codificado em base64 que aponta para a próxima página. Isso permite uma navegação contínua sem a necessidade de números fixos de página

## Endpoint para Listar Notificações

| Método | Endpoint         | Descrição                                  |
| ------ | ---------------- | ------------------------------------------ |
| GET    | `/notifications` | Retorna uma lista de notificações criadas. |

## Parâmetros de Consulta

| Parâmetro | Tipo     | Obrigatório | Descrição                                                                           |
| --------- | -------- | ----------- | ----------------------------------------------------------------------------------- |
| `page`    | `string` | Não         | Registro codificado em base64 para acessar a próxima página. O padrão é `null`.     |
| `status`  | `string` | Não         | Filtra notificações por status. Valores possíveis: `created`, `notified`, `failed`. |

## Exemplo de Requisição

### Sem Parâmetros

```http
GET /notifications HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

### Com Parâmetros

```http
GET /notifications?page=eyJwYWdlIjoxLCJsaW1pdCI6MjB9&status=notified HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

## Exemplo de Resposta

```json
{
  "nextPage": null,
  "notifications": [
    {
      "id": "01JVW1SP3D429M50M5MEGYQQ3N",
      "accountId": "01JVF6DEK1J669P4TP2RGDSRY5",
      "payload": {
        "ok": true
      },
      "status": "NOTIFIED",
      "notificationDate": "2025-05-22T10:11:00.000Z",
      "destination": "https://webhook.site/c0bc7fda-9133-482c-b16e-6791ba99ce48",
      "createdAt": "2025-05-22T13:09:22.157Z",
      "updatedAt": "2025-05-22T13:11:36.927Z"
    }
  ]
}
```

:::tip
Quando o campo `nextPage` vier preenchido, envie-o na próxima requisição para acessa a próxima página.
:::

## Campos Retornados

| Campo           | Tipo     | Descrição                                                   |
| --------------- | -------- | ----------------------------------------------------------- |
| `page`          | `string` | Token base64 que representa a próxima página de resultados. |
| `notifications` | `array`  | Lista de notificações retornadas na página atual.           |

## Cuidados Importantes

- **Paginação infinita**

O parâmetro `page` funciona como um ponteiro para a próxima página de resultados. Utilize o valor retornado na resposta anterior para continuar navegando pelos registros.

- **Filtro por status**

Utilize o parâmetro status para encontrar notificações específicas de acordo com o estado atual.