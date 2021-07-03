```uml
@startuml
 center header <size:20><b>メイン</b></size>
 [*] --> トップページ
 トップページ: 商品一覧
 トップページ --> メニューバー
 state メニューバー {
   メニューバー: ID/PASS入力でログイン,各ボタンクリックで遷移
   商品一覧 -down-> カートの中
   カートの中 -up-> 商品一覧
   カートの中 -down-> 登録情報
   登録情報 -up-> カートの中

 }
 
@enduml
```

```uml
@startuml
 center header <size:20><b>商品一覧</b></size>
 
 [*] --> 

@enduml
```
