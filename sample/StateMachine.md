```uml
@startuml
 center header <size:20><b>メイン</b></size>
 [*] --> メニューバー
 state メニューバー {
   メニューバー: ID/PASS入力でログイン,各ボタンクリックで遷移
   [*] -> 商品一覧
   note "商品検索で商品一覧に遷移" as N1
   note "ログインボタンクリックで必ず商品一覧ページに遷移" as N2
   商品一覧 -down-> カートの中
   カートの中 -up-> 商品一覧
   カートの中 -down-> 登録情報
   登録情報 -up-> カートの中
   商品一覧 -right-> 登録情報
   商品一覧 -[hidden]> 登録情報
   登録情報 -left-> 商品一覧
   登録情報 -[hidden]> 商品一覧
   

 }
 
@enduml
```

```uml
@startuml
 center header <size:20><b>商品一覧</b></size>
 
 [*] --> 

@enduml
```
