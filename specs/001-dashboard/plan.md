# Plan de implementación: dashboard por bloques

## Objetivo y alcance

Implementar Studio Metrics para Alba Vega siguiendo [spec.md](spec.md), mediante HTML semántico y Tailwind CSS v4. El desarrollo será incremental y mobile-first: base común, resultados, factores y operaciones.

No se realizarán pruebas unitarias ni se incorporarán herramientas de testing. Cada fase tendrá una revisión visual, de contenido y de accesibilidad antes de continuar. Este documento no constituye una lista de tareas ni autoriza por sí mismo el inicio de la implementación.

## Arquitectura y reutilización

- La página se implementará en el documento existente `index.html`, conservando el CDN de Tailwind v4.
- La reutilización será mediante patrones consistentes de marcado y clases: tarjeta KPI, encabezado, comparativa de barras, etapa del funnel, tabla, estado, alerta y control.
- No se introducirán componentes ejecutables, archivos parciales, motores de plantillas, frameworks ni composición dinámica de HTML.
- Los tokens de marca se declararán mediante la configuración CSS de Tailwind v4 permitida por la especificación.
- `server.py` se conservará como servidor de desarrollo, sin modificaciones ni nuevas responsabilidades.
- Los valores, tendencias, clasificaciones y anchos de barras serán estáticos, sin cálculos ni JavaScript propio.

## Fase 1. Base visual y estructura semántica

- Configurar `lang="es"`, título «Studio Metrics | Alba Vega», viewport y fuente Nunito con alternativa local.
- Aplicar el fondo `#F2F1F6`, primario `#5B5677`, superficies blancas, contraste suficiente y radios máximos de 8 px.
- Crear enlace de salto, `header`, `nav`, un único `main` y tres `section` tituladas, con identificadores `resultados`, `factores` y `operaciones`.
- Mantener un único `h1` y una jerarquía coherente de encabezados.
- Incorporar una cabecera compacta con identidad, período del 1 al 30 de septiembre de 2026, enlaces internos y aviso «Datos de demostración».
- Incorporar un avatar ilustrado para la identidad ficticia como imagen local con permiso de uso, dimensiones reservadas y alternativa textual adecuada.
- Mostrar «Descargar informe» y «Nueva campaña» mediante botones nativos deshabilitados, con estado «No disponible» y descripción asociada.
- Definir espaciado, tipografía, estados, foco y dimensiones de los patrones comunes. No anidar tarjetas ni presentar las secciones como tarjetas flotantes.

**Revisión de salida:** estructura semántica correcta, navegación interna operativa, avatar cargado, fuente con fallback, foco visible y cabecera sin desbordamientos a 320 px.

## Fase 2. Bloque superior: resultados

**Dependencia:** base visual y semántica de la fase 1.

- Construir el patrón de tarjeta KPI con `dl`, `dt` y `dd` para ventas atribuidas de 42.500,00 €, comisiones de Alba de 6.375,00 €, 850 conversiones y engagement del 7,2%.
- Mostrar tendencias únicamente donde existen: ventas +12,5% y engagement +2,1%, con texto además de color y sin reinterpretarlas como puntos porcentuales.
- Diferenciar ventas de las marcas de la remuneración de Alba. Identificar la comisión del 15% y eliminar la interpretación anterior de ganancias del 85%.
- Agrupar los indicadores secundarios por volumen, ingresos, engagement y rendimiento, retención, satisfacción y eficiencia, incluyendo todos los valores definidos en la especificación.
- Aclarar que el MRR, churn y permanencia pertenecen a una membresía ficticia.
- Conservar el impacto en audiencia de 4,82% y su descenso de 0,4% como contexto secundario de definición no facilitada, no como conversión.
- Usar una columna como base y ampliar progresivamente hasta cuatro KPI en escritorio. Evitar que una cabecera excesiva oculte el primer resultado en móvil.

**Revisión de salida:** cifras cotejadas con la especificación, prioridad comercial clara, ausencia de tendencias inventadas e importes legibles a 320 y 375 px.

## Fase 3. Bloque intermedio: factores del resultado

**Dependencia:** patrones comunes estabilizados en las fases 1 y 2.

