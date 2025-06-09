Esta aplicação fornece uma API RESTful para gerenciamento de tarefas, permitindo que usuários se registrem, autentiquem via JWT e realizem operações de CRUD (criar, ler, atualizar, deletar) em tarefas.

## Tecnologias Utilizadas

* Node.js
* NestJS (framework modular e escalável)
* Sequelize ORM
* PostgreSQL
* TypeScript
* JSON Web Tokens (JWT)

## Estrutura do Projeto

```
src/
├── auth/               # Autenticação (controller, service, module)
├── users/              # Usuários (controller, service, module, model)
├── tasks/              # Tarefas (controller, service, module, model)
├── common/             # Middlewares, filtros, pipes e interceptors
├── config/             # Configurações (database, ambiente)
├── main.ts             # Inicialização da aplicação
└── locale.ts           # Configurações de localização
```

## Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/gabrielgfc/desafio-picpay.git
   cd seu-projeto
   ```

2. Instale as dependências:

   ```bash
   npm install
   ```

3. Crie um arquivo `.env` na raiz com as variáveis de ambiente:

   ```ini
   PORT=3000
   DB_HOST=localhost
   DB_PORT=5432
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   DB_NAME=nome_do_banco
   JWT_SECRET=sua_chave_secreta
   ```

4. Rode as migrations:

   ```bash
   npx sequelize-cli db:migrate
   ```

## Executando a Aplicação

* Desenvolvimento:

  ```bash
  npm run start:dev
  ```
* Produção:

  ```bash
  npm run build
  npm start
  ```

## Endpoints Principais

### Autenticação

* **POST** `/auth/register` — Cadastra novo usuário.
* **POST** `/auth/login` — Autentica usuário e retorna JWT.

### Usuários

* **GET** `/users` — Lista usuários (admin).
* **GET** `/users/:id` — Detalha usuário por ID.

### Tarefas

* **GET** `/tasks` — Lista tarefas do usuário autenticado.
* **GET** `/tasks/:id` — Detalha tarefa por ID.
* **POST** `/tasks` — Cria nova tarefa.
* **PATCH** `/tasks/:id` — Atualiza parcialmente tarefa.
* **DELETE** `/tasks/:id` — Remove tarefa.

> **Observação:** Exceto `/auth/*`, todos os endpoints exigem o header:
>
> ```http
> Authorization: Bearer <seu_token_jwt>
> ```

## Testes

* Unitários:

  ```bash
  npm run test
  ```
* Integração (e2e):

  ```bash
  npm run test:e2e
  ```
* Cobertura:

  ```bash
  npm run test:cov
  ```

## Contribuição

1. Fork do projeto
2. Crie uma branch: `git checkout -b feature/nova-funcionalidade`
3. Commit: `git commit -m "feat: descrição da mudança"`
4. Push: `git push origin feature/nova-funcionalidade`
5. Abra Pull Request

## Autor

* Seu Nome — [@gabrielgfc](https://github.com/gabrielgfc)

