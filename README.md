## 版本说明
* Spring Boot 版本为 3.1.2
* spring-security-oauth2-authorization-server 版本为 1.0.0
* port 为9000

## 步骤
1、进行 authorization config 的编写

2、调用`http://localhost:9000/.well-known/oauth-authorization-server`进行测试查看对应的接口链接，实例结果
```json
{
    "issuer": "http://localhost:9000",
    "authorization_endpoint": "http://localhost:9000/oauth2/authorize",
    "token_endpoint": "http://localhost:9000/oauth2/token",
    "token_endpoint_auth_methods_supported": [
        "client_secret_basic",
        "client_secret_post",
        "client_secret_jwt",
        "private_key_jwt"
    ],
    "jwks_uri": "http://localhost:9000/oauth2/jwks",
    "response_types_supported": [
        "code"
    ],
    "grant_types_supported": [
        "authorization_code",
        "client_credentials",
        "refresh_token"
    ],
    "revocation_endpoint": "http://localhost:9000/oauth2/revoke",
    "revocation_endpoint_auth_methods_supported": [
        "client_secret_basic",
        "client_secret_post",
        "client_secret_jwt",
        "private_key_jwt"
    ],
    "introspection_endpoint": "http://localhost:9000/oauth2/introspect",
    "introspection_endpoint_auth_methods_supported": [
        "client_secret_basic",
        "client_secret_post",
        "client_secret_jwt",
        "private_key_jwt"
    ],
    "code_challenge_methods_supported": [
        "S256"
    ]
}
```

3、来到 OAuth 2.0 debugger https://oauthdebugger.com/ 和 OpenID Connect debugger https://oidcdebugger.com/ 填写对应的数据发起请求。实例（其中 status 为可选参数，写不写都可）

![image](https://github.com/QinJmon/authorization_server_demo1/assets/98678120/be9d497b-81cc-4547-bbee-c7b8f362c2eb)



发送请求之后的结果

![image](https://github.com/QinJmon/authorization_server_demo1/assets/98678120/bdd52cec-dc5b-455a-a0a9-0654e3789fed)



  
