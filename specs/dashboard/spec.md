# AgentHub — Especificación Técnica del Prototipo HTML

## 1. Descripción del Producto

**AgentHub** es una plataforma SaaS donde las empresas pueden alquilar agentes de IA preconfigurados. Cada agente puede equiparse con distintas *skills* (habilidades como navegación web, lectura de documentos, gestión de calendarios, etc.) y desplegarse para tareas de negocio específicas.

El **panel de administración interno** es una interfaz web que permite al equipo de AgentHub gestionar usuarios, agentes, skills, contrataciones y visualizar métricas clave del negocio, así como un log de errores de ejecución de los agentes.

**Usuario objetivo**: Administradores internos de AgentHub que necesitan supervisar y gestionar la plataforma.

---

## 2. Stack Tecnológico y Restricciones

| Componente | Especificación |
|---|---|
| Lenguaje | HTML5 semántico |
| Estilos | Tailwind CSS v4 vía CDN (`@tailwindcss/browser@4`) |
| JavaScript | JS vanilla puro (sin frameworks, sin librerías externas) |
| Iconos | Font Awesome v6 (CDN gratuito) |
| Datos | Hardcodeados en arrays de JS dentro del HTML |
| Backend | No hay backend — todo es estático |
| Archivos | Un único archivo `index.html` con todo integrado |
| Servidor | Flask (`server.py` existente, sin modificar) |

---

## 3. Layout General

### 3.1 Sidebar (navegación lateral persistente)
- Ancho fijo de 240px, fondo oscuro (`bg-gray-900`).
- Contiene el logo de AgentHub en la parte superior.
- Lista de 6 enlaces de navegación, cada uno con un icono y una etiqueta de texto.
- El enlace activo se resalta con color de acento azul (`text-blue-400`, `bg-blue-500/10`).
- Al hacer clic en un enlace, cambia la sección visible en el área de contenido principal sin recargar la página.

### 3.2 Top Bar
- Altura 60px, ocupa el espacio superior derecho (junto al sidebar).
- Contiene: logo/indicador de sección activa a la izquierda, toggle de modo claro/oscuro en el centro, y avatar de administrador con nombre a la derecha.

### 3.3 Main Content Area
- Área variable que ocupa el resto de la pantalla.
- Padding interior uniforme de 24px.
- Muestra una sola sección a la vez según la navegación.

---

## 4. Especificaciones por Sección

### 4.1 Dashboard (`#section-dashboard`)

1. **Cuatro tarjetas de métrica en cuadrícula responsive 2×2** — Cada tarjeta ocupa el mismo ancho en desktop y se apilan en móvil. Cada tarjeta contiene: un icono representativo, una etiqueta descriptiva (ej: "Ingresos totales"), un valor numérico hardcodeado (ej: "$48,290"), y un color de acento distintivo (verde para ingresos, rojo para pérdidas, azul para agentes activos, naranja para agentes fallando). Las tarjetas tienen fondo blanco, borde redondeado (`rounded-xl`), sombra sutil (`shadow-sm`) y padding interior de 20px.

2. **Área placeholder para gráfico semanal** — Debajo de las tarjetas, un contenedor de ancho completo con altura de 280px, borde discontinuo (`dashed`), fondo gris muy claro, y texto centrado "📊 Gráfico de Actividad Semanal — próximamente" para indicar que es un marcador de posición.

3. **Las tarjetas responden al modo oscuro** — En modo oscuro, el fondo de las tarjetas cambia a gris oscuro (`dark:bg-gray-800`), el borde se ilumina ligeramente (`dark:border-gray-700`), y el texto se aclara (`dark:text-gray-200`).

### 4.2 Gestión de Usuarios (`#section-users`)

1. **Tabla de usuarios con 8 filas hardcodeadas** — Columnas: Nombre, Email, Plan (Free/Pro/Enterprise), Estado (Activo/Inactivo/Suspendido con badges de color), y Acciones (botón `⋮`). Cada valor de estado se muestra como un badge: verde para Activo, gris para Inactivo, rojo para Suspendido.

2. **Dropdown de acciones (botón `⋮`) en cada fila** — Al hacer clic en el botón `⋮` se abre un menú contextual flotante. Contiene las opciones "Ver detalle" y "Eliminar". El menú se cierra al hacer clic fuera de él. Las opciones tienen un icono y texto, con efecto hover.

3. **Modal de "Ver detalle" con overlay** — Al seleccionar "Ver detalle" se abre un modal centrado con fondo semitransparente (backdrop). El modal muestra la información completa del usuario: nombre, email, plan, estado, fecha de registro y empresa. Tiene un botón "X" para cerrar y también se cierra al hacer clic en el backdrop. Animación de entrada: fade + scale.

### 4.3 Gestión de Agentes (`#section-agents`)

1. **Lista de tarjetas de agente** — Cada agente se muestra como una tarjeta independiente (no tabla) que incluye: nombre del agente, propietario (email), estado actual (badge: Activo verde / Inactivo gris / Fallando rojo), y un botón expandible de skills.

2. **Skills colapsables con transición suave** — Por defecto, la lista de skills de cada agente está oculta. Un botón con texto "▶ Mostrar skills (N)" permite expandirla. Al hacer clic, el texto cambia a "▼ Ocultar skills (N)" y las skills aparecen con una transición de altura y opacidad. Cada skill se muestra como un badge pequeño.

