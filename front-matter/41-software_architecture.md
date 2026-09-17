## 4.6. Domain-Driven Software Architecture
### 4.6.1. Design-Level EventStorming
En esta sección se presenta la arquitectura de software de Prothia desde el enfoque de Domain-Driven Design, tomando como base el Big Picture Event Storming desarrollado previamente.

**Identity & Access Management**
<br>
<br>
![Level EventStorming2](../assets/ES-Identity%20&%20Access%20Management.jpeg)
<br>
<br>
**Subscriptions & Payment Management**
<br>
<br>
![Level EventStorming2](../assets/ES-Subscriptions%20&%20Payment%20Management.jpeg)
<br>
<br>
**Profiles & Asset Management**
<br>
<br>
![Level EventStorming3](../assets/ES-Profiles%20&%20Asset%20Management.jpeg)
<br>
<br>
**Service Execution & Biomechanical Monitoring**
<br>
<br>
![Level EventStorming4](../assets/ES-Service%20Execution%20&%20Biomechanical%20Monitoring.jpeg)
<br>
<br>
**Rehabilitation Planning & Tracking**
<br>
<br>
![Level EventStorming5](../assets/ES-Rehabilitation%20Planning%20&%20Tracking.jpeg)

## 4.6.2. Software Architecture Context Diagram

El Context Diagram representa a Prothia como un único sistema de software y muestra a los principales actores y sistemas externos con los que interactúa. Los actores considerados son Visitor, Patient, Clinic User y Orthopedic Center User, de acuerdo con las interacciones principales representadas en la solución. Esta separación permite reflejar las responsabilidades relacionadas con la consulta pública del Landing Page, el seguimiento de rehabilitación, el monitoreo clínico y la gestión de prótesis y mantenimiento.

Como sistemas externos se consideran Payment Gateway, Email Service y Prosthesis Biomechanical Sensors (IMU). El Payment Gateway procesa los pagos asociados a suscripciones y licencias; el Email Service soporta recuperación de contraseña y comunicaciones transaccionales; y los sensores biomecánicos suministran la telemetría utilizada durante el monitoreo del paciente.

C4 System Context Diagram de Prothia.

![C4 System Context Diagram Prothia](../assets/c4-system-context-diagram-prothia.png)
