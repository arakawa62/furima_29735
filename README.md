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
| bath_day    | string  | null: false  |

### Association
- has_many :items 
- belongs_to :destinations
- belongs_to :card


## items

| Colum           | Type    | Options                        |
| ----------------| ------- | ------------------------------ |
| item_name       | string  | null: false                    |
| price           | string  | null: false                    |
| item_rede       | string  | null: false                    |
| item_status     | string  | null: false                    |
| derivery_charge | string  | null: false                    |
| derivery_source | string  | null: false                    |
| derivery_days   | string  | null: false                    |
| user_id         | integer | null: false,foreign_key: true  |
| category_id     | integer | null: false, foreign_key: true |

### Association

- belongs_to user
- belongs_to category
- has_many :images



## destinations

| Colum          | Type    | Options                        |
| -------------- | --------| ------------------------------ |
| first_name     | string  | null: false                    |
| last_name      | string  | null: false                    |
| first_kana     | string  | null: false                    |
| last_kana      | string  | null: false                    |
| post_code      | string  | null: false                    |
| prefecture     | string  | null: false                    |
| city           | string  | null: false                    |
| adress         | string  | null: false                    |
| building_name  | string  |                                |
| phone_number   | string  |                                |
| user_id        | integer | null: false, foreign_key: true |

### Association

- belongs_to :user


## orders   

| Colum         | Type    | Options                        |
| ------------- | ------- | -------------------------------|
| price         | string  | null:false                     |
| created_at    | string  |                                |
| update_at     | string  |                                |


- belongs_to :user


## images 

| Colum        | Type    | Options                        |
| ------------ | ------- | ------------------------------ |
| image        | string  | null:false                     |
| item_id      | integer | null: false, foreign_key: true |

### Association

- belongs_to :items