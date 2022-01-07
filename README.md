## usersテーブル
| Column               | Type       | Options                   |
| -------------------- | ---------- | ------------------------- |
| email                | string     | null: false, unique: true |
| encrypted_password   | string     | null: false               |
| name                 | string     | null: false               |
| profile              | text       | null: false               |
| occupation           | text       | null: false               |
| position             | text       | null: false               |

### Association
- belongs_to :email
- belongs_to :encrypted_password
- belongs_to :name
- belongs_to :profile
- belongs_to :occupation
- belongs_to :position

## usersテーブル
| Column               | Type       | Options                   |
| -------------------- | ---------- | ------------------------- |
| email                | string     | null: false, unique: true |
| encrypted_password   | string     | null: false               |
| name                 | string     | null: false               |
| profile              | text       | null: false               |
| occupation           | text       | null: false               |
| position             | text       | null: false               |

### Association
- has_many :comments
- has_many :rooms, through: :comments
- has_many :prototypes

## commentsテーブル
| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| content     | text       | null: false                    |
| prototype   | references | null: false, foreign_key: true |
| user        | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototypes


## prototypesテーブル
| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments


