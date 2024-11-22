# Task Manager

Bem-vindo ao repositório do **Task Manager**! Este guia contém as instruções passo a passo para configurar e executar os serviços do projeto.

---

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas no seu ambiente antes de iniciar:
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- Acesso ao repositório no GitHub

---

## Configuração Inicial

### 1. Clone o Repositório com Submódulos

Use o comando abaixo para clonar o repositório principal juntamente com todos os submódulos de uma só vez:

```shell
git clone --recurse-submodules git@github.com:joathan/c2s.git
```

---

### 2. Inicie os Serviços Compartilhados

Os serviços compartilhados são necessários para o funcionamento dos demais projetos. Execute o comando abaixo para inicializá-los:

```shell
docker compose -f docker-compose.shared.yml up -d
```

Este comando irá subir os containers necessários em segundo plano.

---

## Configuração de um Serviço Específico

Para executar um serviço específico, siga os passos abaixo:

### 1. Acesse a Pasta do Serviço

Entre na pasta do serviço que deseja subir. Substitua `<nome_do_service>` pelo nome do serviço correspondente:

```shell
cd <nome_do_service>
```

### 2. Configure o Arquivo de Ambiente

Copie o arquivo de exemplo `.env-example` para `.env`:

```shell
cp .env-example .env
```

---

### 3. Suba os Containers do Serviço

Com o arquivo `.env` configurado, inicie os containers do serviço:

```shell
docker compose up -d
```

---

## Monitoramento dos Containers

Você pode verificar o status dos containers executando o comando:

```shell
docker ps
```

---

## Configuração do Frontend

O **frontend** foi desenvolvido utilizando React com TypeScript para consumir os endpoints do `auth_service` e do `task_management_service`. Siga os passos abaixo para configurar e executar o frontend:

---

### 1. Pré-requisitos

Antes de iniciar, certifique-se de ter as seguintes ferramentas instaladas no seu ambiente:
- [Node.js](https://nodejs.org/) (versão 18 ou superior)
- [npm](https://www.npmjs.com/) ou [yarn](https://yarnpkg.com/) (gerenciador de pacotes)

---

### 2. Acesse a Pasta do Frontend

Navegue até a pasta do frontend:

```shell
cd c2s_frontend
```

---

### 3. Instale as Dependências

Use o gerenciador de pacotes para instalar as dependências do projeto:

```shell
npm install
```

ou

```shell
yarn install
```

---

### 4. Execute o Frontend

Para iniciar o servidor de desenvolvimento, use:

```shell
npm start
```

ou

```shell
yarn start
```

O frontend estará disponível em: [http://localhost:3000](http://localhost:3000).

---

### 5. Testando o Frontend

Certifique-se de que os serviços backend (`auth_service` e `task_management_service`) estão ativos antes de testar o frontend.
