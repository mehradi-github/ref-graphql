# The Graphql
This project is built with NestJS, Graphql, Docker and Prisma.

- [The Graphql](#the-graphql)
  - [Prerequisites](#prerequisites)
    - [pnpm](#pnpm)
    - [Nest CLI](#nest-cli)
    - [Installing docker-compose:](#installing-docker-compose)



## Prerequisites
### pnpm
[pnpm](https://pnpm.io/installation): Fast, disk space efficient package manager.
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

### Installing docker-compose:
```bash
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version
```