```uml
@startuml

[*]<<big>> --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ
 ||
 [*] --> カートの中 
 カートの中 --> endpoint
 ||
 [*] --> 登録情報ページ

}
メニューバー --> endpoint
endpoint --> メニューバー
endpoint --> [*]





@enduml
```
