# DB定義書
## ER図
[ER図]( https://github.com/Aso2001385/2021sys-design/blob/main/sample/ER.md )

### purchase
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---:|:---:|:---:|
|オーダー番号|order_id|bigint(20)|〇|〇||
購入日付|purchase_date|date|〇|||
合計金額|total_price|int(11)|〇|||

###purchase_detail
オーダー番号|order_id|bigint(20)|〇|〇|〇|
明細番号|detail_id|bigint(20)|〇|〇||
商品コード|item_code|int(11)|〇|〇||
商品価格|price|int(11)|〇|||
数量|num|int(11)|〇|||

###customers
顧客コード|customer_code|varchar(50)|〇|〇||
パスワード|pass|varchar(50)|〇|||
名前|name|varchar(20)|〇|||
住所|address|varchar(100)|〇|||
電話番号|tel|varchar(20)|〇|||
メールアドレス|mail|varchar(100)|〇|||
削除フラグ|del_flag|int(11)||||
登録日|reg_date|date|〇|||

###category
カテゴリid|category_id|int(11)|〇|〇||
カテゴリ名|name|varchar(20)|〇|||
登録日|reg_date|date|〇|||

###items
商品コード|item_code|int(11)|〇|〇||
商品名|item_name|varchar(50)|〇|||
価格|price|int(11)|〇|||
カテゴリid|category_id|int(11)|〇|〇||
イメージ|image|varchar(200)|〇|||
商品説明|detail|varchar(500)||||
削除フラグ|del_flag|int(11)||||
登録日|reg_date|date|〇|||
