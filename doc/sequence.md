@startuml
title Пошаговое взаимодействие в системе "Холодное сердце"

actor "Эльза" as E
participant "СистемаКлимата" as S
participant "Замок" as Castle
participant "Олаф" as Olaf
actor "Анна" as A

E -> S ** : создатьБурю()
note right: переход в состояние EternalWinter

E -> Castle ** : заморозить()
note right: состояние = "заморожен"

E -> Olaf ** : создатьОлафа()
note right: состояние = "оживлён"

A -> S : активироватьЛюбовь()

alt Любовь сильнее магии
    S -> S : растопитьЗиму()
    note over S #A9FFA9: Система вернулась к Summer
else Любовь недостаточна
    S -> S : поддерживатьЗиму()
    note over S #FFAAAA: Вечная зима продолжается
end

@enduml