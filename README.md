# API de Usuários

Esta API permite a criação, listagem, atualização e exclusão de usuários. Ela utiliza Express.js, Prisma ORM e SQLite (ou outro banco de dados suportado pelo Prisma).

## Instalação

1. Clone o repositório
2. Instale as dependências com `npm install`
3. Crie uma conta no MongoDB Atlas ou configure uma instância local do MongoDB.
No MongoDB Atlas, crie um cluster e obtenha a URL de conexão.
4. Edite um arquivo `.env` com os seus dados.
5. Rode o comando `node --watch .\server.js` para iniciar o servidor

## Endpoints

### `POST /usuarios`
Cria um novo usuário.

### `GET /usuarios`
Lista todos os usuários. Filtra por `name`, `email` ou `age` se fornecidos como parâmetros de consulta.

### `PUT /usuarios/:id`
Atualiza as informações de um usuário pelo `id`.

### `DELETE /usuarios/:id`
Exclui um usuário pelo `id`.

**Parâmetros no corpo da requisição (JSON):**
- `email` (string): O e-mail do usuário.
- `name` (string): O nome do usuário.
- `age` (number): A idade do usuário.

**Exemplo de requisição:**
```bash
curl -X POST http://localhost:3000/usuarios \
-H "Content-Type: application/json" \
-d '{"email": "exemplo@email.com", "name": "João", "age": 30}'