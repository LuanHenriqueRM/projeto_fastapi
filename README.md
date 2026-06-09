# Delivery API

API REST desenvolvida com **FastAPI** para gerenciamento de pedidos. Permite autenticação de usuários, criação, listagem e finalização de pedidos.

## Tecnologias

- [FastAPI](https://fastapi.tiangolo.com/)
- [SQLAlchemy](https://www.sqlalchemy.org/)
- [Alembic](https://alembic.sqlalchemy.org/)
- [SQLite](https://www.sqlite.org/)
- [JWT (Python-Jose)](https://github.com/mpdavis/python-jose)
- [Uvicorn](https://www.uvicorn.org/)

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
source venv/bin/activate  # Linux/Mac
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

## 📌 Endpoints

| Método | Rota | Descrição | Autenticação |
|--------|------|-----------|--------------|
| `POST` | `/login` | Autenticação do usuário | ❌ |
| `POST` | `/pedidos` | Criar novo pedido | ✅ |
| `GET` | `/pedidos` | Listar pedidos | ✅ |
| `PATCH` | `/pedidos/{id}/finalizar` | Finalizar pedido | ✅ |

> As rotas com ✅ exigem token JWT no header: `Authorization: Bearer <token>`

---

## Documentação interativa

Com o servidor rodando, acesse:

- **Swagger UI:** `http://127.0.0.1:8000/docs`

---

## Variáveis de ambiente

Consulte o arquivo `.env.example` para ver as variáveis necessárias.

---

## 📁 Estrutura do projeto

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

Desenvolvido por **Luan Henrique** — [LinkedIn][(https://www.linkedin.com/in/luan-henrique28/)]
