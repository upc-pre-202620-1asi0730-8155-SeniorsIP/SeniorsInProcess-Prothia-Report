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
