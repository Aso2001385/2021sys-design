```uml
@startuml

[*] --> メニューバー
state メニューバー {
 state login <<inputPin>>
 
 
 login --> 商品一覧ページ
 ||
 [*] --> カートの中 
 ||
 [*] --> 登録情報ページ
}





@enduml
```
