# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### アソシエーション

-has_many :prototypes
-has_many :comments

## prototype テーブル

| Column     | Type      | Options     |
| ---------- | --------- | ----------- |
| title      | string    | null: false |
| catch_copy | text      | null: false |
| concept    | text      | null: false |
| user       | reference | null: false |

### アソシエーション

-has_many   :comments
-belongs_to :user

## comment テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       |                                |
| user      | references | null: false                    |
| prototype | references | null: false                    |

### アソシエーション

-belongs_to :user
-belongs_to :prototype