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
|id|integer|null: false, foreign_key: true|
|email|string|null: false|
|password|integer|null: false|

### Association
- has_many:tweets
- has_many:comments

## tweetsテーブル

|Column|Type|Options|
|------|----|-------|
|tweet_id|integer|null: false, foreign_key: true|
|text|text|null: false|
|user_id|string|null: false|

### Association
- belongs_to :user
- has_many :comments

## tweet_tagsテーブル

|Column|Type|Options|
|------|----|-------|
|tweets_id|integer|null: false, foreign_key: true|
|tags_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :tweet
- belongs_to :tag