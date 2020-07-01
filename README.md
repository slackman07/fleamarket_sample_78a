# README


# bicycle DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|mail|string|null: false|
|password|string|null: false|
|last_name|string|null: false|
|first_name|string|null: false|
|last_name_furi|string|null: false|
|first_name_furi|string|null: false|
|birth|date|null: false|
|send_last_name|string|null: false|
|send_first_name|string|null: false|
|send_last_name_furi|string|null: false|
|send_first_name_furi|string|null: false|
|post|numeric|null: false|
|prefecture|string|null: false|
|city|string|null: false|
|block|string|null: false|
|building|string||
|phone|string||
### Association
- has_many :product
- belongs_to :card

## productsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text|null: false|
|brand|string||
|name|text|null: false, foreign_key: true|
|explanation|text|null: false|
|status|string|null: false|
|delivery_fee|numeric|null: false, foreign_key: true|
|delivery_area|text|null: false|
|delivery_day|text||
|price|numeric|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :categorie

## categoriesテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|ancestry|integer|null: false, foreign_key: true|
### Association
- has_many :product

## cardsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|text|null: false|
|customer_id|integer|null: false, foreign_key: true|
|card_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user