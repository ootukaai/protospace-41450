#テーブル設計


##usersテーブル


| Column             | Type       | Options                        |
| ----------------   | ---------- | ------------------------------ |
| email              | string     | null: false, unique: true      |
| name               | string     | null: false                    |
| profile            | text       | null: false,                   |
| occupation         | text       | null: false                    |
| position           | text       | null: false,                   |
| encrypted_password | string     | null: false                    |

### Association

- has_many :prototypes
- has_many :coments


##prototypesテーブル


| Column      | Type       | Options                        |
| ---------   | ---------- | ------------------------------ |
| title       | string     | null: false,                   |
| catch_copy  | text       | null: false,                   |
| user        | references | null: false, foreign_key: true |
| concept     | text       | null: false,                   |

### Association

- be_longs_to :user
- has_many :coments

##commentsテーブル


| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| content   | text       | null: false,                   |
| prototype | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

### Association

- be_longs_to :user
- be_longs_to :prototypes