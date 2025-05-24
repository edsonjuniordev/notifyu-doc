---
sidebar_position: 2
---

# Listar chaves de API

Nossa API permite que você visualize todas as chaves de API associadas à sua conta. Isso pode ser feito tanto pelo painel quanto por meio de um endpoint da API. Abaixo, explicamos como realizar essa ação em ambas as opções

## Listando pelo Painel

1. **Acesse o painel de administração**

Faça login na sua conta e vá até a seção de gerenciamento de chaves de API.

2. **Visualize suas chaves**

Na página de gerenciamento, você verá uma lista de todas as chaves de API criadas.

3. **Gerencie suas chaves**

Caso necessário, você pode excluir chaves diretamente no painel.

## Listando pela API

Para integrações automáticas, você pode listar as chaves de API utilizando o endpoint dedicado.

### Endpoint para Listar Chaves

| Método | Endpoint    | Descrição                          |
| ------ | ----------- | ---------------------------------- |
| GET    | `/api-keys` | Retorna uma lista de chaves de API |

### Exemplo de Requisição

```http
GET /api-keys HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

### Exemplo de Resposta

```json
{
  "apiKeys": [
    {
      "id": "01JVAQRP9140RXCJKYS0GPCD9F",
      "apiKey": "01JVAQRP91MNX*************"
    }
  ]
}
```

## Cuidados Importantes

- **Gerenciamento de chaves**

Verifique periodicamente suas chaves de API e remova aquelas que não estão mais em uso.

- **Segurança**

Certifique-se de que apenas usuários autorizados tenham acesso às informações sobre as chaves.