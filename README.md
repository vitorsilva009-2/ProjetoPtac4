# ProjetoPtac4
Projeto de PTAS4


# Sistema de Restaurante

Aplicação front end desenvolvida em **React** para gerenciamento do cardápio de um restaurante, com operações de CRUD sobre duas entidades relacionadas: **Categoria** e **Prato**.



## Requisitos Funcionais

### CRUD de Categorias

| Código | Requisito |
|--------|-----------|
| RF01 | O sistema deve permitir cadastrar uma nova categoria (nome e descrição). |
| RF02 | O sistema deve listar todas as categorias cadastradas. |
| RF03 | O sistema deve permitir editar os dados de uma categoria existente. |
| RF04 | O sistema deve permitir excluir uma categoria, impedindo a exclusão caso existam pratos vinculados a ela (ou exibindo aviso de confirmação). |

### CRUD de Pratos

| Código | Requisito |
|--------|-----------|
| RF05 | O sistema deve permitir cadastrar um prato (nome, descrição, preço e disponibilidade), obrigatoriamente vinculado a uma categoria existente. |
| RF06 | O sistema deve listar todos os pratos, exibindo o nome da categoria a que cada um pertence. |
| RF07 | O sistema deve permitir editar os dados de um prato, inclusive alterar sua categoria. |
| RF08 | O sistema deve permitir excluir um prato, solicitando confirmação antes da exclusão. |

### Funcionalidades Complementares

| Código | Requisito |
|--------|-----------|
| RF09 | O sistema deve permitir filtrar a lista de pratos por categoria. |
| RF10 | O sistema deve permitir buscar pratos pelo nome. |
| RF11 | O sistema deve validar os formulários (campos obrigatórios e preço maior que zero) e exibir mensagens de erro claras. |
| RF12 | O sistema deve permitir marcar um prato como disponível ou indisponível sem precisar editá-lo por completo. |
| RF13 | O sistema deve exibir mensagens de feedback (sucesso ou erro) após cada operação de criar, editar ou excluir. |
| RF14 | O sistema deve exibir o cardápio organizado por categoria, mostrando apenas os pratos disponíveis. |

## Rotas 

| Rota          | Descrição                                  |
|---------------|--------------------------------------------|
| `/categorias` | Listagem e gerenciamento de categorias     |
| `/pratos`     | Listagem e gerenciamento de pratos         |
| `/cardapio`   | Visualização do cardápio por categoria     |



