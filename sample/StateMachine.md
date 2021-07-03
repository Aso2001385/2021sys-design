```uml
@startuml

[*] --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ
 商品一覧ページ --> backpoint1
 ||
 カートの中 ---> backpoint2
 ||
 登録情報ページ ---> backpoint3
}
メニューバー --> backpoints
backpoints --> メニューバー
backpoints --> [*]

@enduml
```
