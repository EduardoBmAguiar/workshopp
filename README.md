# Work Shop
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
[![Licence](https://img.shields.io/github/license/Ileriayo/markdown-badges?style=for-the-badge)](./LICENSE)

# Sobre o projeto

Este **workshop** é um projeto desenvolvido em **Spring Boot** durante meus estudos pessoais, por meio do curso **Java COMPLETO: Programação Orientada a Objetos, UML, JDBC, Spring Boot, JPA, Hibernate e MySQL**.

A aplicação consiste em um sistema de gerenciamento de pedidos, utilizando o banco de dados **H2**. A estrutura do projeto é composta por entidades como **Categoria**, **Pedido**, **Item de Pedido**, **Produto**, **Pagamento** e **Usuário**. 

A relação entre essas entidades pode ser resumida da seguinte forma:

- O **Usuário** realiza um **Pedido**.
- Um **Pedido** contém um **Pagamento** e está associado a um ou mais **Produtos**.
- A ligação entre **Produto** e **Pedido** é feita por meio do **Item de Pedido**.
- Cada **Produto** pertence a uma ou mais **Categorias**.

## Modelo conceitual
![Modelo Conceitual](https://github.com/Duduzzinxxz/assets/blob/main/Modelo-conceitual.png)

# Tecnologias utilizadas
## Back end
- Java
- Spring Boot
- JPA / Hibernate
- Maven
- Postman

## Implantação em produção
- Banco de dados (test profile): [H2 Database](https://www.h2database.com/html/tutorial.html)
- Banco de dados (dev profile): [PostgreSQL](https://www.postgresql.org/download/)

# Como executar o projeto

### Pré-requisitos
- Java [11, 17 ou 21](https://www.oracle.com/java/technologies/downloads/#jdk21-windows)

---
### Passos para Configurar e Executar o Projeto

1. **Clonar o Repositório**  
   Primeiro, clone o repositório do projeto usando o comando abaixo:  
   ```bash
   git clone https://github.com/Duduzzinxxz/workshopp.git
   ```

2. **Acessar a Pasta do Projeto**  
   Entre na pasta do projeto chamada `study`:  
   ```bash
   cd study
   ```

3. **Executar o Projeto**  
   Para rodar a aplicação, utilize o seguinte comando:  
   ```bash
   ./mvnw spring-boot:run
   ```

4. **Acessar o Banco de Dados H2**  
   Abra o navegador e, na barra de pesquisa, digite:  
   ```
   localhost:8080/h2-console/
   ```

5. **Fazer Login no Banco de Dados**  
   Na tela de login do H2, insira os seguintes dados:  
   - **JDBC URL:** `jdbc:h2:mem:testdb`  
   - **User Name:** `sa`  
   - **Password:** (deixe em branco)  

   Clique em **Connect** para acessar o banco de dados.

---

# API Endpoints

## Users

### Listar todos os usuários (GET)
```bash
GET | http://localhost:8080/users
```
#### Exemplo da resposta:
``` json
[
    {
        "id": 1,
        "name": "Maria Brown",
        "email": "maria@gmail.com",
        "phone": "988888888",
        "password": "123456"
    },
    {
        "id": 2,
        "name": "Alex Green",
        "email": "alex@gmail.com",
        "phone": "977777777",
        "password": "123456"
    }
]
```

### Obter um usuário por ID (GET)

```bash
GET | http://localhost:8080/users/1
```
#### Exemplo da resposta:
``` json
{
    "id": 1,
    "name": "Maria Brown",
    "email": "maria@gmail.com",
    "phone": "988888888",
    "password": "123456"
}
```

### Criar um novo usuário (POST)
```bash
POST | http://localhost:8080/users
```
#### Exemplo da requisição:
``` json
{
 "name": "Bob Brown",
 "email": "bob@gmail.com",
 "phone": "977557755",
 "password": "123456"
}
```

### Atualizar um usuário existente (PUT)
```bash
PUT | http://localhost:8080/users/1
```
#### Exemplo da requisição:
``` json
{
 "name": "Bob Brown",
 "email": "bob@gmail.com",
 "phone": "977557755"
}
```

### Excluir um usuário (DELETE)
```bash
DELETE | http://localhost:8080/users/3
```

## Orders

### Listar todos os pedidos (GET)
```bash
GET | http://localhost:8080/orders
```

### Obter um pedido por ID (GET)
```bash
GET | http://localhost:8080/orders/1
```
#### Exemplo de resposta:
``` json
{
    "id": 1,
    "moment": "2019-06-20T19:53:07Z",
    "orderStatus": "PAID",
    "client": {
        "id": 1,
        "name": "Eduardo",
        "email": "bob@gmail.com",
        "phone": "977557755",
        "password": "123456"
    },
    "items": [
        {
            "quantity": 2,
            "price": 90.5,
            "subTotal": 181.0,
            "product": {
                "id": 1,
                "name": "The Lord of the Rings",
                "description": "Lorem ipsum dolor sit amet, consectetur.",
                "price": 90.5,
                "imgUrl": "",
                "categories": [
                    {
                        "id": 2,
                        "name": "Books"
                    }
                ]
            }
        },
        {
            "quantity": 1,
            "price": 1250.0,
            "subTotal": 1250.0,
            "product": {
                "id": 3,
                "name": "Macbook Pro",
                "description": "Nam eleifend maximus tortor, at mollis.",
                "price": 1250.0,
                "imgUrl": "",
                "categories": [
                    {
                        "id": 3,
                        "name": "Computers"
                    }
                ]
            }
        }
    ],
    "payment": {
        "id": 1,
        "moment": "2019-06-20T21:53:07Z"
    },
    "total": 1431.0
}
```

## Products

### Listar todos os produtos (GET)
```bash
GET | http://localhost:8080/products
```

### Obter um produto por ID (GET)
```bash
GET | http://localhost:8080/products/1
```

## Categories

### Listar todas as categorias (GET)

```bash
GET | http://localhost:8080/categories
```

### Obter uma categoria por ID (GET)

```bash
GET | http://localhost:8080/categories/1
```

# Autor

Eduardo Benjamin Mattos Aguiar

https://www.linkedin.com........
