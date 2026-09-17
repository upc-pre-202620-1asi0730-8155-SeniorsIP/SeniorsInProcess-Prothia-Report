# Capítulo V: Product Implementation, Validation & Deployment

## 5.1 Software Configuration Management

La gestión en **SeniorsInProcess (Prothia)** incluye el código fuente, documentación, prototipos y configuraciones del entorno de desarrollo de la plataforma web de monitoreo y seguimiento de rehabilitación de pacientes amputados. El proyecto contempla distintos productos digitales, incluyendo una Landing Page institucional, una aplicación web para clínicas de rehabilitación y centros ortopédicos, y servicios backend orientados al procesamiento de datos biomecánicos y de uso de prótesis en tiempo real. El equipo adopta prácticas basadas en GitFlow, Conventional Commits y Semantic Versioning, asegurando un flujo de trabajo colaborativo y organizado.

### 5.1.1. Software Development Environment Configuration

| Categoría / Actividad | Nombre del Producto | Propósito de Uso en el Proyecto | Tipo / Plataforma | Ruta de Referencia / Descarga |
|---|---|---|---|---|
| Project Management | Trello | Gestión e itinerario de tareas del proyecto mediante tableros organizados por estados (To-Do, In Progress, Done), clave para el seguimiento de entregables como el reporte y la landing page. | SaaS | https://trello.com |
| Team Communication | Discord | Plataforma principal de comunicación remota para la realización de reuniones de equipo sincrónicas, planificación de Sprints y coordinación general. | SaaS / Desktop | https://discord.com/ |
| Requirements Management | Miro | Estructuración de ideas, diagramación de flujos de sistema, análisis del negocio y ejecución de la sesión de Event Storming para el ecosistema IoT. | SaaS | https://miro.com |
| Requirements Management | Structurizr | Modelado de la arquitectura de software del sistema DomotiCore bajo el modelo C4, representando los componentes clave (dashboard, gateway, nodos IoT y servicios de monitoreo). | SaaS / Desktop | https://structurizr.com |
| Product UX/UI Design | Figma | Diseño visual y prototipado interactivo de las interfaces del sistema, incluyendo el dashboard centralizado, paneles de control de dispositivos y visualización de consumo energético. | SaaS / Desktop | https://www.figma.com |
| Product UX/UI Design | Lucidchart | Elaboración de diagramas de flujo de trabajo, arquitectura técnica y diseño de procesos operativos del sistema. | SaaS | https://www.lucidchart.com |
| Software Development | HTML5 / CSS3 / JavaScript | Lenguajes y estándares base utilizados para el desarrollo del frontend web, las interfaces de usuario y la Landing Page del producto. | Lenguajes / Estándares | https://developer.mozilla.org/es/docs/Web |
| Software Development | WebStorm | Entorno de desarrollo integrado (IDE) principal utilizado para la programación, edición y depuración del código fuente del frontend. | Desktop | https://www.jetbrains.com/webstorm/download |
| Software Testing | Gherkin | Lenguaje de especificación para definir escenarios de prueba BDD (Behavior-Driven Development) basados en historias de usuario (control remoto, automatizaciones por horario y alertas de consumo). | Estándar / DSL | https://cucumber.io/docs/gherkin/reference |
| Software Documentation | GitHub | Repositorio central del proyecto para el control de versiones distribuido, registro de commits, trabajo colaborativo y alojamiento de la documentación del sistema. | SaaS | https://github.com |
| Software Deployment | GitHub Pages | Servicio de alojamiento y despliegue continuo para la Landing Page pública del producto, permitiendo exponer la propuesta de valor de DomotiCore. | SaaS | https://pages.github.com |

### 5.1.2 Source Code Management

La gestión de código fuente del proyecto **Prothia (SeniorsInProcess)** se realiza mediante la plataforma **GitHub**, permitiendo un control de versiones en entorno de trabajo colaborativo. Se han definido repositorios independientes para cada producto digital.

#### 5.1.2.1 Repositories

