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

## 4.7.1. Class Diagrams

### Identity & Access Management

El modelo concentra UserAccount, UserSession y PasswordResetRequest. IdentityService implementa IIdentityService y coordina registro, autenticación, administración de sesiones y recuperación de contraseña. UserRole, AccountStatus y UserSessionStatus representan estados y roles válidos del dominio.

Class Diagram - Identity & Access Management.

![Class Diagram Identity Access Management](../assets/class-diagram-identity-access-management.png)

### Rehabilitation Planning & Tracking

RehabilitationPlan representa la planificación de rehabilitación del paciente y se relaciona con Exercise mediante PlanExercise. ExerciseLog registra el cumplimiento de la rutina. PatientDataShare representa la autorización para compartir información con el centro ortopédico. ClinicalReport y ReportFile representan la generación y resultado de reportes, mientras que ClinicIndicatorReadModel concentra los indicadores agregados requeridos para consulta.

RehabilitationTrackingService implementa IRehabilitationTrackingService y coordina las operaciones de asignación, cumplimiento, compartición y generación de información de seguimiento.

Class Diagram - Rehabilitation Planning & Tracking.

![Class Diagram Rehabilitation Planning Tracking](../assets/class-diagram-rehabilitation-planning-tracking.png)

### Service Execution & Biomechanical Monitoring

BiomechanicalSession representa una sesión de captura y agrupa BiomechanicalMeasurement. GaitAssessment almacena el resultado del análisis de movimiento, ThresholdRule mantiene los límites configurados por el profesional y ClinicalAlert representa una condición que requiere revisión clínica. BiomechanicalMonitoringService coordina ingesta, evaluación y administración de umbrales y alertas.

Class Diagram - Service Execution & Biomechanical Monitoring.

![Class Diagram Service Execution Biomechanical Monitoring](../assets/class-diagram-service-execution-biomechanical-monitoring.png)

### Profiles & Asset Management

PatientMedicalRecord representa la información de perfil utilizada por la clínica. Prosthesis representa el activo protésico y permite su asociación con un paciente. MaintenanceSchedule modela el mantenimiento programado, MaintenanceLog registra las intervenciones realizadas, ProsthesisUsageSummary mantiene información acumulada de uso y MaintenanceAlert representa condiciones de mantenimiento que requieren atención.

ProfilesAssetService implementa IProfilesAssetService y coordina creación de perfiles, registro y asociación de prótesis, programación de mantenimiento e intervenciones técnicas.

Class Diagram - Profiles & Asset Management.

![Class Diagram Profiles Asset Management](../assets/class-diagram-profiles-asset-management.png)

### Subscriptions & Payment Management

SubscriptionPlan representa la oferta contratada por una clínica, ClinicSubscription representa su acceso vigente y SoftwareLicense representa la licencia otorgada a un centro ortopédico. PaymentTransaction registra el resultado de cada operación de pago. SubscriptionPaymentService coordina contratación, licenciamiento, confirmación de pagos y vigencia de acceso.

Class Diagram - Subscriptions & Payment Management.

![Class Diagram Subscriptions Payment Management](../assets/class-diagram-subscriptions-payment-management.png)

### Communication & Notification Support

Message representa la comunicación entre usuarios y UserNotification concentra los elementos mostrados en la bandeja de notificaciones. CommunicationNotificationService coordina envío de mensajes, consulta de conversaciones y publicación/lectura de notificaciones originadas por eventos de otros contextos.

Class Diagram - Communication & Notification Support.

![Class Diagram Communication Notification Support](../assets/class-diagram-communication-notification-support.png)

### Public Lead Management

DemoRequest y NewsletterSubscription representan los dos flujos públicos de captación utilizados en la Landing Page. PublicLeadService registra las solicitudes de demostración y las suscripciones al newsletter.

Class Diagram - Public Lead Management.

![Class Diagram Public Lead Management](../assets/class-diagram-public-lead-management.png)

## 4.8. Database Design

El diseño de base de datos utiliza PostgreSQL como DBMS relacional y conserva la separación lógica establecida por los Bounded Contexts identificados en el Design-Level EventStorming. Los módulos de soporte mantienen su propia persistencia para conservar la trazabilidad con las User Stories especificadas en el Capítulo III.

Se utiliza lowercase_snake_case para tablas y columnas, UUID para identificadores, TIMESTAMPTZ para instantes que representan un momento real en el tiempo, DATE para fechas sin componente horario y NUMERIC para valores exactos. Los diagramas especifican claves primarias, claves foráneas internas, restricciones de unicidad, nulabilidad y reglas CHECK necesarias para mantener la integridad de los datos.

