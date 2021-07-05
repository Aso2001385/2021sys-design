```uml
@startuml
!define Color_T #3399FF

skinparam class {
  BackgroundColor DarkGrey-Snow
  BorderColor Black
  ArrowColor Black
}

entity "購入テーブル" as purchase <<T,Color_T>> {
  + order_id [PK][NN]
  --
  order_id [NN]
  customer_code [NN]
  purchase_date [NN]
  total_price [NN]
}


@enduml
```
