# Child Controller 接口文档

## 登录验证

**URL**
- `POST /children/child/loginChild`

**请求参数**
- `username` (String, 必需) - 用户名
- `password` (String, 必需) - 密码

**请求示例**
```json
{
  "username": "example_username",
  "password": "example_password"
}
```

**响应示例 - 成功登录**
```json
{
  "code": "666",
  "data": {
    "id": "example_id",
    "username": "example_username",
    "other_field": "other_value"
  },
  "message": "登录成功"
}
```

**响应示例 - 用户或密码错误**
```json
{
  "code": "0",
  "data": null,
  "message": "用户或密码错误"
}
```

**响应参数**
- `code` (String) - 响应代码，"666" 表示成功，"0" 表示失败。
- `data` (Object) - 用户信息，如果登录失败则为 `null`。
- `message` (String) - 响应消息。
```
