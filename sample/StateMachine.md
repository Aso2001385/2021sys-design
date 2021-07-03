```uml
@startuml
 center header <size:20><b>メイン</b></size>
 [*] --> メニューバー
 state メニューバー {
   メニューバー: ID/PASS入力でログイン,各ボタンクリックで遷移
   [*] --> 商品一覧
   state 商品一覧 {
    [*] --> 一覧ページ
    [*] -[dotted]-> 商品詳細ページ: 「カートの中」から直接遷移
    一覧ページ -right-> 商品詳細ページ: 画像および商品名をクリック
    商品詳細ページ -left-> 一覧ページ: 「前のページに戻る」をクリック
    商品詳細ページ -right-> [*]: 「カートに入れる」をクリック
    
   }
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
