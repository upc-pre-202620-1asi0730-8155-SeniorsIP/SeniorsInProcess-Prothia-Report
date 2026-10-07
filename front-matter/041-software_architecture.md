## 4.6. Domain-Driven Software Architecture
### 4.6.1. Design-Level EventStorming

Para pasar del entendimiento general del negocio al diseño de la arquitectura del software, se desarrolló un Design-Level Event Storming. Este proceso se llevó a cabo en tres etapas consecutivas: identificación de Pivotal Points, definición de Aggregates y delimitación de Bounded Contexts.

#### Paso 1: Identificación de Eventos Clave y los Pivotal Points

![Pivotal Points](../assets/Pivotal%20Points.jpg)

##### Paso 2: Modelado de Agregados y Comandos

![Aggregates](../assets/Aggregates.jpg)

##### Paso 3: Delimitación de Contextos e Integraciones

![Bounded Contexts ](../assets/Bounded%20Contexts.jpg)


Miro: https://miro.com/app/board/uXjVHm-Fti8=/?share_link_id=426808403513

## 4.6.2. Software Architecture Context Diagram

El Context Diagram representa a Prothia como un único sistema de software y muestra a los principales actores y sistemas externos con los que interactúa. Los actores considerados son Visitor, Patient, Healthcare Professional (Médico/Fisioterapeuta), Orthopedic Technician (Técnico Ortopédico), Clinic Administrator y Orthopedic Center Admin, de acuerdo con las interacciones principales representadas en la solución. Esta separación permite reflejar las responsabilidades relacionadas con la consulta pública del Landing Page, el seguimiento de rehabilitación, el monitoreo clínico, la gestión técnica de prótesis y la administración de suscripciones institucionales.

Como sistemas externos se consideran Payment Gateway, Email Service, Prosthesis Biomechanical Sensors (IMU) y External Orthopedic Workshop Systems. El Payment Gateway procesa los pagos asociados a suscripciones y licencias; el Email Service soporta recuperación de contraseña y comunicaciones transaccionales; los sensores biomecánicos suministran la telemetría utilizada durante el monitoreo del paciente; y los sistemas de centros ortopédicos externos reciben reportes clínicos cifrados e interconsultas.

C4 System Context Diagram de Prothia.

![C4 System Context Diagram Prothia](../assets/c4-system-context-diagram-prothia.png)


