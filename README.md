# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| name      | string | null: false |
| password  | string | null: false |
| name      | string | null: false |
| profile   | text   | null: false |
| occupation| text   | null: false |
| position  | text   | null: false |

### Association

- has_many :prototype
- has_many :comments

## prototype テーブル

| Column     | Type      | Options                |
| -----------| ----------| ---------------------- |
| title      | string    | null: false            |
| catch.copy | text      | null:false             |
| concept    | text      | null:false             |
| user       | references| null:false,foreign_key  |

### Association

- has_many :comments
- belong :users


## comments テーブル

| Column  | Type       | Options                |
| ------- | ---------- | -----------------------|
| text    | text       | null: false            |
| user    | reference  | null:false,foreign_key |
### Association

- belongs_to :users
- belongs_to :pyototype
