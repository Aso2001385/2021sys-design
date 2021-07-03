```uml
@startuml
skinparam activity {
  BackgroundColor<<big>> red
}

[*] --> メニューバー
state メニューバー {
 [*] --> 商品一覧ページ <<big>> 
}





@enduml
```
