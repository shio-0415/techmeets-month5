# API仕様書

## エンドポイント一覧

| No | メソッド | エンドポイント | 内容 |
|---|---|---|---|
| 1 | GET | /tasks | タスク一覧を取得する |
| 2 | POST | /tasks | 新しいタスクを作成する |
| 3 | PUT | /tasks/{タスクID} | タスクを更新する |
| 4 | DELETE | /tasks/{タスクID} | タスクを削除する |
| 5 | POST | /users | 会員登録する |
| 6 | POST | /login | ログインする |
| 7 | POST | /logout | ログアウトする |
| 8 | GET | /tags | タグ一覧を取得する |
| 9 | POST | /tags | 新しいタグを作成する |
| 10 | GET | /statuses | 状態一覧を取得する |

## リクエスト/レスポンス例

### POST /tasks（タスクを作成する）

リクエスト:
\`\`\`json
{
  "title": "ES提出",
  "tag_id": 1,
  "status_id": 1,
  "due_date": "2025-12-01",
  "estimated_minutes": 60
}
\`\`\`

レスポンス:
\`\`\`json
{
  "task_id": 15,
  "user_id": 3,
  "title": "ES提出",
  "tag_id": 1,
  "status_id": 1,
  "due_date": "2025-12-01",
  "estimated_minutes": 60,
  "progress": 0
}
\`\`\`

### POST /login（ログインする）

リクエスト:
\`\`\`json
{
  "email": "taro@example.com",
  "password": "password123"
}
\`\`\`

レスポンス:
\`\`\`json
{
  "user_id": 3,
  "name": "田中太郎"
}
\`\`\`

### GET /tasks（タスク一覧を取得する）

リクエスト:
`GET /tasks?user_id=3`（ログイン中のユーザーIDを指定する。JSONのボディは不要）

レスポンス:
\`\`\`json
[
  {
    "task_id": 15,
    "user_id": 3,
    "title": "ES提出",
    "tag_id": 1,
    "status_id": 1,
    "due_date": "2025-12-01",
    "estimated_minutes": 60,
    "progress": 0
  },
  {
    "task_id": 16,
    "user_id": 3,
    "title": "レポート提出",
    "tag_id": 2,
    "status_id": 2,
    "due_date": "2025-12-05",
    "estimated_minutes": 120,
    "progress": 50
  }
]
\`\`\`