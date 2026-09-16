# Capítulo IV: Product Design
## 4.1. Style Guidelines
### 4.1.1. General Style Guidelines

*   **Branding:** Identidad centrada en la salud digital y la biomecánica, orientada a reducir la brecha de información entre pacientes amputados, clínicas de rehabilitación y centros ortopédicos.
*   **Typography:** La tipografía seleccionada es Montserrat para títulos y elementos destacados, por su claridad y estructura moderna. Para el cuerpo de texto se utiliza Inter a 14px con un interlineado de 1.5, garantizando una lectura fluida de los datos médicos. Los tamaños se adaptan al contexto web según la jerarquía: títulos, subtítulos y párrafos.

    *   **Escala:**
        <div align="center">
          <img src="../assets/Escala.png" alt="escala" width="250">
        </div>

    *   **Weights:**
        <div align="center">
          <img src="../assets/Weights.png" alt="weights" width="150">
        </div>

    *   **Nomenclatura:**
        <div align="center">
          <img src="../assets/Nomenclatura.png" alt="nomenclatura" width="250">
        </div>

    *   **Example:**
        <div align="center">
          <img src="../assets/Example.png" alt="example" width="500">
        </div>

*   **Colors:** La paleta de colores de Prothia prioriza la confianza médica, la tecnología y el progreso. El Azul Profundo transmite estabilidad y profesionalismo, usado en textos y fondos principales. El Teal (Verde Azulado) simboliza innovación y eficiencia, ideal para acentos y gráficos biomecánicos. El Verde Esmeralda incrementa la sensación de logro, siendo ideal para captar estados positivos o metas de rehabilitación cumplidas. Finalmente, el Gris Claro aporta orden y limpieza, usado en fondos secundarios y contenedores.

*   **Spacing:** El espaciado está diseñado para ofrecer una experiencia clara y ordenada, facilitando la lectura de historiales técnicos y datos biomecánicos en tiempo real:
    *   Entre secciones principales: mínimo 24px para marcar el cambio de contexto clínico.
    *   Entre encabezados y párrafos: 16px para reforzar jerarquía visual.
    *   Entre párrafos consecutivos: 14px para mantener continuidad y evitar bloques densos.
    *   Espaciado de botones e inputs: mínimo 10px entre elementos para garantizar usabilidad, especialmente en dispositivos móviles.

*   **Tono de comunicación:** Prothia transmite profesionalismo, empatía y proactividad, claves para un sistema que acompaña la adaptación a una prótesis:
    *   Profesional y analítico, de modo que sea comprensible para clínicas de rehabilitación y centros ortopédicos.
    *   Preventivo y confiable, orientado a alertar sobre posturas incorrectas sin generar alarma innecesaria.
    *   Empático y cercano, resaltando que la plataforma está diseñada para apoyar al paciente en su rutina diaria.

*   **Lenguaje aplicado:**
    *   Claro y directo, evitando tecnicismos ortopédicos complejos en la vista del paciente.
    *   Orientado a la acción, con instrucciones breves para los ejercicios de rehabilitación.
    *   Consistente en terminología médica, garantizando coherencia en alertas, reportes de desempeño y documentación técnica.
### 4.1.2. Web Style Guidelines

Elegimos una paleta basada en Azul Profundo, Teal / Verde Azulado, Verde Esmeralda y Gris Claro, porque queremos representar los valores de profesionalismo médico, tecnología, progreso y confianza. El Azul Profundo transmite estabilidad clínica y rigor, siendo el color principal de fondos de cabecera y tipografías para garantizar un alto contraste. El Teal simboliza la salud digital y la innovación, y es utilizado en botones primarios, elementos interactivos y trazados de gráficos biomecánicos. El Verde Esmeralda se reserva para indicadores de éxito, como la confirmación de ejercicios completados o posturas correctas. Finalmente, el Gris Claro se emplea como color de fondo en los dashboards, ofreciendo un lienzo limpio que evita la fatiga visual al revisar historiales clínicos y reportes de uso prolongado.

El uso balanceado de estos tonos asegura que la información clave, como las alertas de posturas inadecuadas o avisos de mantenimiento preventivo, sea rápidamente perceptible sin perder sobriedad visual. Los contrastes se aplican estratégicamente para mantener un diseño ordenado, moderno y fácil de interpretar por los tres actores del sistema: pacientes, profesionales de rehabilitación y técnicos ortopédicos.

En cuanto a la tipografía, dado que Prothia gestiona datos biomecánicos, historiales técnicos y programas de ejercicios, optamos por fuentes claras y contemporáneas. Montserrat se utiliza en títulos y encabezados para dar una estructura moderna y sólida, mientras que Inter se aplica en los cuerpos de texto y tablas de datos para maximizar la legibilidad. Los tamaños son lo suficientemente grandes para asegurar claridad en las métricas, utilizando variaciones de peso para guiar la atención del usuario en las pantallas de monitoreo.

<div align="center">
  <img src="../assets/Colors.png" alt="Paleta de Colores Web" width="250">
</div>

*   **Tipografía:** Se respetará la relación tipográfica y jerarquía establecida en los General Style Guidelines, combinando Montserrat e Inter.