| Product | Repository URL | Description |
| :--- | :--- | :--- |
| **Organization** | [SeniorsInProcess-Prothia-1ASI0729](https://github.com/SeniorsInProcess-Prothia-1ASI0729) --- [https://github.com/SeniorsInProcess-Prothia-1ASI0729] --- | Organización donde se ubican todos los repositorios del proyecto. |
| **Landing Page** | [Prothia-Business-Web-Page](https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-LandingPage) --- [https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-LandingPage] --- | Repositorio de la Landing Page institucional del proyecto. |
| **Frontend Web Application** | [Prothia-Front-End](https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Frontend) --- [https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Frontend] --- | Aplicación web para el monitoreo y seguimiento de la rehabilitación de pacientes amputados. |
| **Backend Web Services** | [Prothia-Back-end](https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Backend) --- [https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Backend] --- | API REST y lógica de procesamiento de datos biomecánicos y de uso de prótesis. |
| **Documentation Repository** | [Prothia-Report](https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Report/tree/develop) --- [https://github.com/upc-pre-202620-1asi0730-8155-SeniorsIP/SeniorsInProcess-Prothia-Report/tree/develop] --- | Documentación técnica, reportes y entregables del proyecto. |
---
<div style="text-align:center;"><img src="../assets/organization-photo.png" width="800" alt="GitHub Repository Structure"></div>

#### 5.1.2.2 GitFlow Workflow

El equipo adopta **GitFlow** como estrategia de branching para mantener la estabilidad.

* **Main Branch**: Contiene únicamente versiones estables y aprobadas del proyecto listas para producción.
    * `main`
* **Develop Branch**: Rama principal de integración donde se consolidan las funcionalidades desarrolladas antes de integrarse en producción.
    * `develop`
* **Feature Branches**: Cada nueva funcionalidad se desarrolla en una rama independiente para evitar conflictos en el código base.
    * **Naming Convention**: `feature/<feature-name>`
    * **Examples**: `feature/patient-monitoring-dashboard`, `feature/biomechanical-data-tracking`
* **Hotfix Branches**: Ramas de emergencia para corregir errores críticos detectados directamente en producción.
    * **Naming Convention**: `hotfix/<issue-description>`

#### 5.1.2.3 Semantic Versioning

El proyecto utiliza **Semantic Versioning 2.0.0** para controlar las versiones de los productos digitales de Prothia.

| Version | Description |
| :--- | :--- |
| **v1.0.0** | Primera versión estable y funcional del producto. |
| **v1.1.0** | Incorporación de nuevas funcionalidades menores. |
| **v1.1.1** | Corrección de errores menores. |
| **v2.0.0** | Cambios mayores que incluyen modificaciones estructurales incompatibles. |

#### 5.1.2.4 Conventional Commits

Se adopta el estándar de **Conventional Commits** para mantener un historial de cambios limpio y fácil de verificar por el equipo.

| Prefix | Purpose |
| :--- | :--- |
| **feat** | Implementación de nuevas funcionalidades. |
| **fix** | Corrección de errores o bugs. |
| **docs** | Actualizaciones en la documentación del repositorio. |
| **style** | Cambios que no afectan la lógica (espaciados, formatos, CSS). |
| **refactor** | Reestructuración del código existente sin cambiar su funcionalidad. |
| **test** | Corrección de pruebas unitarias o de integración. |

**Examples:**
* `feat: implement patient rehabilitation dashboard`
* `docs: update sprint 1 documentation`
* `fix: correct biomechanical data sync error`
* `style: improve clinic panel spacing`

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

Durante este primer sprint, el equipo se enfocó en la implementación de la Landing Page de Prothia, estableciendo el principal canal de comunicación pública y captación para la plataforma biomecánica.  



#### 5.2.1.5. Execution Evidence for Sprint Review

Capturas de pantalla de la Landing Page implementada en vistas Desktop y Mobile, acompañadas del video demostrativo de navegación e interacción del sitio.
<div style="text-align:center;"><img src="../assets/Execution-Evidence-Landing.png" width="800" alt="Landing Page - Desktop"></div>

<div style="text-align:center;"><img src="../assets/Execution-Evidence-LandingMobile.png" width="400" alt="Landing Page - Desktop"></div>

link de la landing: https://upc-pre-202620-1asi0730-8155-seniorsip.github.io/SeniorsInProcess-Prothia-LandingPage/

link del video: https://upcedupe-my.sharepoint.com/:v:/g/personal/u202421065_upc_edu_pe/IQDNRf7YFyx2S7sfhe8y7z-aAemJubaEn3IlURxzwNnz_MM?e=NuhSGo