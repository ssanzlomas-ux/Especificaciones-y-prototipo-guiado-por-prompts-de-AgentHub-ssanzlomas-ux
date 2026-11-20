# Plan de implementación — AgentHub

## Objetivo
Construir un prototipo visual e interactivo del panel de administración de AgentHub, basado en `specs/dashboard/spec.md` y tomando `DESIGN.md`, `screen.png` y el HTML exportado por Google Stitch como referencias visuales. El entregable final será un único `index.html`.

Los datos serán ficticios, hardcodeados y coherentes entre secciones. No representan datos reales del cliente ni implican conexiones a servicios.

## Stack y restricciones
- HTML semántico en un único archivo `index.html`.
- Tailwind CSS cargado exclusivamente mediante CDN.
- JavaScript vanilla para toda la interactividad.
- Sin frameworks, jQuery, herramientas de build, backend ni dependencias adicionales.
- Usar clases/utilidades Tailwind para los estilos. Se permiten estilos inline solo cuando una necesidad concreta no pueda resolverse razonablemente con Tailwind; justificar ese uso.
- Mantener como referencia la dirección visual de Stitch: estética “Executive Precision”, fondos slate, acento índigo, tipografía Inter, bordes finos, superficies limpias y componentes compactos.
- Adaptar la interfaz a pantallas pequeñas; las tablas deben poder desplazarse horizontalmente cuando sea necesario.

## Plan por etapas

### 1. Integración visual y estructura
- Trasladar al `index.html` los patrones visuales útiles de Stitch: sidebar persistente, barra superior y área de contenido.
- Preparar seis vistas: Dashboard, Usuarios, Agentes, Skills, Contrataciones y Log de errores.
- Aplicar la identidad visual y las reglas de responsive descritas arriba.
- En esta etapa se establece la estructura y presentación; no se implementa aún la lógica de las interacciones.

### 2. Contenido de las seis secciones
- **Dashboard:** cuatro tarjetas de métricas (ingresos, pérdidas por descuentos/cupones, agentes activos y agentes fallando) y área de ancho completo como placeholder del gráfico semanal.
- **Usuarios:** tabla con al menos cinco usuarios; nombre, email, plan, estado y datos adicionales suficientes para el modal de detalle.
- **Agentes:** listado con al menos cuatro agentes; nombre, propietario, estado, skills y prompt de sistema editable.
- **Skills:** catálogo con al menos cuatro skills; nombre, descripción y cantidad de agentes habilitados, más una explicación breve del concepto.
- **Contrataciones:** tabla con al menos cuatro contratos; cliente, agente, skills, fechas de inicio y fin e importe. Preparar precios por skill y total para el desglose.
- **Log de errores:** al menos seis entradas con timestamp, agente, tipo/gravedad, descripción y traza simulada.
- Mantener consistencia entre los nombres de usuarios, propietarios, agentes, skills, clientes y contratos.

### 3. Navegación
- Hacer que los seis enlaces de la sidebar cambien la vista sin recargar la página.
- Reflejar la vista seleccionada mediante un indicador visual activo y actualizar el título o breadcrumb de la barra superior.
- Comprobar que la navegación funciona después de interactuar con los componentes de la página.

### 4. Dropdowns de acciones
- Añadir un menú `⋮` por fila o elemento donde lo exige el briefing: Usuarios, Agentes, Skills, Contrataciones y Log de errores.
- Incluir las opciones específicas de cada sección: «Ver detalle»/«Eliminar», «Configurar»/«Eliminar» o «Ver detalle»/«Marcar como resuelto».
- Cerrar los menús al hacer clic fuera.
- Implementar las acciones destructivas como simulaciones seguras, sin backend, con confirmación o aviso visible.

### 5. Modales
- Implementar un componente modal reutilizable para los detalles y la configuración.
- Usuarios: mostrar el registro completo.
- Agentes: mostrar el prompt de sistema en un `<textarea>` editable.
- Skills: mostrar información completa de la capacidad.
- Contrataciones: presentar el desglose de skills y sus precios individuales, además del total.
- Errores: mostrar la información y la traza completa simulada.
- Cerrar los modales con el botón de cierre, al hacer clic en el backdrop y con la tecla Escape.

### 6. Modo claro y oscuro
- Añadir un toggle en la barra superior.
- Aplicar las variantes `dark:` de Tailwind a todas las vistas y componentes, manteniendo legibilidad y contraste.
- Guardar la preferencia en `localStorage` y conservarla al navegar entre secciones y al recargar la página.

### 7. Revisión final
- Comprobar que el prototipo es un único `index.html` y respeta las restricciones de tecnologías y dependencias.
- Revisar mínimos de datos, coherencia entre secciones y requisitos visuales.
- Probar navegación, dropdowns, cierre al hacer clic fuera, modales, expansión/colapso de skills, configuración editable y toggle de tema.
- Revisar responsive, accesibilidad básica, errores de consola y formato del código.

## Orden de trabajo
Integración visual → Contenido de las seis secciones → Navegación → Dropdowns → Modales → Modo oscuro → Revisión final.
