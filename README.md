# The Graphql
This project is built with NestJS, Graphql, Docker and Prisma.

- [The Graphql](#the-graphql)
  - [Prerequisites](#prerequisites)
    - [pnpm](#pnpm)
    - [Nest CLI](#nest-cli)
    - [Installing docker-compose](#installing-docker-compose)
    - [Docker](#docker)
    - [Installing Prisma](#installing-prisma)
  - [Graphql via Nest CLI](#graphql-via-nest-cli)



## Prerequisites
### pnpm
[pnpm](https://pnpm.io/installation): Fast, disk space efficient [package manager](https://pnpm.io/cli/add).
```bash
npm install -g pnpm

```
### Nest CLI
Setting up a new project is quite simple with the [Nest CLI](https://docs.nestjs.com/first-steps).

```bash
npm i -g @nestjs/cli
$ nest new

pnpm install
pnpm run start:dev


```

### Installing docker-compose

The base command for the [Docker CLI](https://docs.docker.com/engine/reference/commandline/docker/) and [docker compose](https://docs.docker.com/engine/reference/commandline/compose/).


```bash
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version

docker-compuse up -d

docker ps
docker exec -it NAME bash
psql -U root -d backend
backend=# \dt

docker-compuse stop
```
```sql
SELECT *
FROM pg_catalog.pg_tables
WHERE schemaname != 'pg_catalog' AND 
    schemaname != 'information_schema';
```
### Docker

```bash
docker ps
docker inspect backend-db

# Backup a container
docker run --rm --volumes-from CONTAINER -v $(pwd):/backup busybox tar cvfz /backup/backup.tar CONTAINERPATH

# Restore container from backup
docker run --rm --volumes-from CONTAINER -v $(pwd):/backup busybox sh -c "cd CONTAINERPATH && tar xvf /backup/backup.tar --strip 1"



```

### Installing Prisma
[Prisma](https://www.prisma.io/docs/getting-started) is a next-generation ORM that consists of these tools:

Prisma Client: Auto-generated and type-safe query builder for Node.js & TypeScript
Prisma Migrate: Declarative data modeling & migration system
Prisma Studio: GUI to view and edit data in your database

```bash
pnpm add -D prisma
pnpx prisma init
pnpx prisma migrate dev --name dog

```
## Graphql via Nest CLI

```bash
nest g service prisma

pnpm add @nestjs/graphql @nestjs/apollo @apollo/server graphql

pnpm add -D ts-morph

# resource dog graphql (schema first)
nest generate resource dog

#Updates all dependencies, adhering to ranges specified in package.json
pnpm up
# Updates all dependencies, ignoring ranges specified in package.json
pnpm up --latest
```