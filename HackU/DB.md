# DB定義書

### ジャンルマスタ
genre
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ジャンルID|genre_id|int|〇|〇|||
|ジャンル名|genre_name|varchar(15)||〇|||

### タイプマスタ
type
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ジャンルID|genre_id|int|〇|〇|〇||
|タイプID|type_id|int|〇|〇|||
|タイプ名|type_name|varchar(15)||〇|||
|特徴|type_feature|text||〇||\*などで区切る|

## ユーザーテーブル
user
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ユーザーID|user_id|int|〇|〇||auto_inc|
|氏名|user_name|varchar(30)||〇|||
|メール|user_mail|varchar(30)||〇|||
|作成日時|user_created|date||〇|||
|更新日時|user_update|date||〇|||
|削除日|user_delete|date|||||

## ログインテーブル
login
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ログインID|login_id|varchar(30)|〇|〇||ユニーク、デフォはメアド|
|ユーザーID|user_id|int||〇|〇|userテーブルから|
|パスワード|login_pass|varchar(30)||〇|||
|作成日時|login_created|date||〇|||
|更新日時|login_update|date||〇||| 

## 履歴テーブル
history
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|ユーザーID|history_user_id|int|〇|〇|〇||
|作成日時|history_created|date|〇|〇|||
|タイプ名|history_type_name|int||〇||こちらにも保存する|
|テーマ名|history_theme|varchar(25)||〇|||
|特徴|history_feature|text||||\*などで区切る|
|テーマワード|history_idea|text||||\*などで区切る|
|結果|history_result|varchar(30)||||
