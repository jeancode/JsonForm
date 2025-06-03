# Formulario Multi-Parte Animado (iOS Dark Mode)(En espera de implementar demo en un dominio externo)

Este proyecto implementa un formulario web interactivo dividido en múltiples pasos, con animaciones suaves entre ellos. Está diseñado con un esquema de colores oscuro al estilo iOS y permite confirmar los datos ingresados antes de exportarlos en formato JSON.

## Características

*   **Formulario Multi-Parte:** Divide un formulario largo en pasos más manejables para el usuario.
*   **Animaciones Suaves:** Transiciones animadas de deslizamiento y fundido (`transform`, `opacity`) entre cada paso para una experiencia de usuario fluida.
*   **Paso de Confirmación:** Un paso final que recopila y muestra todos los datos ingresados para revisión.
*   **Estilo Dark Mode (iOS):** Utiliza variables CSS para definir un esquema de colores oscuro elegante, similar a la interfaz de iOS.
*   **Diseño Responsivo:** Se adapta al ancho de diferentes dispositivos (aunque optimizado para un ancho máximo).
*   **Recopilación de Datos en Tiempo Real:** Almacena los datos ingresados en un objeto JavaScript a medida que el usuario llena los campos.
*   **Exportación JSON:** Permite visualizar los datos recopilados en formato JSON legible en el paso de confirmación.
*   **Altura Dinámica del Contenedor:** El contenedor de los pasos (`#form-step-container`) ajusta su altura dinámicamente al contenido del paso activo mediante JavaScript y una transición CSS, evitando saltos de diseño (agrandamiento/encogimiento) durante las transiciones.
*   **Navegación:** Botones "Anterior" y "Siguiente" con lógica para mostrar/ocultar y deshabilitar durante las transiciones o en los límites del formulario.
*   **Uso de Flexbox:** Empleado en el layout general, la disposición de los botones y, explícitamente añadido en las clases `.form-step` y `.confirmation-step`, para organizar los elementos hijos verticalmente.
*   **Validación Básica:** Incluye una validación simple para asegurar que los campos de entrada de texto/número no estén vacíos antes de avanzar.

## Cómo Usar

1.  Guarda el código HTML completo proporcionado en un archivo con extensión `.html` (por ejemplo, `formulario.html`).
2.  Abre el archivo `.html` en cualquier navegador web moderno.
3.  Interactúa con el formulario:
    *   Usa el botón "Siguiente" para pasar al siguiente campo o al paso de confirmación.
    *   Usa el botón "Anterior" para regresar al paso anterior.
    *   En el paso de confirmación, haz clic en "Exportar JSON" para ver los datos ingresados formateados.

## Tecnologías Utilizadas

*   HTML5
*   CSS3 (Incluyendo Flexbox)
*   JavaScript (Vanilla JS)

## Personalización

*   **Campos del Formulario:** Modifica el array `formDataStructure` dentro de la etiqueta `<script>` para cambiar los campos (nombre, tipo, ID) que componen el formulario.
*   **Estilos:** Ajusta las variables CSS en la sección `:root` o modifica las reglas de estilo existentes para cambiar la apariencia, colores, fuentes, espaciado, etc.
*   **Validación:** Amplía la lógica de validación en la función `nextView()` para incluir validaciones más complejas o personalizadas.
*   **Exportación:** Adapta la función `collectDataAndShowJson()` para enviar los datos a un endpoint de servidor, guardarlos localmente, o realizar cualquier otra acción necesaria con la información.

## Notas y Posibles Mejoras

*   La implementación actual es un archivo HTML autocontenido para simplicidad. Para proyectos más grandes o complejos, sería mejor separar el HTML, CSS y JavaScript en archivos distintos.
*   La validación de campos es básica; se podría mejorar con mensajes de error específicos para cada campo y tipo de validación.
*   El manejo del estado del formulario se realiza directamente con variables JavaScript (`currentStepIndex`, `formDataValues`). Para aplicaciones con más estado o complejidad, un patrón de gestión de estado (como Redux, Vuex, Context API de React, etc., si se integrara en un framework) podría ser beneficioso.
*   La transición de altura, aunque funcional, puede verse menos suave si la diferencia de altura entre pasos es muy grande. Ajustar la duración de la transición puede ayudar.
