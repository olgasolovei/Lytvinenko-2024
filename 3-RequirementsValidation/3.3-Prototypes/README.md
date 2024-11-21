# Prototypes

@startuml
skinparam backgroundColor black
skinparam handwritten false
skinparam rectangle {
    BackgroundColor #2e2e2e
    BorderColor #FFFFFF
}

title Горизонтальний прототип системи моніторингу та безпеки

package "Моніторинг даних" {
    rectangle "Система спостереження" as ObservationSystem
    rectangle "Збір даних про температуру" as TemperatureData
    rectangle "Оновлення кожні 5 секунд" as TemperatureUpdate
    rectangle "Оповіщення про критичну температуру" as TempAlert

    ObservationSystem --> TemperatureData
    TemperatureData --> TemperatureUpdate
    TemperatureUpdate --> TempAlert
}

package "Розрахунок ризиків" {
    rectangle "Оцінка ризиків" as RiskEvaluation
    rectangle "Виявлення потенційної небезпеки" as HazardDetection
    rectangle "Інформування відповідальних осіб" as ResponsibleAlert

    RiskEvaluation --> HazardDetection
    HazardDetection --> ResponsibleAlert
}

package "Архів даних" {
    rectangle "Журнал подій" as EventJournal
    rectangle "Резервне копіювання" as BackupSystem

    EventJournal --> BackupSystem
}

note right of TemperatureData
    Система фіксує дані про зміну температури
end note

note right of TempAlert
    Система надсилає сповіщення про критичну температуру
end note

note right of RiskEvaluation
    Система аналізує дані для оцінки небезпеки
end note

note right of BackupSystem
    Система забезпечує безпечне зберігання резервних копій
end note

@enduml
