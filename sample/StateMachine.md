```uml
@startuml
skinparam activity {
  StartColor red
}

[*] --> メニューバー
state メニューバー {
 [*] <<big>> --> 商品一覧ページ  
}





@enduml
```
