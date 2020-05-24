## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|pssword|string|null: false|

### Association
- has_many :group, through: :groups_users
- has_many :messages

## group
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|

### Association
- has_many :user, through: :groups_users
- has_many :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messages

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string| |
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user