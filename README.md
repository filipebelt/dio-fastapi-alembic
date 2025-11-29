# DIO - Projeto FastAPI + Alembic + Pydantic Settings

Este repositório faz parte do desafio da DIO para criação de uma API utilizando **FastAPI**, **SQLAlchemy**, **Alembic** e **pydantic-settings**.

## 🚀 Tecnologias Utilizadas

- FastAPI
- Uvicorn
- SQLAlchemy
- Alembic
- Pydantic v2
- pydantic-settings
- SQLite (banco padrão)

---

## 📦 Estrutura do Projeto

```bash
.
├── alembic.ini
├── alembic/
│   ├── env.py
│   ├── script.py.mako
│   └── versions/
│       └── <hash>_create_user_table.py
├── src/
│   ├── main.py
│   ├── core/
│   │   └── config.py
│   ├── db/
│   │   ├── base.py
│   │   └── session.py
│   ├── models/
│   │   └── user.py
│   ├── schemas/
│   │   └── user.py
│   └── api/
│       └── v1/
│           └── routes_user.py
├── .env.example
└── requirements.txt
```

---

## ⚙️ Configuração do Ambiente

### 1. Criar e ativar ambiente virtual (opcional, mas recomendado)

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux/Mac
source .venv/bin/activate
```

### 2. Instalar dependências

```bash
pip install -r requirements.txt
```

### 3. Configurar variáveis de ambiente

Crie um arquivo **.env** na raiz do projeto baseado no arquivo **.env.example**:

```bash
cp .env.example .env
```

---

## 🗄️ Executar Migrações (Alembic)

### 1. Criar as tabelas no banco de dados

O projeto já vem com uma migration pronta para a tabela `users`. Basta rodar:

```bash
alembic upgrade head
```

Se quiser criar novas migrations depois de alterar os models:

```bash
alembic revision --autogenerate -m "sua mensagem"
alembic upgrade head
```

---

## ▶️ Executar a API

```bash
uvicorn src.main:app --reload
```

A aplicação estará disponível em:

- Swagger UI: http://127.0.0.1:8000/docs
- Redoc: http://127.0.0.1:8000/redoc

---

## 👤 Rotas de Usuário (Exemplo)

- `GET /api/v1/users/` – Lista todos os usuários
- `POST /api/v1/users/` – Cria um novo usuário
- `GET /api/v1/users/{user_id}` – Busca usuário por ID
- `DELETE /api/v1/users/{user_id}` – Remove usuário

---

## 📎 DIO

Sinta-se à vontade para forkar este repositório, melhorar o código e utilizá-lo como parte do seu portfólio em entrevistas técnicas. Boa sorte! 🚀
