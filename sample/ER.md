```uml
@startuml
!define Color_T Lime
!define Color_M DarkViolet

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

entity "顧客マスタ" as customers <<M,Color_M>> {
  + customer_code [PK][NN]
  --
  pass [NN]
  name [NN]
  address [NN]
  tel [NN]
  mail [NN]
  del_flag 
  reg_date [NN]
}

entity "カテゴリマスタ" as category <<M,Color_M>> {
  + category_id [PK][NN]
  --
  name [NN]
  reg_date [N]
}

entity "商品マスタ" as items <<M,Color_M>> {
  + item_code [PK][NN]
  --
  item_name [NN]
  price [NN]
  category_id [NN][FK]
  image [NN]
  detail
  del_flag
  reg_date [NN]
}

purchase ||-|{ purchase_detail
items }o-|| category
customers |o-o{ purchase
purchase_detail }--|| items

@enduml
```
