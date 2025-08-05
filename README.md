# 📦 GLPI com Docker Compose

Este projeto disponibiliza uma instância do [GLPI](https://glpi-project.org/) utilizando `docker-compose`, com banco de dados MariaDB e persistência de dados via volumes.

---

## 🚀 Como usar

### 1. Clone o repositório

```bash
git clone https://github.com/cleberpeixoto95/GLPI.git
cd GLPI
```

### 2. Crie um arquivo `.env`

Crie um arquivo `.env` com as seguintes variáveis (exemplo abaixo):

```env
# .env
MYSQL_ROOT_PASSWORD=senha_root
MYSQL_DATABASE=glpidb
MYSQL_USER=glpi
MYSQL_PASSWORD=senha123
TIMEZONE=America/Sao_Paulo
```

### 3. Suba os containers

```bash
docker-compose up -d
```

---

## 🖥️ Acessando a aplicação

Após os containers estarem rodando, acesse o GLPI via navegador:

```
http://localhost
```

---

## 🧱 Serviços

- **GLPI (Web)**  
  - Imagem: `diouxx/glpi`  
  - Porta: `80:80`  
  - Volume: `glpi_data:/var/www/html`

- **MariaDB (Banco de dados)**  
  - Imagem: `mariadb:10.5`  
  - Volume: `db_data:/var/lib/mysql`  
  - Variáveis definidas via `.env`

---

## 🗂️ Volumes

- `db_data`: armazena os dados do banco MariaDB
- `glpi_data`: armazena os arquivos persistentes do GLPI

---

## 🔐 Segurança

- Certifique-se de trocar as senhas padrão e proteger seu ambiente caso utilize em produção.
- Utilize `HTTPS` e restrinja o acesso ao banco de dados apenas à aplicação GLPI.

---

## 🛠️ Requisitos

- Docker
- Docker Compose