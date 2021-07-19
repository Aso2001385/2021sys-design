```uml
@startuml
 center header <size:20><b>ログアウト処理</b></size>
  ユーザー -> Webサーバー:ログアウト
  Webサーバー -> DBサーバー:ログアウト申請
  DBサーバー -> DBサーバー:ログアウト処理
  DBサーバー -> Webサーバー:ログアウト処理結果
  Webサーバー ->ユーザー:ログアウトメッセージ表示
@enduml
```
```uml
@startuml
 center header <size:20><b>商品サーチ処理</b></size>
 alt 商品一覧

 ユーザー -> Webサーバー:商品一覧閲覧
 Webサーバー -> DBサーバー:全商品情報要求
 DBサーバー -> DBサーバー:商品情報抽出処理
 DBサーバー -> Webサーバー:抽出結果
 Webサーバー -> ユーザー:商品一覧表示

 else 商品検索
  ユーザー -> Webサーバー:商品検索
  alt 商品名
   Webサーバー -> DBサーバー:商品情報要求(商品名送信)
  else カテゴリ
   Webサーバー -> DBサーバー:商品情報要求(カテゴリ送信)
  end
  DBサーバー -> DBサーバー:対象商品情報抽出処理
  DBサーバー -> Webサーバー:抽出結果
  Webサーバー -> ユーザー:対象商品一覧表示
 end
@enduml
