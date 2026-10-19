# Tareas: dashboard de Alba Vega

Basadas en [plan.md](plan.md) y sujetas a [spec.md](spec.md). Las casillas reflejan el avance verificado de la implementación.

Ejecutar las fases en orden y completar la revisión de cada bloque antes de continuar. Reutilizar patrones de HTML semántico y clases Tailwind v4, sin componentes ejecutables, JavaScript propio ni cálculos. No crear pruebas unitarias, archivos de tests ni instalar frameworks de testing.

Por solicitud del usuario, se retiran las tareas de verificación que requieren ejecutar Chromium. Las comprobaciones restantes se realizarán sobre el marcado, los datos, los estilos declarados y la respuesta del servidor, sin depender de ese navegador. Se conservan los identificadores originales. Esta exclusión no elimina los requisitos responsive y de accesibilidad de la especificación ni equivale a una validación visual o de interacción; las limitaciones se recogerán en T100.

## Fase 1. Base visual y estructura semántica

- [x] T001 Configurar `lang="es"` y el título «Studio Metrics | Alba Vega» en `index.html`.
- [x] T002 Conservar el viewport responsive y el CDN existente de Tailwind CSS v4.
- [x] T003 Incorporar Nunito con la alternativa `ui-rounded, sans-serif`.
- [x] T004 Declarar los tokens de fondo `#F2F1F6` y primario `#5B5677` mediante Tailwind v4.
- [x] T005 Definir el ancho de contenido, espaciado y tipografía base mobile-first.
- [x] T006 Definir el patrón de superficies blancas y bordes, con radios máximos de 8 px.
- [x] T007 Añadir un enlace de salto al contenido visible al recibir foco.
- [x] T008 Crear `header`, `nav` y un único `main` con destino para el enlace de salto.
- [x] T009 Crear las secciones tituladas `resultados`, `factores` y `operaciones`.
- [x] T010 Establecer un único `h1` y una jerarquía ordenada de `h2` y `h3`.
- [x] T011 Añadir la identidad «Alba Vega · Studio Metrics» a la cabecera.
- [x] T012 Añadir el período del 1 al 30 de septiembre de 2026 y «Datos de demostración».
- [x] T013 Añadir los tres enlaces internos de navegación con foco visible.
- [x] T014 Obtener un avatar ilustrado con permiso de uso y guardarlo como `assets/avatar-alba.webp`.
- [x] T015 Incorporar el avatar con dimensiones reservadas y alternativa textual adecuada.
- [x] T016 Añadir el botón nativo deshabilitado «Descargar informe».
- [x] T017 Añadir el botón nativo deshabilitado «Nueva campaña».
- [x] T018 Asociar a ambos botones el estado visible «No disponible» y su descripción accesible.
- [x] T019 Definir el patrón de encabezado de bloque con título y contexto opcional.
- [x] T020 Definir el patrón de estado o tendencia con texto y color complementario.

## Fase 2. Bloque superior: resultados

Dependencia: base de la fase 1 completada, con las exclusiones de verificación indicadas al inicio.

- [x] T023 Crear el patrón de tarjeta KPI mediante `dl`, `dt` y `dd`.
- [x] T024 Añadir ventas atribuidas de 42.500,00 € y tendencia +12,5% frente al mes anterior.
- [x] T025 Añadir comisiones de Alba de 6.375,00 € como resumen de demostración.
- [x] T026 Añadir 850 conversiones totales sin inventar una tendencia histórica.
- [x] T027 Añadir engagement medio del 7,2% y aumento del 2,1% sin llamarlo puntos porcentuales.
- [x] T028 Identificar la comisión del 15% como remuneración de Alba y diferenciarla de las ventas.
- [x] T029 Distribuir los cuatro KPI desde una columna móvil hasta cuatro columnas en escritorio.
- [x] T030 Añadir el resumen de volumen: inscripciones, usuarios activos e impresiones.
- [x] T031 Añadir el resumen de ingresos: MRR de membresía ficticia y precio medio de venta.
- [x] T032 Añadir interacciones totales, conversión global y CTR global como indicadores secundarios.
- [x] T033 Añadir churn y permanencia de la membresía ficticia, más compleción de compra.
- [x] T034 Añadir los indicadores de satisfacción NPS y CSAT.
- [x] T035 Añadir coste por conversión, margen y tiempo hasta la compra.
- [x] T036 Añadir impacto en audiencia del 4,82%, descenso del 0,4% y aclaración de definición no facilitada.
- [x] T037 Cotejar manualmente los valores con la especificación y comprobar que no aparece el indicador de ganancias del 85%.

## Fase 3. Bloque intermedio: factores del resultado

Dependencia: fases 1 y 2 completadas y cotejadas en código, con las exclusiones de verificación indicadas al inicio.

