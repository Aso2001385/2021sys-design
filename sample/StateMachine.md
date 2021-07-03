```uml
@startuml

[*] --> メニューバー
state メニューバー {
  state x <<fork>>
  [*] --> x
  x --> state1
  x --> state2
}





@enduml
```
