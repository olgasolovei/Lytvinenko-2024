## діаграма варіантів використання
@startuml
actor "Інспектор з охорони праці" as Inspector
actor "Менеджер проєкту" as Manager
actor "Працівники будівництва" as Workers
actor "Система моніторингу" as MonitoringSystem

usecase "Моніторинг поточних погодних умов" as UC1
usecase "Створення звіту про ризики" as UC2
usecase "Оцінка ризиків при плануванні робіт" as UC3
usecase "Оновлення протоколу безпеки" as UC4
usecase "Перевірка дозволу на проведення робіт" as UC5
usecase "Ознайомлення з інструкціями безпеки" as UC6
usecase "Отримання даних від погодних сенсорів" as UC7
usecase "Збереження звітів та протоколів" as UC8
usecase "Перегляд історичних даних" as UC9

Inspector -- UC1
Inspector --> UC2 : "Створення на основі UC1"
Manager -- UC3
Manager --> UC4 : "Оновлення після UC3"
Workers -- UC5
Workers --> UC6 : "Перед початком роботи"
MonitoringSystem -- UC1 : "Дані про погоду"
UC1 ..> UC7 : "Запит даних"
UC2 ..> UC8 : "Зберігає звіт"
UC3 ..> UC9 : "Доступ до історії"
UC4 ..> UC8 : "Оновлює протокол"
UC5 ..> UC1 : "Перевіряє погодні умови"
UC6 ..> UC8 : "Перевіряє актуальність"
@enduml
