# README

<!-- ChatSpace DB設計 -->例
<!-- usersテーブル -->
|colimn|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false| 
<!-- association -->
- has_many :messages
- has_many :groups, through: :users_groups
- has_many :users_groups

<!-- users_groupsテーブル -->
|colimn|Type|Options|
|------|----|-------|
|user|reference|null:false, foreign_key: true|
|group|reference|null: false, foreign_key: true|
<!-- association -->
- belongs_to :user
- belongs_to :group


<!-- groupsテーブル -->
|colimn|Type|Options|
|------|----|-------|
|name|string|null: false|
<!-- association -->
- has_many :messages
- has_many :users, through: :users_groups
- has_many :users_groups

<!-- messagesテーブル -->
|colimn|Type|Options|
|------|----|-------|
|text|text|
|picture|text|
|user|reference|null:false, foreign_key: true|
|group|reference|null: false, foreign_key: true|
<!-- association -->
- belongs_to :user
- belongs_to :group

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


