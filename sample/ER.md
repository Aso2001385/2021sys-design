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
  customer_code:varchar(50)[NN]
  purchase_date:date[NN]
  total_price:int(11)[NN]
}


@enduml
```
