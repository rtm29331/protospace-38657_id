## users テーブル

| Column             | Type   | null        |UNIQUE   |　　
| ------------------ | ------ | ------------|---------|
| name               | string | null: false |true     |
| email              | string | null: false |false    |
| encrypted_password | string | null: false |false    |
| profile            | text   | null: false |false    |
| occupation         | text   | null: false |false    |
| position           | text   | null: false |false    |

### Association

- has_many :comments
- has_many :prototypes


## comments テーブル

| Column    | Type       | Options                        |
| ------    | ---------- | ------------------------------ |
| text      | text       | null: false, foreign_key: true |
| room      | references |                                |
| prototype | references |                                |
### Association

- belongs_to :prototype
- belongs_to :user

## prototyep テーブル

| Column     | Type       | Options                        |
| -----------| ---------- | ------------------------------ |
| title      | string     | null: false,                   |
| user       | references | null: false, foreign_key: true |
| catch.copy | text       | null: false,                   |
| concept    | text       | null: false,                   |

### Association

belongs_to :user
has_many :comments
 