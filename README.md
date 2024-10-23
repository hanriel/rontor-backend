<p align="center">
    <a href="http://rontor.hanriel.ru/" target="blank"><img src="https://rontor.hanriel.ru/Logo_Dark_Badge.png" width="250" alt="rontor Logo" /></a>
</p>

[![Docker Image CI](https://github.com/hanriel/rontor/actions/workflows/deploy.yml/badge.svg)](https://github.com/hanriel/rontor/actions/workflows/deploy.yml)

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Docker compose

```yaml
version: '3'
services:
  client:
    image: rontor-server:latest
    environment:
      PORT: 3000
    ports:
      - '3003:3000'
    restart: always
  server:
    image: rontor-server:latest
    environment:
      DB_HOST: '192.168.0.3'
      DB_PORT: '3306'
      DB_NAME: 'rontor'
      DB_USER: 'root'
      DB_PASSWORD: 'P@ssw0rd'
    ports:
      - '7777:7777'
    restart: always

```