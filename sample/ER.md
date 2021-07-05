```uml
@startuml
!define Color_Metal #F2F2F2-D9D9D9
!define Color_T #3399FF

skinparam class {
  BackgroundColor Color_Metal
  BorderColor Black
  ArrowColor Black
}

entity"購入テーブル" as purchase <<T,Color_T>> {
  + order_id [PK][NN]
  --
  order_id:bigint(20)[NN]
  customer_code:varchar(50)[NN]
  purchase_date:date[NN]
  total_price:int(11)[NN]
}


@enduml
```
