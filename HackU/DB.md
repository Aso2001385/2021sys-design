# DB定義書
[ER図]( https://github.com/Aso2001385/2021sys-design/blob/main/sample/ER.md )

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
|タイプ番号|type_id|int|〇|〇|||
|タイプ名|type_name|varchar(15)||〇|||
|ジャンル番号|genre_id|int|〇|〇|||


## 特徴マスタ
|和名|属性名|型|PK|NN|FK|備考|
|:---|:---|:---|:---:|:---:|:---:|:---|
|タイプ番号|type_id|int(20)|〇|〇|||
|特徴番号|type_name|varchar(15)|〇|〇|||

