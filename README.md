# Projeto Spring Boot - Produto e Categoria

## Tecnologias
- Spring Boot
- Spring Data JPA
- MariaDB
- Lombok
- DevTools

## Configuração do Banco de Dados

No arquivo `application.properties`:
```
spring.datasource.url=jdbc:mariadb://localhost:3306/avaliacao
spring.datasource.username=root
spring.datasource.password=suasenha
```

## Rodando a aplicação

```bash
./mvnw spring-boot:run
```

## Endpoints REST

### Categorias
- `GET /categorias`
- `POST /categorias`
- `PUT /categorias/{id}`
- `DELETE /categorias/{id}`

### Produtos
- `GET /produtos`
- `POST /produtos`
- `PUT /produtos/{id}`
- `DELETE /produtos/{id}`

## Testando com Postman
Envie requisições para os endpoints com JSON como este:

```json
{
  "nome": "Eletrônicos"
}
```

```json
{
  "nome": "Notebook",
  "preco": 3500.00,
  "categoria": { "id": 1 }
}
```
