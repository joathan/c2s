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
