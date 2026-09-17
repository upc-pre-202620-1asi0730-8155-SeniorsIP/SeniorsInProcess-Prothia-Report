### 5.1.3. Source Code Style Guide & Conventions.

El uso de un estilo de código unificado y una arquitectura bien definida es clave para asegurar la escalabilidad, la mantenibilidad y la colaboración efectiva en el desarrollo de **Prothia**. Para ello, el proyecto incorpora prácticas de programación y convenciones estructurales que promueven la calidad técnica, la claridad y la consistencia en cada módulo de la plataforma, tomando como referencia estándares reconocidos de la industria y metodologías actuales.

#### Arquitectura y organización del sistema

Prothia adopta el modelo C4 de Simon Brown, lo que permite visualizar el sistema en distintos niveles de abstracción (contexto, contenedor, componente y código). Este enfoque ofrece una representación clara y comprensible, facilitando la comunicación entre desarrolladores, diseñadores y testers. Además, la arquitectura se fundamenta en los principios de Domain-Driven Design (DDD) y Clean Architecture, lo que garantiza una separación rigurosa entre capas (presentación, aplicación, dominio e infraestructura). Gracias a ello, se reduce el acoplamiento, se incrementa la mantenibilidad y se fortalece la capacidad de realizar pruebas automatizadas de manera eficiente.

#### Frontend: Vue.js

En el frontend, se emplea Vue.js como framework principal, implementando una arquitectura centrada en componentes reutilizables, organizados en directorios específicos como components, views y store. La convención de nombres establece el uso de PascalCase para los componentes (por ejemplo, PatientCard.vue) y kebab-case para los archivos (patient-card.vue), en concordancia con las recomendaciones de la comunidad Vue. Asimismo, se aplican buenas prácticas de desarrollo, entre ellas:

* Separación de lógica y presentación mediante el patrón container/presentational components.
* Uso de props y emits para la comunicación clara entre componentes.
* Implementación de lazy loading y code splitting para optimizar el rendimiento.
* Internacionalización con vue-i18n, gestionando archivos JSON para cada idioma.

#### Alineación con guías de estilo estándar

La estructura y nomenclatura utilizadas en Prothia siguen convenciones reconocidas como la Vue Style Guide y lineamientos generales de HTML/CSS. Además, el uso del inglés en identificadores, clases y funciones garantiza coherencia en el trabajo colaborativo, simplifica la integración con librerías externas y favorece la comprensión del código por parte de equipos internacionales.