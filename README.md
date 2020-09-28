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
- has_many :orders




## items

| Colum               | Type    | Options                       |
| --------------------| ------- | ----------------------------- |
| name                | string  | null: false                   |
| price               | integer | null: false                   |
| rede_id             | integer | null: false                   |
| status_id           | integer | null: false                   |
| derivery_charge_id  | integer | null: false                   |
| derivery_source_id  | integer | null: false                   |
| derivery_days_id    | integer | null: false                   |
| user_id             | integer | null: false,foreign_key: true |
| category_id         | integer | null: false                   |

### Association

- belongs_to user
- belongs_to_active_hash :category
- belongs_to_active_hash :status
belongs_to_active_hash : derivery_charge
belongs_to_active_hash : derivery_source
belongs_to_active_hash :derivery_days
- has_one :order



## destinations

| Colum          | Type    | Options                        |
| -------------- | --------| ------------------------------ |
| post_code      | string  | null: false                    |
| prefecture_id  | integer | null: false                    |
| city           | string  | null: false                    |
| adress         | string  | null: false                    |
| building_name  | string  |                                |
| phone_number   | string  | null: false                    |
| order_id        | integer | null: false, foreign_key: true |

### Association

belongs_to :order


## orders   

| Colum         | Type    | Options                        |
| user_id       | integer | null: false, foreign_key: true |
| item_id       | integer | null: false, foreign_key: true |



- belongs_to :user
- belongs_to :item
- has_one : destination


