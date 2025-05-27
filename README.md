
# 🧭 Guia de Execução dos Serviços com Docker Compose

## 📌 Airflow

### 🔹 Subir os serviços do Airflow

```bash
docker-compose -f docker-compose-airflow.yml up -d
```

### 🔐 Credenciais

- **Interface Web**: http://localhost:8081  
- **Usuário**: `airflow`  
- **Senha**: `airflow`  
- **Autenticação**: BasicAuth (configurada via variáveis de ambiente)

---

## 🛰️ Apache Hop

### 🔹 Subir o serviço

```bash
docker compose -f docker-compose-apache-hop-server.yml up -d
```

### 🔗 Endpoints

- **Hop GUI (Web)**: http://localhost:8080/ui  
- **API REST**: http://localhost:8080/hop  

### ℹ️ Observações

- Sem autenticação por padrão  
- A autenticação pode ser habilitada manualmente nas configurações

---

## ⚡ Apache Spark

### 🔹 Subir os serviços

```bash
docker-compose -f docker-compose-spark.yml up -d
```

### 🔗 Endpoints

- **Spark Master UI**: http://localhost:8083  
- **Spark Worker UI**: http://localhost:8082  

### ℹ️ Observações

- Nenhuma autenticação por padrão  
- Modo standalone (sem login/senha)

---

## 🗄️ Banco de Dados PostgreSQL (usado pelo Airflow)

- **Host**: `localhost`  
- **Porta**: `5432` (ou `5433` se alterado no compose)  
- **Banco**: `airflow`  
- **Usuário**: `airflow`  
- **Senha**: `airflow`  
- **Tipo de acesso**: TCP (PostgreSQL protocol — ex: via DBeaver)

---

## ✅ Recomendações

- Mantenha as pastas `dags`, `logs`, e `plugins` organizadas na raiz do projeto
- Para acessar o banco com segurança, considere criar usuários com permissões limitadas
- Use `.env` para ocultar senhas sensíveis, caso publique o repositório

---

## 📂 Estrutura sugerida

```text
/
├── dags/
├── logs/
├── plugins/
├── docker-compose-airflow.yml
├── docker-compose-apache-hop-server.yml
├── docker-compose-spark.yml
└── README.md
```
