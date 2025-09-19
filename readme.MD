# API de ticket de suporte

## Sobre

API para gerenciar ticket de suporte técnico, permitindo criar um ticket solicitando suporte, atualizar as informações do ticket, listar os tickets podendo filtrar pelo status e atualizar o status de um ticket fechado.

---

## Rotas

- Criar Ticket:

  - Método: POST
  - URL: /tickets
  - Dados:
    - equipment (string, obrigatório): nome do equipamento (exemplo: computador).
    - description (string, obrigatório): descrição do problema.
    - user_name (string, obrigatório): nome do usuário que está criando o ticket.

- Obter Tickets:

  - Método: GET
  - URL: /tickets
  - Descrição: obtém uma lista de todos os tickets de suporte.
  - Parâmetros de Consulta (Query Parameters):
    - status (string, opcional): filtra os tickets pelo status ("open" ou "closed")

- Atualizar Ticket

  - Método: PUT
  - URL: /tickets/:id
  - Descrição: atualiza as informações de um ticket específico.
  - Parâmetros de rota:
    - id (UUID, obrigatório): ID do ticket.
  - Parâmetros no Corpo (JSON):
    - equipment (string, obrigatório): nome do equipamento (exemplo: computador)
    - description (string, obrigatório): descrição do problema.
    - user_name não altera.

- Fechar Ticket

  - Método: PATCH
  - URL: /tickets/:id/status
  - Descrição: atualiza as informações de um ticket específico.
  - Parâmetros de Rota:
    - id (UUID, obrigatório): ID do ticket.

- Excluir Ticket
  - Método: DELETE
  - URL: /tickets/:id
  - Descrição: exclui um ticket específico pelo seu ID.
  - Parâmetros de Rota:
    - id (UUID, obrigatório): ID do ticket

---

### Att: monwire
