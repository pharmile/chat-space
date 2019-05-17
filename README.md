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
|name|string|null: false|

### Association

- has_many :messages
- has_many :groups, through: :group_members
- has_many :group_members

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null :false|

### Association

- has_many :messages
- has_many :users, through: :group_members
- has_many :group_members

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null :false, foreign_key :true|
|group_id|integer|null :false, foreign_key :true|
|body|text|
|image|string|

### Association

- belongs_to :user
- belongs_to :group

## group_membersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null :false, foreign_key :true|
|user_id|integer|null :false, foreign_key :true|

### Association
- belongs_to :group
- belongs_to :user

