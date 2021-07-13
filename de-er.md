```uml
@startuml
  !define Color_T Lime
  !define Color_M DeepSkyBlue

  skinparam class {
    BackgroundColor DarkGrey-Snow
    BorderColor Black
    ArrowColor Black
    IconFontColor Snow
  }
  
  package "資格一覧" as target_system{

    entity "学生テーブル" as sts <<T,Color_T>> {
        + sts_code [PK]
        --
        sts_name
    }
    
     entity "取得資格テーブル" as ces <<T,Color_T>>{
        + sts_code [PK][FK]
        + qus_code [PK][FK]
        --
        ces_date
    }

    entity "資格テーブル" as qus <<M,Color_M>>{
        + qus_code [PK]
        --
        qus_name
    }

  }
  
  sts ||-r-o{ ces
  ces }o-r-|| qus


   
  
@enduml
```

## 学生(sts)
|論理名|物理名|型|PK|FK|NN|デフォルト|備考|
|:---|:---|:---|:---:|:---:|:---:|---|---|
|学籍番号|id|int|Y||Y|||
|氏名|name|varchar(30)|||Y|||

## 取得資格(ces)
|論理名|物理名|型|PK|FK|NN|デフォルト|備考|
|:---|:---|:---|:---:|:---:|:---:|---|---|
|学籍番号|id|int|Y|Y|Y|||
|資格番号|id|int|Y|Y|Y|||
|取得日|ces_date|date|||Y|||

## 資格(qus)
|論理名|物理名|型|PK|FK|NN|デフォルト|備考|
|:---|:---|:---|:---:|:---:|:---:|---|---|
|資格番号|id|int|Y||Y|||
|資格名|name|varchar(50)|||Y|||
