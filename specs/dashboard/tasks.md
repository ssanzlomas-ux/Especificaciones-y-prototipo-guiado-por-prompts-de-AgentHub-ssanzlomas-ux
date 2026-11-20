# Tareas verificables — AgentHub

Las tareas se ejecutan en el orden indicado. Una tarea se marca como completada solo después de comprobar sus criterios verificables. Este archivo no implementa código.

## 1. Integración visual y estructura
- [x] **1.1 Crear el documento final `index.html`.** Verificación: existe en la raíz y contiene una estructura HTML semántica completa con `head`, `body` y metadatos responsive.
- [x] **1.2 Integrar Tailwind CSS mediante CDN.** Verificación: Tailwind se carga con un script CDN; no hay framework, herramienta de build ni dependencia adicional.
- [x] **1.3 Construir la estructura persistente del panel.** Verificación: sidebar, barra superior y área principal aparecen en la página y siguen la referencia visual de Stitch.
- [x] **1.4 Preparar las seis vistas del panel.** Verificación: secciones identificables para Dashboard, Usuarios, Agentes, Skills, Contrataciones y Log de errores.
- [x] **1.5 Adaptar el layout a pantallas estrechas.** Verificación: sidebar y contenido siguen siendo utilizables en viewport móvil; las tablas no deforman la página y admiten scroll horizontal cuando haga falta.
- [x] **1.6 Revisar las restricciones de estilos.** Verificación: los estilos se aplican con utilidades Tailwind; todo estilo inline excepcional tiene una necesidad concreta que Tailwind no cubre razonablemente.

## 2. Contenido y datos de muestra
- [x] **2.1 Completar el Dashboard.** Verificación: se ven cuatro métricas requeridas, cada una con etiqueta, icono y valor hardcodeado, y un placeholder de gráfico semanal a ancho completo.
- [x] **2.2 Cargar usuarios de muestra coherentes.** Verificación: hay al menos cinco filas con nombre, email, plan y badge de estado; hay campos suficientes para el registro completo del modal.
- [x] **2.3 Cargar agentes de muestra coherentes.** Verificación: hay al menos cuatro agentes, cada uno con nombre, propietario, estado, skills y prompt de sistema.
- [x] **2.4 Cargar skills de muestra.** Verificación: hay al menos cuatro skills con nombre, descripción y cantidad de agentes habilitados; la vista explica brevemente qué es una skill.
- [x] **2.5 Cargar contratos de muestra.** Verificación: hay al menos cuatro contratos con cliente, agente, skills, fechas de inicio/fin, importes individuales y total.
- [x] **2.6 Cargar errores de muestra.** Verificación: hay al menos seis entradas con timestamp, agente, tipo/gravedad con badge codificado por color, descripción y traza simulada.
- [x] **2.7 Revisar coherencia cruzada de datos.** Verificación: las referencias a usuarios, propietarios, clientes, agentes y skills son consistentes entre las vistas.

## 3. Navegación
- [x] **3.1 Implementar cambio de sección sin recarga.** Verificación: cada enlace de sidebar muestra su vista correspondiente sin recargar el documento.
- [x] **3.2 Reflejar el elemento activo.** Verificación: al cambiar de vista, solo el enlace seleccionado tiene el indicador visual activo y el título/breadcrumb coincide con la sección.
- [x] **3.3 Verificar navegación tras interacciones.** Verificación: cambiar de vista sigue funcionando después de abrir/cerrar un menú o modal.

## 4. Dropdowns
- [x] **4.1 Implementar los dropdowns de acciones requeridos.** Verificación: cada fila/elemento en Usuarios, Agentes, Skills, Contrataciones y Errores tiene un botón `⋮` con las opciones exigidas para esa sección.
- [x] **4.2 Implementar cierre al hacer clic fuera.** Verificación: cualquier menú abierto se cierra al pulsar fuera del menú; pulsar dentro permite ejecutar la opción.
- [x] **4.3 Simular acciones destructivas sin backend.** Verificación: «Eliminar» no llama a un servicio y muestra confirmación o aviso explícito de que la acción es simulada.
- [x] **4.4 Implementar el cambio de estado de error.** Verificación: «Marcar como resuelto» actualiza visualmente la entrada a estado resuelto y la acción puede revertirse si así se diseña.

## 5. Modales
- [x] **5.1 Implementar apertura de detalle de usuario.** Verificación: «Ver detalle» muestra todos los campos del usuario seleccionado.
- [x] **5.2 Implementar configuración de agente editable.** Verificación: «Configurar» muestra el prompt de sistema del agente seleccionado en un `<textarea>` editable.
- [x] **5.3 Implementar detalle de skill.** Verificación: «Ver detalle» muestra descripción extendida y agentes asociados.
- [x] **5.4 Implementar desglose del contrato.** Verificación: el modal muestra cliente/agente/fechas, cada skill con su precio individual y el importe total.
- [x] **5.5 Implementar detalle de error.** Verificación: el modal muestra timestamp, agente, tipo, descripción y traza simulada completa.
- [x] **5.6 Verificar métodos de cierre.** Verificación: todos los modales se cierran con el botón, con clic en el backdrop y con Escape.

## 6. Skills colapsables
- [x] **6.1 Implementar expansión y colapso por agente.** Verificación: las skills están ocultas al cargar, el control revela solo las del agente correspondiente y el segundo clic las oculta con transición suave.

## 7. Modo claro y oscuro
- [x] **7.1 Implementar toggle en la barra superior.** Verificación: el control alterna claro/oscuro usando la clase `dark` y utilidades `dark:` de Tailwind.
- [x] **7.2 Aplicar ambos temas a todas las vistas y overlays.** Verificación: se mantienen legibles Dashboard, tablas, tarjetas, dropdowns, modales y mensajes en los dos temas.
- [x] **7.3 Persistir la preferencia.** Verificación: tras cambiar de sección y recargar la página se conserva el tema elegido.

## 8. Revisión final
- [x] **8.1 Confirmar entregable único.** Verificación: el prototipo final está implementado en `index.html`; no requiere otros archivos de aplicación.
- [x] **8.2 Verificar restricciones técnicas.** Verificación: solo HTML, Tailwind por CDN y JavaScript vanilla; no hay backend, frameworks, jQuery, herramientas de build ni dependencias adicionales.
- [x] **8.3 Ejecutar revisión funcional.** Verificación: se han probado todos los criterios de esta lista y no hay errores de JavaScript en consola.
- [x] **8.4 Revisar accesibilidad e interacción básica.** Verificación: botones con nombres accesibles, controles enfocables y Escape cierra el modal.
- [x] **8.5 Revisar responsive y diferencias visuales.** Verificación: se revisa al menos una vista desktop y una móvil, contrastando con `DESIGN.md` y la captura de Stitch.
