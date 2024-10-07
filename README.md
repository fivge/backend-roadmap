# Backend roadmap

Languages: `javascript` `typescript`

https://roadmap.sh/backend

## 0x01 理论支撑

### 12-Factor

https://12factor.net/zh_cn/

> 为构建 SaaS 应用提供了方法论

### REST 请求规范

### 数据库表设计参考规范

### some thoughts

应该在数据库的包装层，做数据库主键 ID 的 encode、decode 工作。暴露给 service 的数据，不包含数据库的真实 ID。

## 0x02 技术实现

### framework lite

- ~~express~~ ~~restify~~ [tsed](https://github.com/tsedio/tsed) fastify
- https://github.com/honojs/hono TODO
- https://github.com/moleculerjs/moleculer TODO
- https://github.com/hapijs/hapi TODO
- https://github.com/vercel/micro TODO
- https://github.com/oakserver/oak TODO

https://github.com/fivge/node-http-middleware

### framework heavy

- nestjs

  https://github.com/fivge/tour-of-nestjs

- https://github.com/adonisjs/core TODO

- [eggjs](https://github.com/eggjs/egg)

- https://github.com/koajs/koa

- https://github.com/balderdashy/sails

- https://github.com/meteor/meteor TODO

##### headless cms?

- https://github.com/payloadcms/payload
- https://github.com/strapi/strapi
- https://github.com/directus/directus

**how to choose?**

语言框架往往不是限制，限制主要在数据库、负载均衡等方向。选择好用、快速、生态丰富的即可。

https://web-frameworks-benchmark.netlify.app/compare?f=elysia,hono,hono-bun,h3,fastify,nestjs-fastify

|                      |         |     |
| -------------------- | ------- | --- |
| quick                | fastify |     |
| middle               | hono    |     |
| big with more custom | nestjs  |     |
| big                  | strapi  |     |

### In-memory Cache

- https://www.npmjs.com/package/memory-cache
- https://www.npmjs.com/package/lru-cache
- https://github.com/jaredwray/keyv TODO

### db

- **postgresql**
- mysql
- mariadb
- ~~MongoDB~~ [FerretDB](https://github.com/FerretDB/FerretDB)

### orm

- [typeorm](https://github.com/typeorm/typeorm)

  https://github.com/fivge/typeorm-gen

- [sequelize](https://github.com/sequelize/sequelize)

- https://github.com/prisma/prisma

- https://github.com/pubkey/rxdb TODO

### API doc & mock

..

- https://github.com/alinGmail/LiveMock
- https://github.com/YMFE/yapi
- https://github.com/hoppscotch/hoppscotch
- https://github.com/easy-mock/easy-mock
- https://github.com/hey-api/openapi-ts
- https://github.com/openapi-ts/openapi-typescript

#### mock

- not active
  - ~~https://github.com/google/intermock~~
  - [mockjs](https://github.com/nuysoft/Mock)
- active
  - https://github.com/nock/nock
  - https://github.com/mockoon/mockoon
  - https://github.com/mswjs/msw

#### ieads

基于 cloudflare 开发一套 mock 服务 ，类似于 mockoon， 或者在此基础上提 pr

- [ ] 提供 mock api

- [ ] 可以设置 static data——单独 api 或者原始 api 模式

  数据存储在 kv 中，可以读取和更新

mock api 服务

- 代码中，注入 mock
- 浏览器图形化界面，mock 数据
- 服务端接口，返回 mock 数据
- mock 数据生成函数逻辑

### Auth

- JWT

  https://jwt.io/libraries

  https://github.com/nearform/fast-jwt

- oAuth2

  https://oauth.net/code/nodejs/

- https://github.com/jaredhanson/passport

- cookie

  cookie-parser

### logger

- https://github.com/pinojs/pino
- morgan
- winston winston-daily-rotate-file

### 服务通讯 End-to-end

- google-protobuf
- https://github.com/trpc/trpc

#### 长连接

- ws

### test

https://github.com/wg/wrk

### serverless

- cloudflare workers

  https://github.com/fivge/cf-worker

  https://github.com/fivge/r5renew

### bot

- tgbot

- msbot

  https://github.com/fivge/__teams_doc

- ....

## 0x03 代码实现

### 校验

> 基于 schema

- https://github.com/colinhacks/zod

> 基于 class

`class-validator` `class-transformer`
