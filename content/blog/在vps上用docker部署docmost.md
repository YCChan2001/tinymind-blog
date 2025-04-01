---
title: 在vps上用docker部署Docmost
date: 2025-04-01T06:08:45.831Z
---

docker-compose.yml 文件是一个 YAML 格式的文本文件，用于定义 Docker Compose 应用程序的配置。

1. 进入和编辑：
使用 vi/vim：
vi docker-compose.yml：使用 vi/vim 编辑器打开文件。
在 vi/vim 中，按下 i 进入插入模式，然后可以进行修改。

3. 保存和退出：
使用 vi/vim：
按下 Esc 键退出插入模式。
输入 :wq 并按下 Enter 键以保存更改并退出。
输入 :q! 并按下 Enter 键，不保存退出。

4. 删除：
要删除 docker-compose.yml 文件，可以使用 rm 命令：
rm docker-compose.yml

重要说明：
在修改 docker-compose.yml 文件后，您需要运行 docker-compose up 命令以使更改生效。
请务必小心操作，以免意外删除或修改重要的配置文件。
在修改yaml文件时，要注意yaml文件格式，空格，缩进等，如果格式错误，docker-compose将无法正确解析。

```
services:
  docmost:
    image: docmost/docmost:latest
    depends_on:
      - db
      - redis
    environment:
      APP_URL: "http://xxx.xxx.xxxx.xxx:3000" #或者域名
      APP_SECRET: "abcd1234xxxxdgsdgagga1111"      #这个密码要超过32个字符
      DATABASE_URL: "postgresql://docmost:STRONG_DB_PASSWORD@db:5432/docmost?schema=public"    #替换STRONG_DB_PASSWORD
      REDIS_URL: "redis://redis:6379"
    ports:
      - "3000:3000"
    restart: unless-stopped
    volumes:
      - ./docmost:/app/data/storage

  db:
    image: postgres:16-alpine
    environment:
      POSTGRES_DB: docmost
      POSTGRES_USER: docmost
      POSTGRES_PASSWORD: STRONG_DB_PASSWORD  #替换STRONG_DB_PASSWORD
    restart: unless-stopped
    volumes:
      - ./db_data:/var/lib/postgresql/data

  redis:
    image: redis:7.2-alpine
    restart: unless-stopped
    volumes:
      - ./redis_data:/data
```
