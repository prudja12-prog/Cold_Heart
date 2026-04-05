@startuml
left to right direction

actor "Эльза" as Elsa
actor "Анна" as Anna
actor "Жители Эренделла" as Citizens

package "Управление климатом" {
  usecase "Создать снежную бурю" as SnowStorm
  usecase "Заморозить замок" as FreezeCastle
  usecase "Создать Олафа" as CreateOlaf
  usecase "Страдать от холода" as Suffer
  usecase "Активировать сестринскую любовь" as SisterLove
  usecase "Растопить зиму" as MeltWinter
}

Elsa --> SnowStorm
Elsa --> FreezeCastle
Elsa --> CreateOlaf

Citizens --> Suffer

Anna --> SisterLove
Anna --> MeltWinter

SnowStorm <.. FreezeCastle : <<extend>> : при эмоц. сбое
FreezeCastle ..> CreateOlaf : <<include>>

Suffer <.. SnowStorm : <<extend>> : если зима

SisterLove ..> MeltWinter : <<include>>
MeltWinter <.. SnowStorm : <<extend>> : если есть зима

@enduml