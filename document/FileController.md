## 上传任务子项照片

接口地址：`POST /children/file/uploadTaskChildPhoto`

### 请求参数

| 参数名   | 类型          | 是否必需 | 描述              |
| -------- | ------------- | -------- | ----------------- |
| childId  | String        | 是       | 子项ID            |
| taskId   | String        | 是       | 任务ID            |
| file     | MultipartFile | 是       | 要上传的文件      |

### 响应

- 成功响应：

  - 状态码：200 OK
  - 返回数据：

    ```json
    {
      "success": true,
      "message": "作业图片上传成功"
    }
    ```

- 失败响应：

  - 状态码：400 Bad Request
  - 返回数据：

    ```json
    {
      "success": false,
      "message": "作业图片上传失败"
    }
    ```

### 示例

请求：`POST /children/file/uploadTaskChildPhoto`
- Content-Type: multipart/form-data
   - childId=123456
   - taskId=987654
   - file=<文件内容>

响应：
`HTTP/1.1 200 OK`
- Content-Type: application/json

```json
{
"success": true,
"message": "作业图片上传成功"
}
```
或
`HTTP/1.1 400 Bad Request`
- Content-Type: application/json
```json
{
"success": false,
"message": "作业图片上传失败"
}
```
