# Checkpoint 1 - API de Pedidos com Spring Boot

Nome: Gustavo Ferreira Lopes
rm: 98887

## Descrição

Este projeto consiste em uma API REST desenvolvida com Spring Boot para gerenciar pedidos de clientes. A API permite cadastrar, consultar, atualizar e remover pedidos, seguindo os princípios da arquitetura orientada a serviços (SOA). O banco de dados utilizado é o H2, que roda em memória para facilitar os testes.

## Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Lombok
- H2 Database

## Funcionalidades

- Criar um novo pedido
- Listar todos os pedidos
- Buscar um pedido pelo ID
- Atualizar um pedido existente
- Remover um pedido

## Como Executar

1. Clone este repositório.
2. Importe o projeto em sua IDE favorita.
3. Instale as dependecias no diretório onde está o pom.xml /checkpoint1

```
mvn clean install
```

4. Execute a aplicação como um projeto Spring Boot.

```
mvn spring-boot:run
```

5. Utilize o Postman ou outra ferramenta similar para testar os endpoints.

## Autor

Este projeto foi desenvolvido como parte de um checkpoint da disciplina de Arquitetura SOA e Web Services.

## API de Pedidos – `PedidoController`

Base URL: `http://localhost:8080/pedidos`

---

### 🔹 `GET /pedidos`

**Descrição:** Lista todos os pedidos cadastrados.

**Resposta:**

```json
[
  {
    "id": 1,
    "clienteNome": "João da Silva",
    "dataPedido": "2025-03-27",
    "valorTotal": 199.99
  },
  ...
]
```

---

### 🔹 `GET /pedidos/{id}`

**Descrição:** Retorna os dados de um pedido específico, com base no ID.

**Parâmetros de URL:**

- `id` (Long): ID do pedido que deseja buscar.

**Exemplo de resposta:**

```json
{
  "id": 1,
  "clienteNome": "João da Silva",
  "dataPedido": "2025-03-27",
  "valorTotal": 199.99
}
```

---

### 🔹 `POST /pedidos`

**Descrição:** Cria um novo pedido.

**Corpo da requisição (JSON):**

```json
{
  "clienteNome": "João da Silva",
  "valorTotal": 299.9
}
```

> `dataPedido` será definido automaticamente como a data atual.  
> `id` será gerado automaticamente.

**Exemplo de resposta:**

```json
{
  "id": 2,
  "clienteNome": "João da Silva",
  "dataPedido": "2025-03-27",
  "valorTotal": 299.9
}
```

---

### 🔹 `PUT /pedidos/{id}`

**Descrição:** Atualiza os dados de um pedido existente.

**Parâmetros de URL:**

- `id` (Long): ID do pedido a ser atualizado.

**Corpo da requisição (JSON):**

```json
{
  "clienteNome": "Maria Oliveira",
  "valorTotal": 150.0
}
```

**Exemplo de resposta:**

```json
{
  "id": 2,
  "clienteNome": "Maria Oliveira",
  "dataPedido": "2025-03-27",
  "valorTotal": 150.0
}
```

---

### 🔹 `DELETE /pedidos/{id}`

**Descrição:** Deleta um pedido com base no ID.

**Parâmetros de URL:**

- `id` (Long): ID do pedido que deseja excluir.
