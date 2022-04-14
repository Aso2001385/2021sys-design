```uml
@startuml
!define Color_T Lime
!define Color_R Red
!define Color_C DeepSkyBlue

skinparam class {
  BackgroundColor DarkGrey-Snow
  BorderColor Black
  ArrowColor Black
  IconFontColor Snow
}

  entity "ユーザーテーブル" as users {
    + id [PK]
    --
    name
    email
    password
    master_flag
    created_at
    updated_at	
    deleted_at
  }
  
    entity "スキルテーブル" as skills {
    + id [PK]
    --
    type
    name
    version
    created_at
    updated_at	
    deleted_at
  }


  entity "キャリアテーブル" as careers {
    + id [PK]
    --
    user_id
    skill_id
  }

  entity "クライアントテーブル" as clients {
    + id [PK]
    -- 
    name
    created_at
    updated_at	
    deleted_at
  }
  
  entity "案件テーブル" as matters {
    + id [PK]
    --
    client_id
    name
    start_at
    end_at
    created_at
    updated_at	
    deleted_at
  }
  
  users ||-l-o{ skills
  users ||-r-o{ careers
  skills ||-d-o{ careers
  clients ||-d-o{ matter
  
