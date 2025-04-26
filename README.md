# Projeto Spring Boot - Produto e Categoria

## Tecnologias utilizadas
- Java 17
- Spring Boot
- Spring Data JPA
- MariaDB
- Lombok
- DevTools

---

## Configuração do ambiente

### 1. Instalando e configurando o MariaDB com XAMPP
- Baixe e instale o [XAMPP](https://www.apachefriends.org/index.html).
- Após instalado, abra o painel de controle do XAMPP.
- Inicie o módulo **MySQL** (MariaDB).
- Acesse o `phpMyAdmin` clicando em "Admin" no módulo MySQL.
- Crie um banco de dados chamado `avaliacao`.

---

## 2. Configuração do projeto

No arquivo `src/main/resources/application.properties`, configure seu acesso ao banco:

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/avaliacao
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MariaDBDialect
server.port=8080
```

---

## 3. Rodando o projeto

No terminal, dentro da pasta do projeto:

```bash
./mvnw spring-boot:run
```

Ou, se tiver o Maven instalado globalmente:

```bash
mvn spring-boot:run
```

---

## 4. Relacionamento entre as entidades

Este projeto implementa um relacionamento **One-to-Many** entre as entidades `Categoria` e `Produto`, onde:
- Uma **Categoria** pode conter vários **Produtos**.
- Cada **Produto** pertence a apenas uma **Categoria**.

---

## 5. Endpoints REST

### Categorias
- `GET /categorias` - Lista todas as categorias
- `POST /categorias` - Cria uma nova categoria
- `PUT /categorias/{id}` - Atualiza uma categoria
- `DELETE /categorias/{id}` - Deleta uma categoria

### Produtos
- `GET /produtos` - Lista todos os produtos
- `POST /produtos` - Cria um novo produto
- `PUT /produtos/{id}` - Atualiza um produto
- `DELETE /produtos/{id}` - Deleta um produto

---

## 6. Testando com Postman

### Exemplo de JSON para criar uma categoria:
```json
{
  "nome": "Eletrônicos"
}
```

### Exemplo de JSON para criar um produto:
```json
{
  "nome": "Notebook",
  "preco": 3500.00,
  "categoria": { "id": 1 }
}
```

---

## Autor
- Nome: Willer Henrique da Silva Barbosa
- Curso: ADS - Análise e Desenvolvimento de Sistemas
