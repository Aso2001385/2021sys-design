```uml
@startuml
skinparam activity {
  StartColor<<big>> red
}

[*] --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ <<big>> 
}





@enduml
```
