# Purchase Controller 接口文档

## 查看当前孩子的订单列表/消耗积分记录

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
      "id": "1",
      "subId": "subject1",
      "subPhoto": "photo1.jpg",
      "name": "物品1",
      "value": 200,
      "status": true
    },
    {
      "id": "3",
      "subId": "subject3",
      "subPhoto": "photo3.jpg",
      "name": "物品3",
      "value": 75,
      "status": true
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
- `purchase` (Object, 必需) - 订单信息，包括 `childId`, `value`, `subId`, `subNum` 字段。
- 插入自动生成订单创建时间和订单状态（创建初始为进行中）

**请求示例**
```json
{
  "purchase": {
    "childId": "example_child_id",
    "value": 100,
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

