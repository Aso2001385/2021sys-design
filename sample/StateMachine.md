```uml
@startuml

[*]<<big>> --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ
 ||
 [*] --> カートの中 
 カートの中 --> backpoint
 ||
 [*] --> 登録情報ページ

}
メニューバー --> backpoints
backpoints --> メニューバー
backpoints --> [*]





@enduml
```
