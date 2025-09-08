# db

# CRUD com MongoDB e Python (PyMongo)

Este projeto demonstra um **CRUD completo** (Create, Read, Update, Delete) em um banco de dados MongoDB utilizando a biblioteca [PyMongo](https://pypi.org/project/pymongo/).

O código funciona com:
- MongoDB local
- MongoDB em container Docker
- MongoDB Atlas (nuvem)

---

## 📌 Arquivos

- `mongodb_crud_demo.py` → script principal com as operações CRUD
- `requirements.txt` → lista de dependências

---

## 🚀 Como rodar o projeto

### 1. Clonar o repositório

git clone https://github.com/SEU_USUARIO/crud-mongodb-python.git
cd crud-mongodb-python

### 2. Criar ambiente virtual (recomendado)

python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

### 3. Instalar dependências

pip install -r requirements.txt

### 4. Subir MongoDB (se usar Docker)

docker run -d --name mongodb -p 27017:27017 mongo:latest

### 5. Executar o script

python mongodb_crud_demo.py

## ⚙️ Configuração de Conexão

Por padrão, o script conecta em:

mongodb://localhost:27017

Se estiver usando MongoDB Atlas ou outra URI, defina a variável de ambiente MONGODB_URI:

# Linux/macOS
export MONGODB_URI="sua-uri-aqui"

# Windows PowerShell
$env:MONGODB_URI="sua-uri-aqui"


## 📖 O que o código faz

Conecta ao MongoDB e cria o banco demo_crud com a coleção users.

Cria um índice único no campo email.

Insere documentos de exemplo (CREATE).

Lê documentos com filtros e projeções (READ).

Atualiza registros (inclusive com upsert) (UPDATE).

Deleta registros específicos e em massa (DELETE).

Exibe todos os resultados no terminal.

Saída esperada
== CREATE ==
Inseridos _ids: [ObjectId('...'), ObjectId('...'), ObjectId('...')]

== READ (todos) ==
{'_id': ObjectId(...), 'name': 'Ana Carolina Mendes', 'email': 'ana@example.com', 'age': 22, ...}

== UPDATE (inc age onde tags contém 'mobile') ==
Atualização: {'matched': 2, 'modified': 2}

== DELETE (remover 'ana@example.com') ==
Removidos: 1

✅ Demonstração finalizada.

👨‍💻 Projeto desenvolvido para fins didáticos (atividade prática de CRUD com PyMongo).
