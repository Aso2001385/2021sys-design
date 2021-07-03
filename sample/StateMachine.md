```uml
@startuml

[*] --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ
 カートの中 --> backpoint
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
