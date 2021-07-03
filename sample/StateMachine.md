```uml
@startuml
skinparam activity {
  StartColor<<big>> red
}

[*] --> メニューバー
state メニューバー {
 [*] <<big>> --> 商品一覧ページ  
}





@enduml
```
