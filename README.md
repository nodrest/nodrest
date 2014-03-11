# nodrest[node rest],没头


知识和生活没有头

> [](https://developer.atlassian.com/stash/docs/latest/how-tos/example-basic-authentication.html)

## 基础认证

`-u`参数，传递用户名密码

```bash
curl -D- -u fred:fred -X GET -H "Content-Type: application/json" http://localhost:7990/rest/api/1.0/projects
```

## 基础认证头

步骤如下:

* 创建表单username:password的字符
* Base64编码字符串
* 提供"Authorization"头，带"Basic "后面跟着编码字符, 如"Basic YWRtaW46YWRtaW4="

```bash
curl -D- -X GET -H "Authorization: Basic ZnJlZDpmcmVk" -H "Content-Type: application/json" http://localhost:7990/rest/api/1.0/projects
```

## OAuth2.0的令牌获取

```bash
curl -D- -X POST -H "grant-types:client_credentials" -H "token-types:bearer" http://localhost:9999/token
```
