# 📚 Biblioteca API

API REST para gerenciamento de **biblioteca escolar**, construída com **NestJS**, **Prisma** e **MySQL**.  
Inclui autenticação com **JWT**, controle de permissões (admin/usuário), CRUD de livros e fluxo de empréstimos/devoluções.

---

## 🛠️ TecnologiasJ

- [NestJS](https://nestjs.com/) – framework back-end
- [Prisma ORM](https://www.prisma.io/) – mapeamento e acesso ao banco
- [MySQL](https://www.mysql.com/) – banco de dados relacional
- [JWT](https://jwt.io/) – autenticação baseada em tokens
- DTOs + ValidationPipe para validação de dados

---

## 🔧 Pré-requisitos

- [Node.js 18+](https://nodejs.org/)  
- [MySQL 8+](https://www.mysql.com/)  
- [Postman](https://www.postman.com/) (para testes)

---

## 📦 Instalação

```bash
# Clone o repositório
git clone https://github.com/olegarioojv/biblioteca-api-joao-victor.git
cd biblioteca-api

# Instale as dependências
npm install
```
---

## ⚙️ Configuração

Crie um arquivo **`.env`** na raiz com as variáveis:

```env
DATABASE_URL="mysql://root:senha@localhost:3306/biblioteca"
JWT_SECRET="chave_secreta"
```

Depois rode os comandos do Prisma:

```bash
npx prisma migrate dev
npx prisma generate
```

---

## ▶️ Como rodar

```bash
# Modo desenvolvimento
npm run start:dev
```

A API estará disponível em `http://localhost:3000`.

---

## 📖 Endpoints principais


### 🔑 Autenticação
```env
- `POST /auth/register` → cria usuário
- `POST /auth/login` → login e retorna token JWT
```

### 👤 Usuários
```env
- `GET /users` → lista usuários (restrito)
- `GET /users/:id` → detalhes de um usuário
```

### 📚 Livros
```env
- `GET /books` → lista livros
- `POST /books` → cria livro (admin)
- `PATCH /books/:id` → atualiza livro
- `DELETE /books/:id` → remove livro
```

### 🔄 Empréstimos
```env
- `POST /loans/borrow` → faz empréstimo
- `POST /loans/return` → devolve livro
```

---

## 🧪 Testes

Na raiz do projeto há uma **collection do Postman** com variáveis pré-configuradas:

- `{{base_url}}` → URL da API (ex: `http://localhost:3000`)
- `{{jwt}}` → Token JWT obtido após login

Utilize em Headers:  
Key: `Authorization`  
Value: `Bearer {{jwt}}`

---

## ✅ Checklist de Entrega

- [x] Estrutura em NestJS com módulos (auth, users, books, prisma)
- [x] DTOs + ValidationPipe
- [x] Auth JWT + RolesGuard
- [x] CRUD de livros
- [x] Empréstimo e devolução
- [x] Collection Postman
---


