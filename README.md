# Pagamento Simplificado

Microsserviço de transferências financeiras entre usuários, desenvolvido em Java com Spring Boot como estudo prático de arquitetura orientada a microsserviços. O projeto simula um fluxo simplificado de pagamentos com validações e comunicação entre serviços independentes.

---

## 🚀 Stack e Dependências

Tecnologias e bibliotecas utilizadas neste projeto:

- **Java 17**
- **Spring Boot 3.5.3**

### 📦 Dependências principais

- `Spring Web` – Criação de APIs REST
- `Spring Data JPA` – Persistência com ORM
- `H2 Database` – Banco de dados em memória (ambiente local)
- `Spring Boot DevTools` – Facilita desenvolvimento com hot reload
- `Lombok` – Reduz boilerplate de código Java
- `OpenFeign` – Comunicação entre microsserviços via REST

---

## 🧱 Arquitetura do Projeto

O sistema é dividido em três microsserviços independentes, cada um com sua responsabilidade bem definida e comunicação via APIs RESTful:

### 🔹 `ps-user`
- Gerencia o cadastro de usuários e seus saldos (carteira).
- Expõe endpoints para consultar usuários e atualizar saldos.
- Responsável por validar tipo de usuário e saldo disponível.

### 🔸 `ps-transaction`
- Responsável por orquestrar as transferências de valores.
- Realiza chamadas ao serviço de autorização externa.
- Interage com `ps-user` para débito/crédito e com `ps-notification` para notificar o destinatário.

### 🟢 `ps-notification`
- Simula o envio de notificações ao usuário recebedor da transferência.
- Implementado de forma resiliente para lidar com possíveis falhas no mock externo de notificação.

Cada microsserviço é desacoplado, seguindo princípios de responsabilidade única e preparados para evolução modular.

---

<!-- Comentário: Futuras seções que podem ser adicionadas:
- Instruções de execução local (com Maven)
- Exemplos de requisição (curl/Postman)
- Roadmap de melhorias
- Contribuição e licença
- Swagger/OpenAPI
-->
