# DB 設計

## users table

| Column     | Type   | Options     |
|------------|--------|-------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

* has_many :comments
* has_many :prototypes

## comments table

| Column    | Type       | Options           |
|-----------|------------|-------------------|
| text      | text       | null: false       |
| prototype | references | foreign_key: true | 
| user      | references | foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype

## prototypes table

| Column     | Type       | Options           |
|------------|------------|-------------------|
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| user       | references | foreign_key: true |

### Association

- belongs_to :user
- has_many :comments
