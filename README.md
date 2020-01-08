# README

## usersテーブル
|column|type|options|
|------|----|-------|
|name|string|null: false, unique: true|
|e-mail|string|null: false, unique: true|
|password|string|null: false|

### Association
- has_many :messages
- has_many :groups, through:　:groups_users
- has_many :groups_users


## groupsテーブル
|column|type|options|
|------|----|-------|
|name|string|null, false, unique: true|

### Association
- has_many :messages
- has_many :users, through:　:groups_users
- has_many :groups_users


## messagesテーブル
|column|type|options|
|------|----|-------|
|message|text|
|image|string|
|user_id|integer|foreign_key: true, null: false|
|group_id|integer|foreign_key: true, null: false|

### Association
- belongs_to :user
- belongs_to :group


## groups_usersテーブル
|column|type|options|
|------|----|-------|
|user_id|integer|foreign_key: true, null: false|
|group_id|integer|foreign_key: true, null: false|

### Association
- belongs_to :user
- belongs_to :group
