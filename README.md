# テーブル設計


##  users テーブル

|  Column     | Type    | Options      |
| ----------- | ------- | ------------ |
| nickname    | string  | null: false  |
| email       | string  | null: false  |
| password    | string  | null: false  |
| first_name  | string  | null: false  |
| last_name   | string  | null: false  |
| first_kana  | string  | null: false  |
| last_kana   | string  | null: false  |
| bath_day    | date    | null: false  |

### Association
- has_many :items 




## items

| Colum           | Type    | Options                        |
| ----------------| ------- | ------------------------------ |
| item_name       | string  | null: false                    |
| price           | string  | null: false                    |
| item_rede       | text    | null: false                    |
| item_status     | string  | null: false                    |
| derivery_charge | integer  | null: false                   |
| derivery_source | integer  | null: false                   |
| derivery_days   | integer  | null: false                   |
| user_id         | integer | null: false,foreign_key: true  |
| category_id     | integer | null: false                    |

### Association

- belongs_to user
- belongs_to_active_hash :category
- 



## destinations

| Colum          | Type    | Options                        |
| -------------- | --------| ------------------------------ |
| post_code      | string  | null: false                    |
| prefecture     | string  | null: false                    |
| city           | string  | null: false                    |
| adress         | string  | null: false                    |
| building_name  | string  |                                |
| phone_number   | string  | null: false                    |
| order_id        | integer | null: false, foreign_key: true |

### Association

belongs_to :user


## orders   

| Colum         | Type    | Options                        |
| user_id       | integer | null: false, foreign_key: true |
| item_id       | integer | null: false, foreign_key: true |



- belongs_to :user
- belongs_to :item
- has_one : destinations


