# Delivery API

API REST desenvolvida com **FastAPI** para gerenciamento de pedidos. Permite autenticação de usuários, criação, listagem e finalização de pedidos.

---

## Tecnologias

- [FastAPI](https://fastapi.tiangolo.com/)
- [SQLAlchemy](https://www.sqlalchemy.org/)
- [Alembic](https://alembic.sqlalchemy.org/)
- [SQLite](https://www.sqlite.org/)
- [JWT (Python-Jose)](https://github.com/mpdavis/python-jose)
- [Uvicorn](https://www.uvicorn.org/)

---

## Pré-requisitos

- Python 3.10+
- pip

---

## Instalação

**1. Clone o repositório**
```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

**2. Crie e ative o ambiente virtual**
```bash
python -m venv venv
venv\Scripts\activate  # Windows
```

**3. Instale as dependências**
```bash
pip install -r requirements.txt
```

**4. Configure as variáveis de ambiente**
```bash
# Copie o arquivo de exemplo
cp .env.example .env

# Edite o .env com seus valores
```

**5. Gere o banco de dados**
```bash
alembic upgrade head
```

**6. Inicie o servidor**
```bash
uvicorn main:app --reload
```

A API estará disponível em: `http://127.0.0.1:8000`

---

## Endpoints

### Auth

| Método | Rota | Descrição | Autenticação |
|--------|------|-----------|--------------|
| `GET` | `/auth/` | Verificar autenticação | ✅ |
| `POST` | `/auth/criar_conta` | Criar nova conta | ❌ |
| `POST` | `/auth/login` | Login com JSON | ❌ |
| `POST` | `/auth/login-form` | Login com formulário | ❌ |
| `GET` | `/auth/refresh` | Renovar token de acesso | ✅ |

### Pedidos

| Método | Rota | Descrição | Autenticação |
|--------|------|-----------|--------------|
| `GET` | `/pedidos/` | Listar todos os pedidos | ✅ |
| `POST` | `/pedidos/pedido` | Criar novo pedido | ✅ |
| `POST` | `/pedidos/pedido/cancelar/{id_pedido}` | Cancelar pedido | ✅ |
| `GET` | `/pedidos/listar` | Listar pedidos | ✅ |
| `POST` | `/pedidos/pedido/adicionar-item/{id_pedido}` | Adicionar item ao pedido | ✅ |
| `POST` | `/pedidos/pedido/remover-item/{id_item_pedido}` | Remover item do pedido | ✅ |
| `POST` | `/pedidos/pedido/finalizar/{id_pedido}` | Finalizar pedido | ✅ |
| `GET` | `/pedidos/pedido/{id_pedido}` | Visualizar pedido | ✅ |
| `GET` | `/pedidos/listar/pedidos-usuario` | Listar pedidos do usuário | ✅ |

> As rotas com ✅ exigem token JWT no header: `Authorization: Bearer <token>`

---

## Documentação interativa

Com o servidor rodando, acesse:

- **Swagger UI:** `http://127.0.0.1:8000/docs`

---

## Variáveis de ambiente

Consulte o arquivo `.env.example` para ver as variáveis necessárias.

---

## Estrutura do projeto

```
├── alembic/          # Migrations do banco de dados
├── main.py           # Entrypoint da aplicação
├── models.py         # Modelos do banco de dados
├── schemas.py        # Schemas Pydantic
├── routers/          # Rotas da API
├── .env.example      # Exemplo de variáveis de ambiente
├── .gitignore        # Arquivos ignorados pelo Git
└── requirements.txt  # Dependências do projeto
```

---

## Autor

Desenvolvido por **Luan** — [LinkedIn](https://www.linkedin.com/in/luan-henrique28/)