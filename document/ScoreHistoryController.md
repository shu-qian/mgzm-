# ScoreHistory Controller 接口文档

## 获取孩子的积分总表

**URL**
- `GET /children/score-history/total-list/{childId}`

**请求参数**
- `childId` (String, 必需) - 孩子的ID

**响应示例 - 成功检索积分收支记录**
```json
{
  "success": true,
  "message": "该儿童的所有积分收支记录已成功检索",
  "data": [
    {
      "childId": "example_child_id_1",
      "eventTime": "2023-11-05T08:00:00",
      "score": 100,
      "eventType": "获得积分",
      "eventDetail": "任务对应学科"
    },
    {
      "childId": "example_child_id_2",
      "eventTime": "2023-11-05T12:30:00",
      "score": -50,
      "eventType": "支出积分",
      "eventDetail": "物品1 x 2"
    },
    {
       "childId": "1",
        "eventTime": "2023-11-03T23:29:51.000+00:00",
        "score": -20,
        "eventType": "支出积分",
        "eventDetail": "直尺 x 1"
    },
    {
        "childId": "1",
        "eventTime": "2023-11-02T15:19:28.000+00:00",
        "score": 1,
        "eventType": "获得积分",
        "eventDetail": "Math"
    } 
  ]
}
```

**响应示例 - 该儿童没有任何积分收支记录**
```json
{
  "success": false,
  "message": "该儿童没有任何积分收支记录",
  "data": null
}
```
