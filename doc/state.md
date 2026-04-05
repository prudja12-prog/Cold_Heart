@startuml
skinparam state {
  BackgroundColor<<Winter>> #ADD8E6
  BackgroundColor<<Summer>> #A9FFA9
}

title Жизненный цикл климата Эренделла

[*] --> Лето : <<start>>

state "Лето" as Лето <<Summer>>
state "Вечная зима" as Зима <<Winter>>
state c <<choice>>

Лето --> c : Snow_Storm

c --> Зима : [эмоциональный сбой = true]
c --> Лето : [эмоциональный сбой = false]

Зима --> c : Sisterly_Love

c --> Лето : [сила любви >= сила магии]
c --> Зима : [сила любви < сила магии]

Лето --> [*] : стабильность

note left of c
  **Точка выбора (Choice)**
  Проверяет:
  - есть ли эмоциональный сбой
  - достаточно ли силы любви
end note

note right of Зима
  Состояние "Вечная зима"
  поддерживается магией Эльзы
end note

@enduml