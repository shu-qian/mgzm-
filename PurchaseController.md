# Purchase Controller 接口文档

## 查看当前孩子的订单列表

**URL**
- `GET /children/purchase/list/{childId}`

**请求参数**
- `childId` (String, 必需) - 孩子的ID

**响应示例 - 成功检索订单列表**
```json
{
  "success": true,
  "message": "订单列表已成功检索",
  "data": [
    {
      "id": "example_id_1",
      "childId": "example_child_id_1",
      "value": 100,
      "date": "2023-11-04T10:00:00",
      "status": true,
      "subId": "example_sub_id_1",
      "subNum": 2
    },
    {
      "id": "example_id_2",
      "childId": "example_child_id_2",
      "value": 150,
      "date": "2023-11-05T14:30:00",
      "status": true,
      "subId": "example_sub_id_2",
      "subNum": 1
    }
  ]
}
```

**响应示例 - 该儿童没有任何订单**
```json
{
  "success": false,
  "message": "该儿童没有任何订单",
  "data": null
}
```

## 插入订单

**URL**
- `POST /children/purchase/add`

**请求体数据**
- `purchase` (Object, 必需) - 订单信息，包括 `childId`, `value`, `date`, `status`, `subId`, `subNum` 字段。

**请求示例**
```json
{
  "purchase": {
    "childId": "example_child_id",
    "value": 100,
    "date": "2023-11-04T10:00:00",
    "status": true,
    "subId": "example_sub_id",
    "subNum": 2
  }
}
```

**响应示例 - 订单添加成功**
```json
{
  "success": true,
  "message": "订单添加成功"
}
```

**响应示例 - 订单添加失败**
```json
{
  "success": false,
  "message": "订单添加失败"
}
```

这是Purchase Controller的接口文档示例，你可以根据实际需要进行修改和扩展。
