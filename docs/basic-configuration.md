---
id: configuration
title: 配置
layout: docs
category: 基础知识
next: router
permalink: docs/configuration.html
---

Qails 使用 [dotenv](https://www.npmjs.com/package/dotenv) 做工程配置管理，dotenv 只支持字符串类型变量，如果代码中需要布尔型的开关变量，使用时必须做字符串比较，如

```js
if (process.env.ENABLE === 'true') {
  // do something
}
```

工程初始化的通用配置项如下：
```
# 环境变量
NODE_ENV=local

# API服务端口
PORT=3000

# 执行代码目录地址[本地开发为src，其它环境均为dist]
DOCUMENT_ROOT=src

# 日志文件存放目录
LOG_ROOT=logs

# 是否输出带格式化的json
JSON_PRETTY=true

# 是否启动 session
SESSION_ENABLE=false

# 是否启用NODE对安全证书的验证[0:禁用/1:启用]
NODE_TLS_REJECT_UNAUTHORIZED=0

## knex
# knex调试开关
DEBUG=knex:query
# knex客户端类型
KNEX_CLIENT=mysql

## mysql
# mysql服务器地址
MYSQL_HOST=localhost
# mysql用户名
MYSQL_USER=root
# mysql密码
MYSQL_PASSWORD=
# mysql数据库名
MYSQL_DATABASE=test
# mysql端口
MYSQL_PORT=3306

## PM2
PM2_EXEC_INTERPRETER=babel-node
PM2_EXEC_MODE=fork
PM2_INSTANCES=1
PM2_WATCH=true

## watcher
# 是否使用watcher监控
WATCHER_ENABLE=false
# watcher服务信息
WATCHER_HOST=
WATCHER_PORT=
WATCHER_PREFIX=

## cors
# 是否允许前端跨域请求开关
CORS_ENABLE=true
# 允许跨域的域名，多个用英文逗号连接，*表示允许所有域名
CORS_ORIGIN=*
# 支持的HTTP请求动作类型，多个用英文逗号连接
CORS_ALLOW_METHODS=GET

## pug
# 是否使用pug模版
PUG_ENABLE=true
# pug模版位置
PUG_PAGES_PATH=src/templates/pages

## model 特性配置
# 让 Model 具有返回虚拟字段的功能
MODEL_VIRTUALS＝false
# 让 Model 调用 toJSON 方法时具有显示／隐藏某些字段的功能
MODEL_VISIBILITY＝false
# 让 Model 具有分页功能
MODEL_PAGINATION＝false
# 让 Model 具有删除关联数据功能
MODEL_CASCADEDELETE＝false
# 让 Model 具有返回自定义字段的功能
MODEL_MASK＝false
# 让 Model 具有自动生成UUID的功能
MODEL_UUID＝false
#让 Model 具有自动存储序列化对象的能力
MODEL_JSONCOLUMNS＝false
# 让 Model 具有自动转换对象 key 拼写的能力
MODEL_MAGICCASE＝false
```