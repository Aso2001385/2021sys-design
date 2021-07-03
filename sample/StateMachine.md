```uml
@startuml

[*] --> メニューバー
state メニューバー {
 state login <<inputPin>>
 state search <<inputPin>>
 state cart <<inputPin>>
 state mydata <<inputPin>>
 [*] --> 商品一覧ページ
 ||
 [*] --> カートの中 
 ||
 [*] --> 登録情報ページ
}





@enduml
```
