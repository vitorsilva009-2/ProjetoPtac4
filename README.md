# Sistema de Restaurante

Aplicação front end desenvolvida em **React** para gerenciamento do cardápio de um restaurante, com operações de CRUD sobre duas entidades relacionadas: **Categoria** e **Prato**.

## Resumo do Problema

Muitos restaurantes de pequeno e médio porte ainda controlam o cardápio de forma manual, em papel ou planilhas soltas. Isso gera preços desatualizados, pratos listados mesmo quando estão em falta, dificuldade para organizar os itens por tipo (entradas, bebidas, sobremesas etc.) e retrabalho a cada alteração.

Este sistema resolve esse problema ao centralizar o gerenciamento do cardápio em uma interface web simples. O responsável pelo restaurante consegue cadastrar, consultar, atualizar e remover categorias e pratos, controlar a disponibilidade de cada item e visualizar o cardápio organizado e sempre atualizado.

## Modelo de Dados

Relação **1:N**: uma categoria possui vários pratos, e cada prato pertence a uma única categoria.

### Categoria

| Campo      | Tipo   | Descrição                |
|------------|--------|--------------------------|
| id         | number | Identificador (PK)       |
| nome       | string | Nome da categoria        |
| descricao  | string | Descrição da categoria   |

### Prato

| Campo        | Tipo    | Descrição                              |
|--------------|---------|----------------------------------------|
| id           | number  | Identificador (PK)                     |
| nome         | string  | Nome do prato                          |
| descricao    | string  | Descrição do prato                     |
| preco        | number  | Preço do prato                         |
| disponivel   | boolean | Indica se o prato está disponível      |
| categoriaId  | number  | Chave estrangeira (FK) para Categoria  |

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

## Requisitos Não Funcionais

| Código | Categoria | Requisito |
|--------|-----------|-----------|
| RNF01 | Usabilidade | A interface deve ser simples e intuitiva, permitindo que um usuário sem treinamento realize as operações de CRUD. |
| RNF02 | Responsividade | A aplicação deve se adaptar a diferentes tamanhos de tela (desktop, tablet e celular). |
| RNF03 | Desempenho | As listagens e operações devem responder em até 2 segundos em condições normais de uso. |
| RNF04 | Compatibilidade | A aplicação deve funcionar nas versões atuais dos navegadores Chrome, Firefox, Edge e Safari. |
| RNF05 | Manutenibilidade | O código deve ser organizado em componentes reutilizáveis e em pastas separadas por responsabilidade (`pages/`, `components/`, `services/`). |
| RNF06 | Tecnologia | O front end deve ser desenvolvido em React, com navegação entre páginas via React Router. |
| RNF07 | Persistência | Os dados devem ser mantidos entre sessões, por meio de API fake (json-server) ou localStorage. |
| RNF08 | Confiabilidade | O sistema deve tratar erros de comunicação com a API e exibir mensagens amigáveis em vez de falhar silenciosamente. |
| RNF09 | Acessibilidade | Os formulários devem ter rótulos (`label`) associados aos campos e contraste adequado entre texto e fundo. |
| RNF10 | Consistência visual | A aplicação deve seguir um padrão visual único (cores, fontes e espaçamentos) em todas as telas. |

## Rotas Sugeridas

| Rota          | Descrição                                  |
|---------------|--------------------------------------------|
| `/categorias` | Listagem e gerenciamento de categorias     |
| `/pratos`     | Listagem e gerenciamento de pratos         |
| `/cardapio`   | Visualização do cardápio por categoria     |

## Tecnologias

- React
- React Router DOM
- json-server ou localStorage (persistência dos dados)

## Como Executar

```bash
# Instalar dependências
npm install

# Iniciar a API fake (caso use json-server)
npx json-server --watch db.json --port 3001

# Iniciar a aplicação
npm start
```
