# TaskChild Controller 接口文档

## 获取孩子的已提交未批改任务
(由于数据库变更，后端方法待修改，届时请求参数可能略有修改)

**URL**
- `GET /children/task-child/submitted-uncorrected/{childId}`

**请求参数**
- `childId` (String, 必需) - 孩子的ID

**响应示例 - 已成功检索已提交未批改任务**
```json
{
  "success": true,
  "message": "该儿童已提交的未批改任务已成功检索",
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
  ]
}
```

**响应示例 - 该儿童没有已提交的未批改任务**
```json
{
  "success": false,
  "message": "该儿童没有已提交的未批改任务",
  "data": null
}
```

## 获取孩子的已批改任务

**URL**
- `GET /children/task-child/corrected/{childId}`

**请求参数**
- `childId` (String, 必需) - 孩子的ID

**响应示例 - 已成功检索已批改任务**
```json
{
  "success": true,
  "message": "该儿童已提交的已批改任务已成功检索",
  "data": [
    {
      "id": "3",
      "score": 80,
      "startTime": "2023-11-04T14:00:00.000+00:00",
      "finishTime": "2023-11-04T16:00:00.000+00:00",
      "video": "video_url_3",
      "subject": "English",
      "grade": "C",
      "status": "Not Started",
      "isMustDo": true,
      "content": "Task 3 content",
      "name": "Task 3",
      "taskPhoto": "photo_url_3"
    }
  ]
}
```

**响应示例 - 该儿童没有已提交的已批改任务**
```json
{
  "success": false,
  "message": "该儿童没有已提交的已批改任务",
  "data": null
}
```
