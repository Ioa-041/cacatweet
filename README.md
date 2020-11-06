# cacatweet
**cacatweet**は猫カフェの感想や写真を共有するサイトです。

# 概要
このサイトは猫カフェに行った感想や写真を投稿できます。   
また店名で検索すると、そのお店だけのツイートを絞り込めます。

# URL

# テスト用アカウント

# 利用方法

# 目指した課題解決
猫好きでよく猫カフェを利用している人の  
「利用した時ことを写真付きで記録として残したい」や「猫好き同士で共有したい」という課題を解決したかった。  
また猫カフェに関する感想を色んなSNSから検索する人の手間を解決したかった。

# 洗い出した要件

# 実装した機能についてのGIFと説明

# 実装予定の機能

# データベース設計
## ER図
<img width="669" alt="ER図_cacatweet" src="https://user-images.githubusercontent.com/71744979/98339342-e6ffe500-204e-11eb-8b3b-21c28c0c433f.png">

## テーブル設計
## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_many :tweets
- has_many :messages

## tweets テーブル

| Column        | Type       | Options           |
| ------------- | ---------- | ----------------- |
| store         | string     | null: false       |
| prefecture_id | integer    | null: false       |
| station       | string     |                   |
| cat_name      | string     |                   |
| text          | string     |                   |
| user          | references | foreign_key: true |

### Association

- belongs_to :user
- has_many ::messages

## messages テーブル

| Column | Type       | Options           |
| ------ | ---------- | ----------------- |
| text   | string     | null: false       |
| user   | references | foreign_key: true |
| room   | references | foreign_key: true |

### Association

- belongs_to :tweet
- belongs_to :user

# ローカルでの動作方法