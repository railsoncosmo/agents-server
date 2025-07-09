# 🕵️‍♂️ Agents

Projeto desenvolvido durante o evento **Next Level Week (NLW) utilizando tecnologias modernas para criação de uma API robusta e eficiente.

---

## 🚀 Tecnologias

* **Node.js** com **TypeScript** nativo (`--experimental-strip-types`)
* **Fastify** – Framework web rápido e eficiente
* **PostgreSQL** com extensão **pgvector** para vetores
* **Drizzle ORM** – Operações com banco de dados com type-safety
* **Zod** – Validação de esquemas
* **Docker** – Containerização do banco de dados
* **Biome** – Linting e formatação de código

---

## 🏗️ Arquitetura

O projeto segue uma arquitetura modular com os seguintes princípios:

* Separacão de responsabilidades entre **rotas**, **schemas** e **conexão com banco de dados**
* Validação de dados com **Zod** para garantir **type safety**
* Uso de **Drizzle ORM** para operações seguras com o banco
* Validação centralizada de **variáveis de ambiente**

---

## ⚙️ Setup e Configuração

### ✅ Pré-requisitos

* Node.js (versão com suporte a `--experimental-strip-types`)
* Docker e Docker Compose

### 📦 Passos para rodar o projeto

1. **Clone o repositório**

   ```bash
   git clone <url-do-repositorio>
   cd server
   ```

2. **Configure o banco de dados**

   ```bash
   docker-compose up -d
   ```

3. **Configure as variáveis de ambiente**

   Crie um arquivo `.env` na raiz do projeto com o seguinte conteúdo:

   ```env
   PORT=3333
   DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
   ```

4. **Instale as dependências**

   ```bash
   npm install
   ```

5. **Execute as migrações do banco**

   ```bash
   npx drizzle-kit migrate
   ```

6. **(Opcional) Popule o banco com dados de exemplo**

   ```bash
   npm run db:seed
   ```

7. **Execute o projeto**

   * **Modo desenvolvimento**:

     ```bash
     npm run dev
     ```

   * **Modo produção**:

     ```bash
     npm start
     ```

---

## 📚 Scripts Disponíveis

| Script            | Descrição                                    |
| ----------------- | -------------------------------------------- |
| `npm run dev`     | Executa o servidor em modo desenvolvimento   |
| `npm start`       | Executa o servidor em modo produção          |
| `npm run db:seed` | Popula o banco de dados com dados de exemplo |

---

## 🌐 Endpoints da API

A aplicação estará disponível em: **[http://localhost:3333](http://localhost:3333)**

| Método | Rota      | Descrição                               |
| ------ | --------- | --------------------------------------- |
| GET    | `/health` | Verifica se o servidor está funcionando |
| GET    | `/rooms`  | Lista as salas disponíveis              |

---
