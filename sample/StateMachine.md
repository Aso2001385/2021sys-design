```uml
@startuml

[*] --> トップページ
トップページ: 商品一覧
トップページ --> メニューバー
state メニューバー {
 商品一覧 --> [*]
 ||
 カートの中 --> [*]
 ||
 登録情報 --> [*]
}
メニューバー --> backpoint
backpoints --> メニューバー
backpoints --> [*]

@enduml
```
