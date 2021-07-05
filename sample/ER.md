```uml
@startuml
!define Color_T Lime-Snow

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

entity "購入詳細テーブル" as purchase_detail <<T,Color_T>> {
  + order_id [PK][NN][FK]
  + detail_id [PK][NN]
  --
  item_code [NN]
  price [NN]
  num [NN]
}

@enduml
```
