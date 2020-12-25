# README

# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname               | string | null: false |
| email                  | string | null: false |
| password               | string | null: false |
| password_confirmation  | string | null: false |
| last-name              | string | null: false |
| first-name             | string | null: false |
| last-name-kana         | string | null: false |
| first-name-kana        | string | null: false |
| birth_data             | string | null: false |

- has_many :items
- has_many :buys_history

## items テーブル

| Column | Type   | Options     |
| ------ | ---------- | --------------------------------- |
| item-name                | string | null: false |
| item-info                | text | null: false   |
| item-category            | text | null: false   |
| item-sales-status        | text | null: false   |
| item-shipping-fee-status | text | null: false   |
| item-prefecture          | text | null: false   |
| item-scheduled-delivery  | text | null: false   |
| item-price               | text | null: false   |
| user                     | references | null: false, foreign_key: true |
| item-image |

- belongs_to :user
- has_one :buys_history

## buys_history テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| user | references | null: false, foreign_key: true         |
| item | references | null: false, foreign_key: true         |


- belongs_to :user
- belongs_to :items
- has_one :another_user

## another_users テーブル
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| card-number    | integer | null: false |
| card-exp-month | integer | null: false |
| card-exp-year  | integer | null: false |
| card-cvc       | integer | null: false |
| postal-code    | integer | null: false |
| prefecture     | text | null: false    |
| city           | text | null: false    |
| addresses      | text | null: false    |
| building       | text | null: false    |
| phone-number   | integer | null: false |
| buys_history   | references | null: false, foreign_key: true |


- belongs_to :buys_history