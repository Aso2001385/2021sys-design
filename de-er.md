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

   
  
@enduml
```
