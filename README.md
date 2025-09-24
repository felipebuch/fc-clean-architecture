# Clean Architecture – Desafios de Product

Este repositório contém a implementação dos **desafios de Clean Architecture** do curso, focando na entidade **Product** e na aplicação de princípios de **Domain-Driven Design (DDD)** e **arquitetura limpa** em **Node.js + TypeScript**.

## 📂 Estrutura do Projeto

```text
src/
  domain/
    @shared/
      entity/
      event/
      notification/
      repository/
      validator/
    customer/
      entity/
      factory/
      repository/
      validator/
    product/
      entity/
      event/
      factory/
      repository/
      service/
      validator/
    checkout/
      ...
    value-object/
  infrastructure/
    ...
  usecase/
    customer/
      create/
      find/
      list/
      update/
    product/
      create/
      find/
      list/
      update/
```

> **Padrão aplicado:** cada entidade possui pastas próprias para **entidades**, **eventos**, **fábricas**, **repositórios**, **serviços**, **validações** e **casos de uso**, garantindo separação de responsabilidades e alta manutenibilidade.

---

## 🚀 Desafios Implementados

### 1️⃣ CRUD de Products
Criação dos *use cases* para **Product**:

- `create.product.usecase.ts`
- `find.product.usecase.ts`
- `list.product.usecase.ts`
- `update.product.usecase.ts`

Inclui:
- **Testes unitários** para cada caso de uso.
- **Testes de integração** validando a persistência com **SQLite** via **Sequelize**.

---

### 2️⃣ Listagem de Products na API
Exposição da listagem de produtos através de **API REST** criada com **Express**, replicando a lógica já existente em `Customers`.

- Nova rota `GET /products`
- Controller e DTOs dedicados.
- **Teste end-to-end (E2E)** validando a requisição HTTP completa.

---

### 3️⃣ Notification Pattern em Products
Implementação do **Notification Pattern** para agrupar múltiplos erros de validação em uma única resposta.

- Validação com **Yup**, inspirada em `CustomerYupValidator`.
- **Teste específico** cobrindo cenário com dois erros acumulados.

---

## 🧪 Testes

- **Unitários**: validam a lógica isolada de cada caso de uso.
- **Integração**: verificam a interação entre domínio e banco de dados **SQLite** com **Sequelize**.
- **End-to-end**: garantem que a API **Express** funcione de ponta a ponta.

Para executar:

```bash
npm install
npm run test
```

## 🛠️ Tecnologias e Padrões

- Node.js + TypeScript
- Express para a API
- SQLite (banco de testes) + Sequelize (ORM)
- Yup para validações
- Jest para testes automatizados
- Clean Architecture e Domain-Driven Design
- Notification Pattern para tratamento elegante de múltiplos erros

## 📚 Aprendizados

- Estruturação de casos de uso (create, find, list, update) com Clean Architecture.
- Aplicação do Notification Pattern para centralizar e acumular erros.
- Uso de Yup para validação robusta.
- Implementação de testes em múltiplos níveis: unitário, integração e end-to-end.

## 📄 Licença

Este projeto é distribuído sob a licença [MIT](LICENSE). Para mais detalhes, acesse o arquivo **LICENSE**.
