---
sidebar_position: 3
---

# Deletar chave de API

Caso uma chave de API não seja mais necessária ou tenha sido comprometida, você pode excluí-la para garantir a segurança da sua conta. A exclusão de uma chave pode ser feita tanto pelo painel administrativo quanto por meio de um endpoint da API

## Deletando pelo Painel

1. **Acesse o painel de administração**

Faça login na sua conta e vá até a seção de gerenciamento de chaves de API.

2. **Localize a chave que deseja excluir**

Encontre na lista a chave que deseja deletar.

3. **Exclua a chave**

Clique no botão **"Excluir"** ou no ícone correspondente e confirme a exclusão.

:::danger Atenção!
Após excluir uma chave, ela será permanentemente removida e não poderá ser recuperada.
:::

## Deletando pela API

Para maior flexibilidade, você pode excluir uma chave diretamente pelo endpoint da API.

### Endpoint para Deletar Chaves

| Método | Endpoint            | Descrição                       |
| ------ | ------------------- | ------------------------------- |
| DELETE | `/api-keys/{keyId}` | Exclui uma chave de API pelo ID |

### Exemplo de Requisição

```http
DELETE /api-keys/key_1 HTTP/1.1
Authorization: Bearer <seu-token-jwt>
```

### Exemplo de Resposta

A API retorna apenas um status code `204`.

## Cuidados Importantes

- **Revogação imediata**

Exclua imediatamente qualquer chave de API comprometida para evitar acessos não autorizados.

- **Gerenciamento de chaves**

Certifique-se de que a chave a ser deletada não está mais em uso por nenhum sistema ou integração.