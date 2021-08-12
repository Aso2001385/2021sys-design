# DB定義書

### ジャンルマスタ
genre
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ジャンル番号|genre_id|int|〇|〇|||
|ジャンル名|genre_name|varchar(15)||〇|||

### タイプマスタ
type
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ジャンル番号|genre_id|int|〇|〇|〇||
|タイプ番号|type_id|int|〇|〇|||
|タイプ名|type_name|varchar(15)||〇|||
|特徴|type_text|text||〇||*などで区切る|

## ユーザーテーブル
user
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ユーザー番号|user_id|uuid(20)|〇|〇|||
|氏名|user_name|varchar(30)||〇|||
|メール|user_mail|varchar(30)||〇|||
|パスワード|user_pass|varchar(30)||〇||

## 履歴テーブル
history
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ユーザー番号|user_id|uuid(20)|〇|〇|||
|作成日時|user_name|varchar(30)||〇|||
|タイプID|type_id|int||〇|||
|特徴|history_text|||||
|結果|history_result|||||
