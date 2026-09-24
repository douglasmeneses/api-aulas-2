# 🛒 API E-Commerce & Carrinho de Compras — Programação Web II

![Java](https://img.shields.io/badge/Java-11-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-2.7-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white)

API RESTful para plataforma de e-commerce desenvolvida na disciplina de **Programação Web** (Unipê). A aplicação implementa gestão de usuários, catálogo de produtos, fluxo completo de carrinho de compras (`Carrinho` e `ItemCarrinho`), além de integração com APIs externas para consulta de CEP e catálogo fictício.

---

## 📌 Funcionalidades

- 👤 **Gestão de Usuários:** Cadastro, autenticação/login, consulta por ID, listagem geral, atualização de perfil cadastral e alteração de senha.
- 📦 **Catálogo de Produtos:** Cadastro, listagem, busca detalhada, atualização de estoque/preço e remoção de produtos.
- 🛍️ **Carrinho de Compras:** Criação de carrinho vinculado a usuário, inserção de itens com quantidade, atualização de itens, remoção e listagem dos produtos contidos.
- 💳 **Checkout & Compras:** Simulação de fechamento de pedido com formas de pagamento e histórico de compras.
- 📍 **Enriquecimento de Dados:** Integração para busca de endereços via CEP (`DadosCepDTO`) e importação de produtos mockados (`FakeProductDTO`).

---

## 🏗️ Estrutura do Projeto

```text
src/main/java/com/unipe/api2/
├── controller/          # UsuarioController, ProdutoController, CarrinhoController
├── dto/                 # DTOs de transporte, CEP (ViaCEP) e FakeProduct
│   └── form/            # Formulários de entrada (Login, ProdutoForm, UsuarioForm)
├── model/               # Entidades JPA (Usuario, Produto, Carrinho, ItemCarrinho)
├── repository/          # Interfaces Spring Data JPA
├── service/             # Regras de negócio de usuários, produtos e carrinhos
├── utils/               # Classes utilitárias e contratos de resposta
└── Api2Application.java
```

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** [Java 11](https://www.oracle.com/java/)
- **Framework Principal:** [Spring Boot 2.7.17](https://spring.io/projects/spring-boot)
- **Acesso a Dados:** Spring Data JPA / Hibernate
- **Banco de Dados:** [MySQL 8](https://www.mysql.com/)
- **Produtividade:** Project Lombok & Spring Boot DevTools
- **Build Tool:** Gradle

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
- [JDK 11](https://adoptium.net/) instalado
- [MySQL Server](https://www.mysql.com/) rodando localmente ou via container

### 1. Clonar o repositório
```bash
git clone https://github.com/douglasmeneses/api-aulas-2.git
cd api-aulas-2
```

### 2. Configurar o banco de dados
Configure o arquivo `src/main/resources/application.properties` com as credenciais do seu banco de dados:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/db_ecommerce?createDatabaseIfNotExist=true&useTimezone=true&serverTimezone=UTC
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 3. Executar o projeto
No Linux/macOS:
```bash
./gradlew bootRun
```
No Windows:
```cmd
gradlew.bat bootRun
```

A aplicação subirá em `http://localhost:8080`.

---

## 📡 Principais Endpoints

### Usuários (`/usuarios`)
- `POST /usuarios/criar` — Cadastra novo usuário
- `POST /usuarios/login` — Autentica usuário
- `GET /usuarios/listar-todos` — Lista todos os usuários
- `GET /usuarios/buscar/{id}` — Busca por ID
- `PUT /usuarios/atualizar-dados/{id}` — Atualiza dados cadastrais
- `PATCH /usuarios/atualizar-senha/{id}` — Atualiza senha
- `DELETE /usuarios/deletar/{id}` — Remove usuário

### Produtos (`/produtos`)
- `POST /produtos/criar` — Cadastra novo produto
- `GET /produtos/listar-todos` — Lista produtos
- `GET /produtos/buscar/{id}` — Detalha produto
- `PUT /produtos/atualizar-dados/{id}` — Atualiza produto
- `DELETE /produtos/deletar/{id}` — Remove produto

### Carrinho (`/carrinhos`)
- `POST /carrinhos/criar` — Cria carrinho e adiciona itens
- `PUT /carrinhos/atualizar/{id}` — Atualiza quantidade de itens
- `DELETE /carrinhos/deletar/{id}` — Remove item do carrinho
- `GET /carrinhos/listar-produtos/{id}` — Lista produtos do carrinho

---

## 👨‍💻 Autor

Desenvolvido por **Douglas Meneses**.

- 💼 GitHub: [@douglasmeneses](https://github.com/douglasmeneses)
- ✉️ Email: [meneses.doug@gmail.com](mailto:meneses.doug@gmail.com)
