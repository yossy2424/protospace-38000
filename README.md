## usersテーブル

| name       | string | option                   |
| ---------- | ------ | ------------------------ |
| email      | string | null: false unique: true |
| encrypted  | string | null: false              |
| name       | string | null: false              |
| profile    | text   | null: false              |
| occupation | text   | null: false              |
| position   | text   | null: false              |

has_many :prototype
has_many :comments

## prototypesテーブル

| name       | string     | option                         |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch-copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false ,foreign_key: true |

belong_to :users
has_many :comments

## commentsテーブル

| name      | string     | option                        |
| --------- | ---------- | ----------------------------- |
| content   | text       | null: false                   |
| prototype | references | null: false foreign_key: true |
| user      | references | null: false foreign_key: true |

belong_to :users
belong_to :comments

ゴール
コメントの投稿内容と名前の表示

保存すべてのコメントを表示する
@comments = @prototype.comments

each