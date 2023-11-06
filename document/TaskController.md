# Task Controller 接口文档

## 展示所有任务

**URL**
- `GET /children/task/showAll`

**响应示例 - 有正在进行的任务**
```json
{
  "code": "666",
  "data": [
    {
      "id": "4",
      "score": 20,
      "startTime": "2023-11-03T21:51:26.000+00:00",
      "finishTime": "2023-12-03T21:51:28.000+00:00",
      "video": "video_url_4",
      "subject": "Math",
      "grade": "D",
      "status": "In Progress",
      "isMustDo": true,
      "content": "Task 4 content",
      "name": "Task 4",
      "taskPhoto": "photo_url_4"
    }
  ],
  "message": "查看所有时效的任务"
}
```

**响应示例 - 没有正在进行的任务**
```json
{
  "code": "0",
  "data": null,
  "message": "没有正在进行的任务"
}
```

## 显示必做任务（待定,先不要写对应的前端请求）

**URL**
- `GET /children/task/verifyGradeTask`

**请求参数**
- `child` (Child, 必需) - 孩子对象，包括年级等信息

**响应示例 - 有必做任务**
```json
{
  "code": "666",
  "data": [
    {
      "id": "example_task_id_3",
      "name": "任务3",
      "description": "任务3的描述",
      "grade": "example_grade",
      "finishTime": "2023-11-02T00:00:00.000Z",
      "isMustDo": 1
    }
  ],
  "message": "查看任务的必做和选做"
}
```

**响应示例 - 没有必做任务**
```json
{
  "code": "0",
  "data": null,
  "message": "没有正在进行的必做任务"
}
```

## 模糊查找任务（待定,先不要写对应的前端请求）

**URL**
- `GET /children/task/searchTask`

**请求参数**
- `subject` (String, 必需) - 学科名称

**响应示例 - 有匹配条件的搜索结果**
```json
{
  "code": "666",
  "data": [
    {
      "id": "example_task_id_4",
      "name": "任务4",
      "description": "任务4的描述",
      "grade": "example_grade",
      "finishTime": "2023-11-02T00:00:00.000Z",
      "subject": "example_subject"
    }
  ],
  "message": "查看模糊查询的结果"
}
```

**响应示例 - 没有匹配条件的搜索结果**
```json
{
  "code": "0",
  "data": null,
  "message": "没有匹配条件的搜索结果"
}
```
