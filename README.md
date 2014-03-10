# nodrest[node rest],没头


知识和生活没有头

## Stash REST API Example - Basic Authentication

Stash allows REST clients to authenicate themselves with a user name and password using basic authentication.

### Simple example

Most client software provides a simple mechanism for supplying a user name and password and will build the required authentication headers automatically. For example you can specify the -u argument with curl as follows

```bash
curl -D- -u fred:fred -X GET -H "Content-Type: application/json" http://localhost:7990/rest/api/1.0/projects
```

### Supplying Basic Auth headers

If you need to you may construct and send basic auth headers yourself. To do this you need to perform the following steps:
Build a string of the form username:password

### Base64 encode the string

Supply an "Authorization" header with content "Basic " followed by the encoded string, e.g. "Basic YWRtaW46YWRtaW4="

```bash
curl -D- -X GET -H "Authorization: Basic ZnJlZDpmcmVk" -H "Content-Type: application/json" http://localhost:7990/rest/api/1.0/projects
```

## Authentication challenge

Some http client software expects to receive an authentication challenge before it will send an authorization header and this may mean that it may not behave as expected. In this case you may need to configure it to supply the authorization header as described above rather than relying on its default mechanism.

## OAuth2.0的令牌获取

```bash
curl -D- -X POST -H "grant-types:client_credentials" -H "token-types:bearer" http://localhost:9999/token
```
