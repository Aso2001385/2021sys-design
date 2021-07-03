```uml
@startuml
skinparam activity {
  StartColor red
}

[*]:ああ --> メニューバー
state メニューバー {
 [*] <<big>> --> 商品一覧ページ  
}





@enduml
```
