---
sidebar_position: 3
---

# Cancelar notificação

O endpoint para cancelar uma notificação permite que você interrompa o envio de uma notificação antes que ela seja processada. Este recurso é ideal para cenários em que a notificação foi criada por engano ou não é mais necessária.

Ao cancelar uma notificação, ela será marcada como cancelada e não será mais enviada. Além disso, o valor da notificação será automaticamente ressarcido para o usuário.

## Endpoint para Cancelar uma Notificação

| Método | Endpoint              | Descrição                           |
| ------ | ----------------------| ----------------------------------- |
| DELETE | `/notifications/:id`  | Cancela uma notificação específica. |

## Parâmetros de Rota

| Parâmetro | Tipo     | Obrigatório | Descrição                                               |
| --------- | -------- | ----------- | ------------------------------------------------------- |
| `id`      | `string` | Sim         | Identificador único da notificação que deseja cancelar. |

## Exemplo de Requisição

```http
DELETE /notifications/12345 HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

## Exemplo de Resposta

A API retorna apenas um status code `204`.

## Observações Importantes

- Quando uma notificação é cancelada, ela não será enviada e o valor correspondente será ressarcido automaticamente para o usuário.
- Somente notificações com status `created` podem ser canceladas. Se a notificação já tiver sido enviada, o cancelamento não será permitido.