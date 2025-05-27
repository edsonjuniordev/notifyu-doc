---
sidebar_position: 1
---

# Criar chave de API

As chaves de API são essenciais para autenticar e autorizar o acesso aos recursos da nossa API. Você pode criar uma nova chave de API de duas maneiras: pelo painel ou diretamente por meio de um endpoint da API. Abaixo, explicamos ambos os métodos.

## Criando pelo Painel

1. **Acesse o painel de administração**

Faça login na sua conta e navegue até a seção de gerenciamento de chaves de API.

2. **Inicie a criação**

Clique no botão **"Criar Nova Chave"**.

3. **Confirme e salve**

Após configurar a chave, clique em **"Salvar"**. A nova chave será gerada e exibida.

:::danger Atenção!

A chave será exibida apenas uma vez. Certifique-se de copiá-la e armazená-la em um local seguro.

:::

## Criando pela API

Também é possível criar uma chave de API utilizando nosso endpoint dedicado. Este método é ideal para integrações ou automações.

### Endpoint de Criação

| Método | Endpoint    | Descrição                  |
| ------ | ----------- | -------------------------- |
| POST   | `/api-keys` | Cria uma nova chave de API |

### Exemplo de Requisição

```http
POST /api-keys HTTP/1.1
Authorization: Bearer <seu-token-jwt>
Content-Type: application/json
```

### Exemplo de Resposta

```json
{
  "apiKey": "01JVAQRP91MNXS1X12D38DT92Y"
}
```

## Cuidados Importantes

- **Proteja suas chaves**

Nunca exponha sua chave de API em repositórios públicos ou outros locais não seguros.

- **Deleção de chaves**

Se você suspeitar que uma chave foi comprometida, [delete-a](./delete-api-key.md) imediatamente e crie uma nova