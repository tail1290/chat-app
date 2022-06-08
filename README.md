<!-- # テーブル設計 -->

<!-- ##users_table -->

| Column             | Type   | Option      |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

<!-- ### Association -->

- has_many :room_users
- has_many :rooms,through: :room_users
- has_many :messages


<!-- ## rooms_table -->

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

<!-- ### Association -->

- has_many :room_users
- has_many :rooms,through: :room_users
- has_many :messages


<!-- ## rooms_tale -->

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

<!-- ### Association -->

- belong_tp :room
- belong_to :user


<!-- ## messages_table -->

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

<!-- ### Association -->

- belong_tp :room
- belong_to :user