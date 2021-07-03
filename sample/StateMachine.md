```uml
@startuml

[*] --> 商品一覧
商品一覧: あ
商品一覧 --> メニューバー
state メニューバー {
 [*] --> 商品一覧
 商品一覧 --> backpoint1
 ||
 カートの中 --> backpoint2
 ||
 登録情報 --> backpoint3
}
メニューバー --> backpoints
backpoints --> メニューバー
backpoints --> [*]

@enduml
```