*   **Responsive Design Standards:** Prothia está diseñado con una arquitectura adaptable para satisfacer los distintos contextos de uso de sus usuarios:
    *   **Mobile (360px – 768px)**
        *   Navegación tipo hamburguesa.
        *   Tarjetas de ejercicios y reportes apiladas en columna.
        *   Botones grandes y legibles, ideal para el paciente amputado que consulta su rutina y progreso desde el hogar mediante su smartphone.
    *   **Tablet (769px – 1024px)**
        *   Layout en 2 columnas.
        *   Menú lateral colapsable, optimizado para técnicos ortopédicos que visualizan datos de mantenimiento y ajustan parámetros desde el taller.
    *   **Desktop (1025px en adelante)**
        *   Menú principal siempre visible.
        *   Layout de 3 columnas en los dashboards clínicos, permitiendo a los fisioterapeutas analizar gráficos biomecánicos, métricas en tiempo real y listas de alertas de forma simultánea.

*   **Interactivity:**
    *   **Botones:**
        *   Bordes redondeados en 8px.
        *   Hover: cambio sutil de saturación en el color Teal y sombra suave para indicar interactividad.
        *   Feedback claro mediante animaciones sutiles al confirmar una tarea de rehabilitación o guardar un registro técnico.
    *   **Transiciones y animaciones:**
        *   Duración: 200–300ms.
        *   Curva: ease-in-out, asegurando fluidez al navegar entre fichas de pacientes y reportes de uso de prótesis.

*   **Accessibility:**
    *   Todo ícono debe tener alternativa textual (`aria-label` o `alt`) para herramientas de asistencia.
    *   Navegación totalmente compatible con teclado (Tab, Enter, Esc).
    *   Fuente mínima: 16px para garantizar legibilidad, considerando a pacientes que puedan tener dificultades visuales.
    *   Colores validados para asegurar un contraste suficiente (WCAG AA), permitiendo que textos sobre fondos claros como el Gris Claro se lean sin esfuerzo.

*   **UI Consistency:**
    *   Iconografía uniforme orientada a la salud y biomecánica, en estilo outline con grosor consistente.
    *   Botones y formularios con la misma geometría y espaciado en las interfaces del paciente, clínica y centro ortopédico.
    *   Uso consistente de la paleta semántica: Teal para acciones, Verde Esmeralda para éxito y estados óptimos, y colores de alerta (como rojo o naranja) exclusivamente para advertencias críticas de posturas inadecuadas o necesidades de mantenimiento en la prótesis.
    *   Estándar de espaciado basado en múltiplos de 8px para mantener un ritmo visual coherente y ordenado.

---
## 4.2. Information Architecture

### 4.2.1. Organization Systems

Para estructurar la gran cantidad de datos médicos y de sensores, Prothia utiliza los siguientes sistemas de organización:

*   **Organización Jerárquica:** Utilizada en los dashboards principales, donde se prioriza mostrar en la parte superior las alertas críticas (posturas incorrectas o mantenimientos urgentes), seguidas por los resúmenes de progreso biomecánico y, finalmente, los historiales detallados.
*   **Organización Secuencial:** Aplicada en los flujos de tareas paso a paso, como el registro de los datos clínicos de un paciente, la asociación de una prótesis a un usuario o la asignación de un plan de ejercicios.
*   **Organización Matricial:** Empleada en las vistas de analítica, permitiendo a los profesionales de rehabilitación cruzar datos de adherencia a los ejercicios con métricas de simetría de apoyo o cadencia a lo largo del tiempo.
### 4.2.2. Labeling Systems

El sistema de etiquetado en Prothia está diseñado para reducir la carga cognitiva, utilizando un lenguaje ubicuo que sea familiar tanto para el personal clínico como para el paciente en su hogar.

*   **Principios clave del sistema de etiquetado:**
    *   Se evitarán tecnicismos ortopédicos en la vista del paciente, utilizando términos claros como "Mis Ejercicios" o "Mi Progreso".
    *   Para las clínicas y ortopedias, se mantendrá la precisión técnica necesaria (ej. "Datos Biomecánicos", "Historial Técnico").
*   **Etiquetas principales por área:**
    *   **Navegación global:** Inicio, Pacientes, Prótesis, Monitoreo, Alertas, Mensajes.
    *   **Landing Page:** Soluciones, Para Clínicas, Para Ortopedias, Para Pacientes, Contacto.
    *   **Gestión de rehabilitación (Clínicas):** Asignar plan, Progreso de rehabilitación, Historial biomecánico.
    *   **Gestión técnica (Ortopedias):** Historial de uso, Programar mantenimiento, Estado del dispositivo.
    *   **Acciones del usuario:** Registrar paciente, Asociar prótesis, Generar reporte, Enviar mensaje, Configurar umbrales.
### 4.2.3. SEO Tags and Meta Tags

Para asegurar el posicionamiento de la Landing Page de Prothia y captar a los segmentos objetivo corporativos (clínicas y ortopedias), se han definido las siguientes etiquetas SEO:

*   **Title:** Prothia | Plataforma de Monitoreo Biomecánico y Rehabilitación
*   **Meta Description:** Conecta a pacientes amputados, clínicas de rehabilitación y centros ortopédicos. Optimiza el seguimiento remoto, analiza datos biomecánicos en tiempo real y gestiona el mantenimiento de prótesis con Prothia.
*   **Meta Keywords:** telerehabilitación, monitoreo biomecánico, pacientes amputados, prótesis, software clínico, mantenimiento ortopédico, salud digital.
*   **Meta Author:** SeniorsInProcess.