Las relaciones internas de cada Bounded Context se representan mediante claves foráneas. Cuando una entidad necesita identificar información administrada por otro contexto, se conserva únicamente el identificador como referencia lógica, evitando introducir dependencias de persistencia que mezclen responsabilidades de dominio.

### 4.8.1. Database Diagrams

#### Identity & Access Management

El modelo persiste cuentas de usuario, sesiones y solicitudes de recuperación de contraseña. El correo de cada cuenta y el hash de cada token de recuperación son únicos. Una cuenta puede originar múltiples sesiones y solicitudes de recuperación; las sesiones controlan su periodo de vigencia y las solicitudes conservan used_at en NULL mientras no hayan sido utilizadas.

Database Diagram - Identity & Access Management.

![Database Diagram Identity Access Management](../assets/database-diagram-identity-access-management.png)

#### Rehabilitation Planning & Tracking

El modelo persiste planes de rehabilitación, ejercicios, asignaciones de ejercicios, registros de cumplimiento, autorizaciones para compartir información, reportes clínicos, archivos generados y snapshots de indicadores de clínica. Cada plan contiene uno o más ejercicios mediante plan_exercise, donde la combinación de plan y ejercicio es única. Las frecuencias y repeticiones deben ser positivas y los rangos utilizados para reportes deben mantener una fecha final igual o posterior a la fecha inicial.

Los identificadores de paciente, profesional, clínica y centro ortopédico se mantienen como referencias lógicas cuando pertenecen a responsabilidades administradas por otros contextos.

Database Diagram - Rehabilitation Planning & Tracking.

![Database Diagram Rehabilitation Planning Tracking](../assets/database-diagram-rehabilitation-planning-tracking.png)

#### Service Execution & Biomechanical Monitoring

El modelo persiste sesiones biomecánicas, mediciones capturadas, evaluaciones de marcha, reglas de umbral y alertas clínicas. Cada sesión contiene una o más mediciones y puede producir como máximo una evaluación de marcha. Las alertas clínicas mantienen la sesión que originó el evento, mientras que las reglas de umbral se configuran por paciente y tipo de métrica.

Los límites configurados deben incluir al menos un valor mínimo o máximo y, cuando ambos existen, el máximo no puede ser menor que el mínimo.

Database Diagram - Service Execution & Biomechanical Monitoring.

![Database Diagram Service Execution Biomechanical Monitoring](../assets/database-diagram-service-execution-biomechanical-monitoring.png)

#### Profiles & Asset Management

El modelo persiste perfiles clínicos de pacientes, prótesis, programaciones de mantenimiento, intervenciones técnicas, resúmenes de uso y alertas de mantenimiento. Debido a que paciente y prótesis se administran dentro del mismo Bounded Context, la asociación entre ambos se representa mediante una clave foránea interna. La asociación es opcional mientras la prótesis permanezca disponible.

La referencia de cada prótesis es única y el uso acumulado no admite valores negativos. Las programaciones, intervenciones y alertas permanecen vinculadas a la prótesis correspondiente.

Database Diagram - Profiles & Asset Management.

![Database Diagram Profiles Asset Management](../assets/database-diagram-profiles-asset-management.png)

#### Subscriptions & Payment Management

El modelo persiste planes de suscripción, suscripciones de clínicas, licencias de software y transacciones de pago. Cada suscripción referencia el plan contratado y cada transacción corresponde a una suscripción o a una licencia, pero no a ambas simultáneamente. Esta exclusión se controla mediante una restricción CHECK.

Los importes deben ser positivos y las fechas de expiración deben ser posteriores al inicio del periodo contratado.

Database Diagram - Subscriptions & Payment Management.

![Database Diagram Subscriptions Payment Management](../assets/database-diagram-subscriptions-payment-management.png)

#### Communication & Notification Support

El módulo persiste mensajes y elementos de notificación. Los identificadores de emisor, destinatario y usuario se conservan como referencias lógicas a las cuentas administradas por Identity & Access Management. Las notificaciones pueden incluir una referencia lógica al evento o elemento que las originó y mantienen read_at en NULL hasta que el usuario las marque como leídas.

Database Diagram - Communication & Notification Support.

![Database Diagram Communication Notification Support](../assets/database-diagram-communication-notification-support.png)

#### Public Lead Management

El módulo persiste las solicitudes de demostración y las suscripciones al newsletter provenientes del Landing Page. Ambos procesos son independientes. Las solicitudes conservan la institución y los datos de contacto necesarios para su seguimiento, mientras que el correo utilizado para el newsletter mantiene una restricción de unicidad.

Database Diagram - Public Lead Management.

![Database Diagram Public Lead Management](../assets/database-diagram-public-lead-management.png)
