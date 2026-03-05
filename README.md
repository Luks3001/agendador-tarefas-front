# Agendador de Tarefas 📅

Um sistema completo para gerenciamento de tarefas e agendamentos, desenvolvido como um projeto pessoal para aplicar conceitos avançados de desenvolvimento Full-Stack, microsserviços e conteinerização.

Este repositório contém o código-fonte da aplicação **Frontend**.

---

## 🚀 Visão Geral e Demonstração

🎥 **[Clique aqui para ver o vídeo de demonstração completo no LinkedIn](https://www.linkedin.com/posts/lucas-santos-dev_java-springboot-angular19-activity-7435334695514624000-TgSJ?utm_source=share&utm_medium=member_desktop&rcm=ACoAADGvi9ABDm3n0dZ-B69ZLvtRMBpNAVpC1xE)**

---

## 💻 Funcionalidades

O sistema oferece uma interface fluida para que o usuário gerencie sua rotina e seus dados:

* **Gestão de Conta:** Criação de conta de usuário com sistema de autenticação.
* **Perfil do Usuário:** Atualização e exclusão de dados cadastrais (telefone, endereço, etc).
* **Gestão de Tarefas (CRUD):** * Adicionar novas tarefas e agendamentos.
  * Visualizar a lista completa de tarefas.
  * Editar detalhes de tarefas existentes.
  * Remover tarefas concluídas ou canceladas.

---

## 🏗️ Arquitetura do Sistema

Apesar deste repositório focar na interface do usuário, o sistema como um todo foi arquitetado para ser escalável e resiliente, utilizando o padrão **BFF (Backend for Frontend)**. 

A comunicação do Frontend não ocorre diretamente com os serviços de domínio, mas sim através do BFF, que orquestra e entrega os dados formatados exatamente como a tela precisa. O ecossistema de backend é dividido nos seguintes microsserviços:
* `bff-agendador-tarefas`: Gateway e orquestrador das requisições.
* `agendador-tarefas`: Domínio responsável pelas regras de negócio das tarefas.
* `usuario`: Domínio responsável por contas, autenticação e dados pessoais.
* `notificacao`: Serviço de mensageria/alertas.

🔗 **[Acessar Repositório do Backend (BFF) e Documentação Swagger](https://github.com/Luks3001/bff-agendador-tarefas)**

---

## 🛠️ Tecnologias Utilizadas

**Frontend:**
* [Angular 19](https://angular.dev/) - Framework principal.
* [Angular Material 19](https://material.angular.io/) - Componentes de UI modernos e responsivos.
* [TypeScript](https://www.typescriptlang.org/) - Tipagem estática e segurança.

**Backend & Infraestrutura:**
* **Linguagem/Framework:** Java 17 com Spring Boot.
* **Infraestrutura:** Docker e Docker Compose.
* **Bancos de Dados:** PostgreSQL (Relacional para usuários) e MongoDB (NoSQL para tarefas).

---

## ⚙️ Como executar o projeto localmente

### Pré-requisitos
Certifique-se de ter instalado em sua máquina:
* [Node.js](https://nodejs.org/en/)
* [Angular CLI](https://angular.dev/tools/cli)
* [Docker e Docker Desktop](https://www.docker.com/) (Necessário para subir a infraestrutura local)

### 1. Subindo a infraestrutura do Backend (Microsserviços)
Como o projeto utiliza múltiplos repositórios e o Docker Compose compila as imagens localmente via `build`, é necessário clonar todos os serviços em um mesmo diretório raiz.

1. Crie uma pasta principal no seu computador (ex: `projeto-agendador`).
2. Abra o terminal dentro dessa pasta e clone os repositórios com os nomes exatos abaixo:


```bash
git clone https://github.com/Luks3001/usuario
git clone https://github.com/Luks3001/agendador-tarefas
git clone https://github.com/Luks3001/notificacao
git clone https://github.com/Luks3001/bff-agendador-tarefas
```

3. Acesse a pasta do orquestrador:
```bash
cd bff-agendador-tarefas
```
4. Execute o comando para compilar e subir todos os microsserviços e bancos de dados:
```bash
docker-compose up -d --build
```

### 2. Rodando o Frontend
Com os serviços de backend ativos nos containers, abra uma nova aba no terminal e siga os passos:

1. Clone este repositório (pode ser dentro da mesma pasta raiz criada anteriormente):
```bash
git clone https://github.com/Luks3001/agendador-tarefas-front
```
2. Acesse a pasta do projeto:
```bash
cd agendador-tarefas-front
```
3. Instale as dependências:
```bash
npm install
```
4. Execute o servidor de desenvolvimento:
``` bash 
ng serve
```
5. Abra o navegador e acesse http://localhost:4200/.

