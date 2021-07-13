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

    entity "学生テーブル" as students <<T,Color_T>> {
        + student_number [PK]
        --
        student_name
    }

    entity "取得資格テーブル" as aquisition_license <<T,Color_T>>{
        + student_numbar [PK][FK]
        + license_code [PK][FK]
        --
        acquisition_date
    }

    entity "資格テーブル" as license <<T,Color_T>>{
        + license_code [PK]
        --
        license_name
    }

  }
  students |--r-o{ aquisition_license 
    aquisition_license }o-r--| license
@enduml
```
