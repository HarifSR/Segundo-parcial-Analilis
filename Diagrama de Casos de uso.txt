login


@startuml
title Caso de Uso - Login

actor Colaborador

usecase "Iniciar sesión" as UC_Login

Colaborador --> UC_Login

note right of UC_Login
Debe tener un rol asignado (secretaría, enfermero o terapeuta).
Debe ingresar un correo electrónico y contraseña válida.
end note

@enduml


REGISTRO DE PACIENTES


@startuml
title Caso de Uso - Registro de Pacientes

actor Secretaria
actor Enfermero

usecase "Registrar paciente" as UC_RegistroPaciente

Secretaria --> UC_RegistroPaciente
Enfermero --> UC_RegistroPaciente

note right of UC_RegistroPaciente
Debe verificar que el paciente no exista previamente en el sistema.
end note

@enduml



REGISTRO Y CONTROL DE TERAPIAS

@startuml
title Caso de Uso - Registro y Control de Citas

actor Secretaria
actor Enfermero

usecase "Agendar cita para paciente" as UC_Cita

Secretaria --> UC_Cita
Enfermero --> UC_Cita

note right of UC_Cita
Validar que el paciente esté registrado.
Verificar disponibilidad del horario.
end note

@enduml



REGISTRO DE TERAPIAS

@startuml
title Caso de Uso - Registro de Terapias

actor Terapeuta

usecase "Registrar resultado de terapia" as UC_Terapia

Terapeuta --> UC_Terapia

note right of UC_Terapia
Debe registrar el resultado de la sesión y programar la próxima cita.
end note

@enduml