3. **Modal de "Configurar" con system prompt** — Al seleccionar "Configurar" del dropdown, se abre un modal que muestra el nombre del agente y su system prompt completo en un área de texto de solo lectura. El prompt contiene las instrucciones de sistema del agente.

### 4.4 Skills (`#section-skills`)

1. **Bloque informativo contextual** — Al inicio de la sección, un recuadro informativo con fondo azul claro y borde azul explica: "Las skills son capacidades preconfiguradas que pueden equiparse a los agentes. Cada skill añade una funcionalidad específica al agente, como navegación web, lectura de documentos, gestión de calendario, etc."

2. **Tarjetas de skill con indicador de uso** — Cada skill se muestra en una tarjeta con: nombre de la skill, descripción breve, y un badge que indica cuántos agentes la tienen habilitada actualmente (ej: "4 agentes"). Las tarjetas están en una cuadrícula flexible.

3. **Modal de "Ver detalle" de skill** — Muestra el nombre completo, la descripción extendida y la lista de agentes que tienen esa skill habilitada.

### 4.5 Contrataciones de Agentes (`#section-hires`)

1. **Tabla de contratos con 8 filas** — Columnas: Cliente, Agente, Skills Contratadas, Fecha Inicio, Fecha Fin, Total, Acciones. Las skills contratadas se muestran como badges compactos agrupados.

2. **Modal de "Ver detalle" con desglose de precios** — Muestra cliente, agente, fechas del contrato, y una lista detallada de cada skill contratada con su precio individual, y el total al final.

3. **Formato de moneda** — Todos los valores monetarios se muestran con formato USD (ej: "$1,200.00") en la tabla y en los modales.

### 4.6 Log de Errores (`#section-error-log`)

1. **Tabla de errores con 10 entradas** — Columnas: Timestamp, Agente, Tipo de Error, Descripción, Acciones. Cada error tiene un timestamp con formato fecha-hora.

2. **Badges de color por tipo de gravedad** — El tipo de error se muestra como un badge: `ERROR` en rojo, `WARNING` en amarillo/naranja, `CRITICAL` en rojo oscuro/púrpura, `INFO` en azul. Cada badge tiene su propio color de fondo y texto.

3. **Modal de "Ver detalle" con traza completa** — Muestra timestamp, agente, tipo de error, descripción y la traza completa del error (stack trace simulado en formato `font-mono` con fondo oscuro).

4. **Acción "Marcar como resuelto"** — Al seleccionar esta opción del dropdown, la fila del error se actualiza visualmente: aparece un badge verde "Resuelto" en la fila y la opción cambia a "Marcar como no resuelto" (toggle).

---

## 5. Inventario de Componentes Reutilizables

| Componente | Descripción | Secciones donde aparece |
|---|---|---|
| **Sidebar** | Barra de navegación lateral fija con 6 enlaces e iconos | Todas |
| **Top Bar** | Barra superior con logo, toggle de tema y avatar | Todas |
| **Tarjeta de métrica** | Card con icono, etiqueta, valor y color de acento | Dashboard |
| **Tabla de datos** | Tabla HTML con cabecera, filas de datos y columna de acciones | Usuarios, Contrataciones, Errores |
| **Dropdown de acciones** | Menú contextual con opciones activado por botón `⋮` | Usuarios, Agentes, Skills, Contrataciones, Errores |
| **Modal** | Ventana emergente con overlay semitransparente y botón de cierre | Usuarios, Agentes, Skills, Contrataciones, Errores |
| **Badge de estado** | Etiqueta de color que indica un estado (activo/inactivo/error) | Usuarios, Agentes, Errores |
| **Skills colapsables** | Lista expandible/colapsable con transición suave | Agentes |
| **Toggle de modo oscuro** | Interruptor visual para cambiar entre modo claro y oscuro | Todas (en Top Bar) |
| **Toast de notificación** | Notificación flotante temporal que desaparece tras 3 segundos | Todas (acción Eliminar) |

---

## 6. Criterios de Aceptación

1. [ ] La navegación lateral permite cambiar entre las 6 secciones sin recargar la página.
2. [ ] La sección activa en la sidebar se resalta visualmente.
3. [ ] El toggle de modo claro/oscuro cambia toda la interfaz usando las utilidades `dark:` de Tailwind.
4. [ ] Las 4 tarjetas de métrica del Dashboard se muestran con icono, etiqueta, valor y color distintivo.
5. [ ] El placeholder del gráfico semanal está presente debajo de las tarjetas.
6. [ ] La tabla de usuarios muestra 8 filas con badges de estado de color.
7. [ ] El dropdown de acciones (`⋮`) se abre al hacer clic y se cierra al hacer clic fuera.
8. [ ] "Ver detalle" en usuarios abre un modal con los datos completos del usuario.
9. [ ] El modal se cierra con el botón X y haciendo clic en el backdrop.
10. [ ] "Eliminar" en cualquier sección muestra un toast de notificación.
11. [ ] Las skills de los agentes se expanden/colapsan con animación suave.
12. [ ] "Configurar" en agente abre un modal con el system prompt.
13. [ ] La sección Skills incluye un bloque informativo contextual.
14. [ ] "Ver detalle" en contrataciones muestra un desglose con precios individuales.
15. [ ] Los errores se muestran con badges de color según su tipo (ERROR, WARNING, CRITICAL, INFO).
16. [ ] "Marcar como resuelto" cambia el estado visual de la entrada de error.
17. [ ] Todos los datos están hardcodeados (no hay llamadas a API ni backend).
18. [ ] El diseño funciona correctamente en escritorio (viewport 1280px+).