- Representar el funnel mediante cuatro etapas: 250.000 personas alcanzadas, 25.000 visitas, 1.250 carritos y 850 compras.
- Crear comparativas con `figure` y `figcaption`, barras HTML/Tailwind, anchos literales y etiquetas y valores visibles, sin bibliotecas de gráficos.
- Comparar plataformas por ingresos y participación; presentar engagement y ROI por separado, sin mezclar unidades en una misma escala.
- Comparar productos por ingresos, comisiones, conversión y engagement utilizando el mismo patrón visual.
- Incorporar los indicadores de calidad: leads cualificados 64%, asistencia 73% y aprobación de solicitudes 88%.
- Mostrar actividad e interacciones por red, junto con los clics, visualizaciones, compleción, tiempo medio de visualización y CTR definidos en la especificación.
- Conservar los crecimientos de plataforma como contexto de fuente con métrica no identificada, sin convertirlos en tendencias comerciales o alertas de conversión.

**Revisión de salida:** datos comprensibles sin hover ni color, unidades y escalas inequívocas, gráficos nombrados y etiquetas ajustadas a móvil.

## Fase 4. Bloque inferior: operaciones

**Dependencia:** patrones de tablas, controles y estados de la base común. Se recomienda ejecutarla después de la fase 3 para evitar cambios simultáneos sobre el mismo documento.

- Construir las tablas de productos, plataformas y campañas con todos los campos y valores establecidos en la especificación.
- Utilizar `caption`, `thead`, `tbody` y encabezados `th` con `scope` según corresponda.
- Encapsular cada tabla en una región adaptable con desplazamiento horizontal propio, nombre accesible y acceso por teclado cuando resulte necesario.
- Añadir filtros de período, plataforma, producto y estado con etiquetas explícitas, valores iniciales coherentes y estado deshabilitado acompañado de ayuda asociada.
- Incorporar las tres alertas estáticas, listados destacados y oportunidades de mejora especificados.
- Expresar estados y líderes por métrica mediante texto, sin depender exclusivamente de colores.
- No utilizar `aria-live` ni `role="alert"` para presentar el contenido inicial estático del reporte.

**Revisión de salida:** tablas completas y semánticas, desplazamiento limitado a sus contenedores, filtros honestos y estados claros sin desbordamiento global.

## Fase 5. Revisión integrada y entrega

**Dependencia:** los tres bloques terminados.

- Contrastar el resultado con los 13 criterios de aceptación de la especificación, sin recalcular ni conciliar los conjuntos ficticios.
- Ejecutar el servidor existente con `python3 server.py` y el requisito Flask documentado por el proyecto. Si el puerto 3000 está ocupado, utilizar otro puerto mediante un servidor estático disponible sin modificar el servidor existente.
- Revisar la página a 320, 375, 768, 1024 y 1440 px, además de zoom al 200%, comprobando ausencia de solapamientos, recortes y desplazamiento horizontal global.
- Recorrer la interfaz con Tab, Shift+Tab y Enter: salto al contenido, navegación interna, foco visible y regiones desplazables. Los controles deshabilitados no deben formar parte del recorrido de foco; sus motivos permanecerán visibles y asociados.
- Inspeccionar regiones, jerarquía de encabezados, nombres accesibles y tablas mediante el árbol de accesibilidad o un lector de pantalla disponible.
- Verificar contraste mínimo de 4,5:1 en texto normal y 3:1 donde corresponda, objetivos táctiles de 44 × 44 px y comprensión sin depender del color.
- Comprobar carga de avatar y fuente, funcionamiento del fallback, fidelidad de valores y ausencia de JavaScript propio, cálculos e integraciones.
- Utilizar las herramientas de navegador, diagnóstico o validación HTML disponibles sin añadir dependencias al proyecto. Cualquier comprobación no ejecutada se declarará pendiente.
- Entregar la URL local y un resumen de lo implementado y de las limitaciones estáticas.

## Archivos previstos

| Archivo | Intervención |
| --- | --- |
| `index.html` | Documento semántico, tokens de Tailwind y todos los bloques del dashboard |
| `assets/avatar-alba.webp` | Nuevo recurso visual local para la identidad ficticia |
| `specs/001-dashboard/spec.md` | Referencia de requisitos y datos, sin cambios durante la implementación |
| `server.py` | Servidor existente, sin cambios |
| `README.es.md` | Referencia para la ejecución local, sin cambios previstos |

## Exclusiones

- Sin pruebas unitarias, archivos de tests ni frameworks de testing.
- Sin JavaScript propio, cálculos, agregaciones, API, persistencia ni backend nuevo.
- Sin nuevas dependencias de frontend, frameworks o motores de plantillas.
- Sin descargas, creación de campañas o filtros funcionales simulados: las acciones y filtros estarán visibles y deshabilitados; los enlaces internos sí funcionarán.
- Sin reinterpretar métricas ambiguas ni presentar los datos de demostración como contabilidad conciliada.
- La lista de tareas se documentará por separado; no se incluye en este plan.