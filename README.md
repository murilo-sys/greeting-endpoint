# CRUD with Database and Dozer

Este projeto é uma API RESTful construída com **Spring Boot** que implementa operações CRUD para gerenciar pessoas (`Person`) com persistência em banco de dados relacional. Além disso, utiliza **Dozer** para mapeamento e transformação de objetos.

---

## Funcionalidades

- CRUD completo para entidade Person  
- Persistência em banco relacional via Spring Data JPA  
- Mapeamento e conversão automática de objetos com Dozer  
- Tratamento de exceções customizado  

---

## Tecnologias utilizadas

- Java 17+  
- Spring Boot  
- Spring Data JPA  
- Dozer  
- Banco de dados relacional (MySQL, PostgreSQL, etc.)  
- Maven  
- REST API  

---

## Configuração do Banco de Dados

Configure seu banco no arquivo `application.yml` ou `application.properties` (exemplo para MySQL):

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/seu_banco
    username: seu_usuario
    password: sua_senha
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
```

---

## Como executar

1. Clone o repositório:  
   `git clone https://github.com/murilo-sys/crud-with-database-and-dozer.git`  
   `cd crud-with-database-and-dozer`

2. Configure seu banco de dados no arquivo de configuração.

3. Rode o projeto:  
   `./mvnw spring-boot:run`

4. Teste os endpoints (exemplo com Postman ou curl):

| Método | Endpoint           | Descrição                                         |  
|--------|--------------------|--------------------------------------------------|  
| GET    | `/person`          | Lista todas as pessoas                            |  
| GET    | `/person/{id}`     | Busca pessoa pelo ID (retorna erro se não existir) |  
| POST   | `/person`          | Cria nova pessoa (ID enviado é ignorado)         |  
| PUT    | `/person`          | Atualiza pessoa existente (retorna erro se ID não existir) |  
| DELETE | `/person/{id}`     | Remove pessoa pelo ID (retorna erro se ID não existir) |  

---

## Exemplo JSON para criação/atualização

```json
{
  "firstName": "Murilo",
  "lastName": "Silva",
  "address": "Rua das Flores, 123",
  "gender": "Male"
}
```

---

## Estrutura do Projeto

```
src/
├── main/
│   ├── java/io/github/murilo_sys/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── repository/
│   │   ├── model/
│   │   ├── exception/
│   │   └── mapper/        (onde pode estar a configuração do Dozer)
│   └── resources/
│       └── application.yml
└── test/
```

---

## Autor

Murilo ([@murilo-sys](https://github.com/murilo-sys))

---

## Como contribuir

1. Faça um fork do projeto  
2. Crie uma branch: `git checkout -b minha-feature`  
3. Commit suas alterações: `git commit -m 'feat: minha nova feature'`  
4. Faça push para sua branch: `git push origin minha-feature`  
5. Abra um Pull Request  
