```uml
@startuml

[*] --> 商品一覧(トップページ)
商品一覧(トップページ): あああ
商品一覧(トップページ) --> メニューバー
state メニューバー {
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
