# 練習課題3：ToDoアプリのRESTful API仕様書

## エンドポイント一覧

| メソッド | エンドポイント | 内容 |
|---|---|---|
| GET | /tasks | タスク一覧を取得する |
| POST | /tasks | 新しいタスクを作成する |
| PUT | /tasks/{task_id} | タスクを更新する（完了状態への変更も含む） |
| DELETE | /tasks/{task_id} | タスクを削除する |

## リクエスト/レスポンス例

### POST /tasks（タスクを作成する）

リクエスト:
\`\`\`json
{
  "title": "牛乳を買う",
  "due_date": "2025-12-01"
}
\`\`\`

レスポンス:
\`\`\`json
{
  "task_id": 1,
  "title": "牛乳を買う",
  "due_date": "2025-12-01",
  "completed": false
}
\`\`\`

### PUT /tasks/{task_id}（タスクを完了にする例）

リクエスト:
\`\`\`json
{
  "completed": true
}
\`\`\`

レスポンス:
\`\`\`json
{
  "task_id": 1,
  "title": "牛乳を買う",
  "due_date": "2025-12-01",
  "completed": true
}
\`\`\`