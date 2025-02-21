# 📌 Documentação do Projeto Django: Sistema de Votação com Django Admin

## 📝 Visão Geral

Este projeto é um sistema simples de votação construído com o framework **Django** e containerizado com **Docker**. Sua principal função é gerenciar votos em uma plataforma online.

O foco principal do sistema está na administração de sites por meio da interface **Django Admin**, onde os administradores têm controle total sobre as funcionalidades do sistema, como:
- 📌 **Criação, edição e exclusão de perguntas**
- 📌 **Gerenciamento de opções de resposta**
- 📌 **Visualização dos resultados das votações**

---

## 📂 Estrutura do Projeto

O projeto segue a estrutura básica de um aplicativo Django, com a adição de arquivos de configuração para Docker. Abaixo está um resumo da estrutura de diretórios:

```
/mysite/
│
├── Dockerfile
├── docker-compose.yml
├── manage.py
├── mysite/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│
└── polls/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── views.py
    ├── urls.py
    └── migrations/
```

---

## 🔑 Principais Arquivos

- **`Dockerfile`** → Define como o ambiente do projeto será montado em um container Docker.
- **`docker-compose.yml`** → Configurações para gerenciar múltiplos serviços (ex.: banco de dados e aplicação Django).
- **`mysite/settings.py`** → Configurações globais do projeto, incluindo banco de dados.
- **`polls/models.py`** → Define os modelos de dados usados no sistema de votação (Pergunta e Escolha).
- **`polls/admin.py`** → Customiza a interface do Django Admin para gerenciar perguntas e escolhas.

---

## ⚙️ Funcionalidades Principais

### ✅ Sistema de Votação
- 📌 **Perguntas e Opções de Voto**: Os administradores podem criar e gerenciar perguntas de votação.
- 📌 **Votação de Usuários**: Os usuários podem acessar uma página de votação e selecionar suas respostas.

### 🔧 Administração com Django Admin
- 📌 **Criar e editar perguntas** com opções de resposta.
- 📌 **Monitorar resultados em tempo real** pelo painel administrativo.
- 📌 **Gerenciar usuários e permissões**.

---

## 🐳 Utilização do Docker

O projeto está **containerizado com Docker**, permitindo a replicação do ambiente de desenvolvimento e produção de forma rápida e eficiente.

### 🚀 Subindo o Sistema com Docker

1️⃣ **Instale o Docker** (caso não tenha instalado).

2️⃣ **Construa a imagem do Docker**:

```bash
docker-compose build
```

3️⃣ **Suba os containers**:

```bash
docker-compose up
```

4️⃣ **Acesse o Django Admin** no navegador:

```bash
http://localhost:8000/admin
```

---

## 🔒 Variáveis de Ambiente

As variáveis sensíveis (como `SECRET_KEY` e credenciais do banco) devem ser configuradas no `docker-compose.yml` ou em um arquivo `.env`.

---

## 🗄️ Banco de Dados

O sistema utiliza **PostgreSQL** como banco de dados, executado em um container Docker.

### 🔧 Configuração no `docker-compose.yml`:

```yaml
services:
  db:
    image: postgres
    environment:
      POSTGRES_DB: meu_banco
      POSTGRES_USER: usuario
      POSTGRES_PASSWORD: senha
```

### 📌 Aplicar as migrações do banco de dados:

```bash
docker-compose exec web python manage.py migrate
```

---

## 🔑 Configuração Inicial do Django Admin

Para acessar o Django Admin, é necessário criar um **superusuário**:

```bash
docker-compose exec web python manage.py createsuperuser
```

---

## 🧪 Testes

Para garantir a integridade do sistema, execute os testes com:

```bash
docker-compose exec web python manage.py test
```

---

## 🏁 Conclusão

Este projeto oferece um **sistema simples de votação**, com foco na administração pelo **Django Admin**.

A **containerização com Docker** facilita a configuração e a manutenção do ambiente, garantindo escalabilidade e facilidade no desenvolvimento.

🚀 **Agora é só rodar o projeto e começar a votar!**

