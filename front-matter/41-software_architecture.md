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

## 4.6.3. Software Architecture Container Diagrams

La solución se distribuye en cuatro containers principales: Landing Page, Web Application, RESTful API y Relational Database. La Landing Page utiliza HTML5, CSS3 y JavaScript para presentar el modelo de negocio y captar solicitudes públicas. La Web Application utiliza Vue 3, PrimeVue y JavaScript para proporcionar las experiencias autenticadas de los diferentes roles. El RESTful API utiliza ASP.NET Core, C# y Entity Framework Core para exponer servicios, aplicar reglas de negocio y coordinar persistencia e integraciones. La información relacional se almacena en PostgreSQL.

Los CTA de la Landing Page redirigen hacia la Web Application. Tanto los formularios públicos como la Web Application se comunican con el RESTful API mediante HTTPS y JSON. El RESTful API es el único container que accede a la base de datos y a los servicios externos.

C4 Container Diagram de Prothia.

![C4 Container Diagram Prothia](../assets/c4-container-diagram-prothia.png)

## 4.6.4. Software Architecture Components Diagrams

### Landing Page Components

La Landing Page se descompone en Navigation & Segment CTAs, Segment Content, Demo Request Form, Newsletter Form, Landing API Client e Internationalization & Accessibility. Los CTA dirigen a los visitantes hacia la experiencia correspondiente de la Web Application, mientras que Demo Request Form y Newsletter Form utilizan Landing API Client para registrar información mediante el RESTful API.

C4 Component Diagram - Landing Page.

![C4 Component Diagram Landing Page](../assets/c4-component-diagram-landing-page.png)

### Web Application Components

La Web Application separa Authentication & Access UI, Patient Experience, Clinic Experience, Orthopedic Experience y Subscription & License UI. Todas estas experiencias utilizan un API Client centralizado y comparten recursos de Internationalization & Accessibility, manteniendo una única vía de comunicación con el RESTful API.

C4 Component Diagram - Web Application.

![C4 Component Diagram Web Application](../assets/c4-component-diagram-web-application.png)

### RESTful API Components

El RESTful API organiza sus componentes principales de acuerdo con los Bounded Contexts identificados en el Design-Level EventStorming: Identity & Access Management, Rehabilitation Planning & Tracking, Service Execution & Biomechanical Monitoring, Profiles & Asset Management y Subscriptions & Payment Management.

Identity & Access Management API concentra registro, autenticación, sesiones y recuperación de contraseña. Rehabilitation Planning & Tracking API gestiona planes de rehabilitación, cumplimiento de ejercicios, progreso, compartición autorizada de información, reportes, exportaciones e indicadores de clínica. Service Execution & Biomechanical Monitoring API procesa telemetría, sesiones biomecánicas, evaluaciones de marcha, umbrales y alertas clínicas. Profiles & Asset Management API administra perfiles de paciente, prótesis, asociación paciente-prótesis, historial técnico y mantenimiento. Subscriptions & Payment Management API gestiona planes, suscripciones, licencias, pagos y vigencia de acceso institucional.

Además, Communication & Notification Support mantiene la mensajería y la bandeja general de notificaciones requeridas por las User Stories, mientras que Public Lead Management API soporta las solicitudes de demostración y las suscripciones al newsletter del Landing Page. Estos dos componentes actúan como módulos de soporte y no introducen Bounded Contexts adicionales.

Persistence Layer concentra el acceso mediante Entity Framework Core hacia PostgreSQL y External Integrations encapsula la comunicación con Payment Gateway, Email Service y Prosthesis Biomechanical Sensors (IMU).

C4 Component Diagram - RESTful API.

![C4 Component Diagram Restful Api](../assets/c4-component-diagram-restful-api.png)

### Relational Database Components

El container Relational Database se organiza mediante separación lógica de datos. Los esquemas identity_access, rehabilitation_tracking, biomechanical_monitoring, profiles_asset y subscriptions_payments corresponden a los cinco Bounded Contexts identificados. Los esquemas communication_notifications y public_leads mantienen la persistencia requerida por los módulos de soporte de comunicación y captación pública.

Esta organización permite conservar límites de responsabilidad a nivel de persistencia aun cuando PostgreSQL sea desplegado inicialmente como una única instancia.

C4 Component Diagram - Relational Database.

![C4 Component Diagram Relational Database](../assets/c4-component-diagram-relational-database.png)

## 4.7. Software Object-Oriented Design

El diseño orientado a objetos se organiza de acuerdo con los Bounded Contexts identificados en el Design-Level EventStorming y con los módulos de soporte necesarios para mantener trazabilidad con las User Stories del Capítulo III. Los nombres de clases, atributos, métodos e interfaces se mantienen en inglés y se especifican relaciones, multiplicidades y visibilidad de miembros.



