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
  
  sts ------ qus 
  qus ------ ces


   
  
@enduml
```
