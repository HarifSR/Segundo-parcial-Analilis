# UML Class Diagram - CADEP Database

```plantuml
@startuml 
title UML Class Diagram - CADEP Database

class Department {
  +id: Integer
  +name: String
}

class Municipality {
  +id: Integer
  +name: String
  --
  +departmentId: Integer
}

class State {
  +id: Long
  +name: String
}

class Role {
  +id: Integer
  +name: String
  +description: Text
  --
  +stateId: Long
}

class User {
  +id: Integer
  +name: String
  +password: String
  --
  +roleId: Integer
  +stateId: Long
}

class Branch {
  +id: Integer
  +name: String
  +phone: String
  --
  +municipalityId: Integer
  +departmentId: Integer
  +stateId: Long
}

class Area {
  +id: Integer
  +name: String
}

'--- Associations (foreign key relationships)

Municipality --> Department : belongs to >
Branch --> Municipality : located in >
Branch --> Department : located in >
Branch --> State : has status >
Role --> State : has status >
User --> Role : assigned >
User --> State : has status >
@enduml
