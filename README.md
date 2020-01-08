# README

## usersテーブル
|column|type|options|
|------|----|-------|
|name|string|null: fales, unique: true|
|e-mail|string|null: fales, unique: true|
|password|string|null: faless|

### Association
- has_many :messages
- has_many :groups, through:　:groups_users
- has_many :groups_users


## groupsテーブル
|column|type|options|
|------|----|-------|
|group-name|string|null, fales, unique: true|
|user_id|integer|foreign_key: true, null: faless|

### Association
- belongs_to :user
- has_many :messages
- has_many :users, through:　:groups_users
- has_many :groups_users


## messagesテーブル
|column|type|options|
|------|----|-------|
|message|text|
|image|string|
|user_id|integer|foreign_key: true, null: faless|
|group_id|integer|foreign_key: true, null: faless|

### Association
- belongs_to :user
- belongs_to :group


## groups_usersテーブル
|column|type|options|
|------|----|-------|
|user_id|integer|foreign_key: true, null: faless|
|group_id|integer|foreign_key: true, null: faless|

### Association
- belongs_to :user
- belongs_to :group
