### Recomendaciones

1. Continuar la implementación de Prothia priorizando las funcionalidades que aparecieron con mayor frecuencia e importancia durante el needfinding, especialmente el seguimiento de planes de rehabilitación, visualización de datos biomecánicos, generación de alertas y gestión del mantenimiento preventivo de las prótesis.

2. Implementar en los siguientes sprints la primera versión funcional de la Web Application manteniendo el acceso diferenciado por roles definido en los requisitos y en la arquitectura, de manera que pacientes, profesionales clínicos y técnicos ortopédicos accedan únicamente a la información y funciones correspondientes a sus responsabilidades.

3. Desarrollar progresivamente el RESTful API y la persistencia de datos respetando los Bounded Contexts, componentes, clases y esquemas definidos durante el diseño técnico, evitando introducir dependencias innecesarias entre responsabilidades de dominio.

4. Realizar pruebas de usabilidad con usuarios representativos de los tres segmentos antes de considerar definitivas las interfaces desarrolladas en Figma. Estas pruebas deben permitir comprobar especialmente la facilidad para interpretar dashboards, consultar progreso, identificar alertas y acceder a información relacionada con mantenimiento.

5. Durante las siguientes entregas, ejecutar las entrevistas de validación y evaluaciones heurísticas necesarias para contrastar las Hypothesis Statements y los criterios de éxito definidos durante Lean UX. Los resultados deberán utilizarse para corregir assumptions que no coincidan con el comportamiento observado de los usuarios.

6. Validar progresivamente la forma en que se obtendrán y procesarán los datos biomecánicos, comenzando con datos controlados o simulados cuando sea necesario y posteriormente comprobando la integración con sensores compatibles, debido a que la disponibilidad y precisión de esta información representa una parte esencial de la propuesta de valor de Prothia.

7. Mantener durante el desarrollo las prácticas de control de versiones establecidas para el proyecto, utilizando ramas de trabajo, mensajes de Conventional Commits y versiones identificables para facilitar la revisión de la participación del equipo y la trazabilidad entre requisitos, implementación y entregas.

8. Utilizar la Landing Page desplegada como primer canal para presentar la propuesta de valor y captar interés de clínicas y centros ortopédicos, pero evitar utilizar su publicación como evidencia de validación del producto completo, debido a que las principales funciones de Prothia todavía requieren implementación y evaluación con usuarios reales.

9. Actualizar las conclusiones en cada entrega incorporando únicamente nueva evidencia obtenida durante el desarrollo y la validación. De esta manera, las conclusiones actuales de AV1 podrán contrastarse posteriormente con los resultados de la Web Application, Web Services, entrevistas de validación y versión final del producto.