- [x] T039 Crear el patrón semántico de etapa del funnel con nombre y valor estático.
- [x] T040 Incorporar las cuatro etapas: 250.000 personas alcanzadas, 25.000 visitas, 1.250 carritos y 850 compras.
- [x] T041 Crear el patrón de gráfico con `figure`, `figcaption`, etiquetas y valores visibles.
- [x] T042 Fijar los anchos literales de las barras y mantener una escala común por métrica, sin cálculos.
- [x] T043 Añadir la comparación de ingresos y participación por plataforma.
- [x] T044 Añadir la comparación de engagement por plataforma.
- [x] T045 Añadir la comparación de ROI por plataforma.
- [x] T046 Añadir la comparación de ingresos por producto.
- [x] T047 Añadir la comparación de comisiones por producto.
- [x] T048 Añadir la comparación de tasas de conversión por producto.
- [x] T049 Añadir la comparación de engagement por producto.
- [x] T050 Añadir leads cualificados 64%, asistencia al directo 73% y aprobación de solicitudes 88%.
- [x] T051 Añadir actividad publicada e interacciones de Instagram según la especificación.
- [x] T052 Añadir actividad publicada e interacciones de TikTok según la especificación.
- [x] T053 Añadir actividad publicada e interacciones de YouTube según la especificación.
- [x] T054 Incorporar clics, visualizaciones, compleción, tiempo medio de visualización y CTR de la captura con etiquetas específicas.
- [x] T055 Incorporar los crecimientos de plataforma como contexto de fuente con métrica no identificada.
- [x] T056 Revisar que cada comparativa tiene unidad clara y no mezcla euros con alcance.

## Fase 4. Bloque inferior: operaciones

Dependencia: patrones comunes estabilizados; realizar después de la fase 3 para evitar cambios simultáneos sobre `index.html`.

- [x] T058 Crear el patrón de tabla con `caption`, `thead`, `tbody` y encabezados `th` con `scope`.
- [x] T059 Crear el contenedor adaptable de tabla con desplazamiento horizontal propio y nombre accesible.
- [x] T060 Preparar las columnas de productos: nombre, precio, ingresos, comisión aplicable, comisiones generadas, conversiones, tasa de conversión, engagement y ROI.
- [x] T061 Incorporar las tres filas de productos con sus valores estáticos.
- [x] T062 Preparar las columnas de plataformas: nombre, alcance, ingresos, engagement, conversiones y ROI.
- [x] T063 Incorporar las tres filas de plataformas y señalar con texto los liderazgos especificados.
- [x] T064 Preparar las columnas de campañas: marca, campaña, fechas, producto, estado, seguidores, ingresos, pago a Alba y ROI.
- [x] T065 Incorporar las tres filas de campañas con sus valores y estados estáticos.
- [x] T066 Añadir el filtro de período con etiqueta y valor inicial del reporte.
- [x] T067 Añadir el filtro de plataforma con etiqueta y valor inicial coherente.
- [x] T068 Añadir el filtro de producto con etiqueta y valor inicial coherente.
- [x] T069 Añadir el filtro de estado con etiqueta y valor inicial coherente.
- [x] T070 Deshabilitar los cuatro filtros y asociarles una explicación visible y accesible.
- [x] T071 Crear el patrón de alerta estática sin `aria-live` ni `role="alert"`.
- [x] T072 Añadir la alerta de descenso de conversión del Producto C sin inventar su magnitud.
- [x] T073 Añadir la alerta de pico de conversiones en Instagram sin inventar su magnitud.
- [x] T074 Añadir la alerta de Review Video pausada por revisión de seguimiento.
- [x] T075 Añadir el listado de productos destacados y sus motivos.
- [x] T076 Añadir los listados de plataforma y campaña destacadas con sus motivos.
- [ ] T077 Añadir las oportunidades de mejora del Producto C y de YouTube.
- [ ] T078 Revisar manualmente que las tablas conservan su semántica y contienen todos los campos.
- [ ] T080 Comprobar que filtros y estados no prometen funcionalidad inexistente ni dependen solo del color.

## Fase 5. Revisión integrada y entrega

Dependencia: los tres bloques terminados y revisados en código. Solo comprobaciones de contenido, marcado, estilos declarados y servidor; sin pruebas unitarias ni verificaciones dependientes de Chromium.

- [ ] T081 Servir el dashboard con el servidor existente y verificar su respuesta HTTP, sin modificar `server.py`; usar otro puerto si el 3000 está ocupado.
- [ ] T092 Verificar contraste mínimo de 4,5:1 para texto normal y 3:1 donde corresponda.
- [ ] T094 Comprobar que tendencias, alertas, estados y gráficos se entienden sin depender del color.
- [ ] T096 Cotejar todas las cifras, unidades, fechas y etiquetas con la especificación sin recalcular discrepancias.
- [ ] T097 Revisar el HTML semántico con las herramientas de diagnóstico o validación disponibles, sin nuevas dependencias.
- [ ] T098 Confirmar ausencia de JavaScript propio, cálculos, API, persistencia y nuevas dependencias de frontend.
- [ ] T099 Contrastar el código con los 13 criterios de aceptación de la especificación, identificando los aspectos visuales y de interacción no verificados.
- [ ] T100 Registrar las comprobaciones no ejecutadas como pendientes, sin declararlas aprobadas.
- [ ] T101 Entregar la URL local y un resumen de la implementación y sus limitaciones estáticas.