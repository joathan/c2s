# Task Manager

Este repositório contém instruções para fazer o setup dos projetos:

É importante iniciar os serviços compartilhados antes de rodar cada projeto.

Passo a passo:

Faça o clone do repositorio com o comando abaixo para clonar todos os projtos de uma unica vez.
```
git clone --recurse-submodules git@github.com:joathan/c2s.git
```

Execute o comando abaixo para subir os containers necessarios antes executar os containers dos projetos.

```shell
docker compose -f docker-compose.shared.yml up -d
```

Apos todoos os serviços subirem, entre na pasta do projeto que necessita subir e copie o `.env-example` para `.env`:

```shell
cd <nome_do_service>
cp .env-example .env
```

```shell
docker compose up -d
```
