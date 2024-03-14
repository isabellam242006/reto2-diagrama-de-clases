# Reto 2 - Diagrama de Clases

Para demostrar las diferentes diferencias entre relaciones, herencias y composiciones entre clases decidí hacerlo a través de lo que sería un sistema de créditos y cupos de materias.

Por ejemplo para demostrar lo que serían las relaciones, lo hice a través del siguiente diagrama:
```mermaid
classDiagram
     Sistema <-- Estudiante
     Estudiante <-- Profesor
     Sistema <-- Profesor
     Sistema : + Características visuales
     Sistema: + Plataforma interactiva
     Sistema : + Menú desplegable
     Sistema : +Mostrar datos personales()
     Sistema : + Guardar información sobre materias, cupos y créditos()
     Sistema : + Mostrar horario estudiante()

     Estudiante : +Nombre
     Estudiante : +ID
     Estudiante : +Género
     Estudiante : +Dirección
     Estudiante : +Teléfono
     Estudiante : +Agregar materias()
     Estudiante : +Cancelar materias()

     Profesor : +Nombre
     Profesor : +Materia que imparte
     Profesor : +Edad
     Profesor : +Género
     Profesor : +Impartir clases()
     Profesor : +Colocar notas()
```
Luego para demostrar lo que es la composiciónn, lo hice a partir de la clase materia, la cual está compuesta de un número de créditos, un número de cupos, un horario, un programa curricular y algunas características más:
```mermaid
classDiagram
    Materia *-- Créditos
    Materia *-- Cupos
    Materia *-- Horario
    Materia *-- Programa curricular
    Materia : +Número de cupos
    Materia:  +Código
    Materia : +Horario
    Materia : +Lugar asignado
    Materia : +Profesor asignado
    Materia : +Créditos
    Créditos : +Número de créditos
    Créditos : +Dificultad materia
    Créditos: +Equivalencia en tiempo de estudio
    Cupos: +Número de cupos
    Horario: +Día
    Horario: +Hora
    Programa curricular: +Temas a ver
    Programa curricular: +Fecha entrega trabajos
    Programa curricular: +Fecha entrega proyecto
    Programa curricular: +Fechas de parciales
```
Por último para demostrar la herencia, decidí hacerlo a partir de las diferentes facultades, las cuales a pesar de tener diferentes mallas curriculares se rigen por el mismo sistema. Esto quiere decir que cada facultad se rige por los mismos métodos para acceder al ingreso de materias con la diferencia de que cada facultad tiene características en su programa que los diferencia del resto.
```mermaid
classDiagram
   
    Sistema *-- Facultad
    Facultad <|-- Ingeniería
    Facultad <|-- Medicina
    Facultad <|-- Derecho
    Facultad <|-- Artes
    Facultad <|-- Ciencias
    Sistema : + Características visuales
    Sistema: + Plataforma interactiva
    Sistema : + Menú desplegable
    Sistema : +Mostrar datos personales()
    Sistema : + Guardar información sobre materias, cupos y créditos()
    Sistema : + Mostrar horario estudiante()
    Facultad : + Información programa

    Ingeniería : +Materias
    Ingeniería : +Ubicación en el campus
    Medicina : +Materias
    Medicina : +Ubicación en el campus
    Derecho : +Materias
    Derecho : +Ubicación en el campus
    Artes : +Materias
    Artes : +Ubicación en el campus
    Ciencias : +Materias
    Ciencias : +Ubicación en el campus
```
