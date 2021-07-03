```uml
@startuml

[*] --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ
 商品一覧ページ --> backpoint
 ||
 [*] --> カートの中 
 カートの中 --> backpoint
 ||
 [*] --> 登録情報ページ
 登録情報ページbackpoint
}
メニューバー --> backpoints
backpoints --> メニューバー
backpoints --> [*]

@enduml
```
