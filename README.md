# README

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
## usersテーブル

|Column|Type|Options|
|------|----|-------|
||integer|null: false, foreign_key: true|
|name|string|null:false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many:messages
- has_many:users_groups
- has_many:group,through:group_user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
||integer|null: false, foreign_key: true|
|text|text||
|image|text||
|user|reference|null: false,foreign_key: true|
|group|reference|null: false,foreign_key: true|

### Association
- belongs_to:user
- belongs_to:group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
||integer|null: false, foreign_key: true|
|name|string|null: false|

### Association
- has_many:users_groups
- has_many:users,through:group_user

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to:user
- belongs_to:group