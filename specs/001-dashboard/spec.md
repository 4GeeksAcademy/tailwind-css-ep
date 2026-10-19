# Especificación: dashboard de Alba Vega

## Objetivo

Presentar un reporte estático para una influencer que colabora con marcas en Instagram, TikTok y YouTube. La primera pantalla debe priorizar los resultados comerciales y permitir identificar ingresos, comisiones, productos destacados, conversión, retorno y engagement.

Este documento contiene requisitos y criterios de aceptación. El plan de implementación y las tareas quedan fuera de su alcance.

## Base del proyecto y límites técnicos

- El proyecto es una plantilla HTML, sin framework, dependencias de frontend instaladas ni sistema de componentes.
- `index.html` contiene el documento inicial y carga Tailwind CSS v4 mediante su CDN oficial de navegador.
- `server.py` es un servidor Flask de desarrollo que sirve los archivos existentes en el puerto 3000; no es un backend de datos del dashboard.
- La implementación utilizará únicamente HTML y utilidades de Tailwind CSS v4. Se permite declarar tokens mediante la configuración CSS propia de Tailwind v4, sin una hoja de estilos de componentes independiente.
- No se incorporarán React, Vue, motores de plantillas, herramientas de compilación, bibliotecas JavaScript de gráficos ni JavaScript propio.
- El script existente de Tailwind es la única excepción técnica necesaria para procesar las utilidades en el navegador.
- No habrá cálculos, fórmulas ejecutables, agregaciones, consultas a redes sociales, API, autenticación, persistencia ni actualización de datos.
- Todos los valores, porcentajes, clasificaciones, anchos de barras y tendencias serán literales estáticos.
- No se modificará el servidor para componer componentes ni se introducirán inclusiones dinámicas de HTML.

## Identidad y lenguaje visual

- Influencer: Alba Vega, creadora de contenido de belleza, moda y tecnología.
- Nombre del producto: Studio Metrics.
- Idioma de interfaz y documento: español; moneda: EUR.
- Período inicial: del 1 al 30 de septiembre de 2026.
- Fondo principal obligatorio: `#F2F1F6`.
- Color primario obligatorio para marca, acciones y énfasis: `#5B5677`.
- Tipografía: Nunito, sans serif redondeada, con alternativa local `ui-rounded, sans-serif` si no carga la fuente externa.
- Superficies blancas, texto oscuro de contraste suficiente y bordes discretos. Verde, rojo y colores de plataforma podrán funcionar como acentos semánticos secundarios.
- Interfaz de trabajo compacta, sin portada promocional, titulares gigantes ni secciones decorativas presentadas como tarjetas flotantes.
- Tarjetas con radio máximo de 8 px. No se anidarán tarjetas dentro de tarjetas.
- El avatar de Alba será una imagen con dimensiones reservadas y texto alternativo adecuado; no se presentará una fotografía de stock como identidad real de una cliente.
- Los recursos visuales no podrán ser la única vía para comprender los datos.
- Se mostrará una indicación discreta de «Datos de demostración».

## Usuarios y preguntas principales

La usuaria principal es Alba. Debe poder consultar cuánto recibe en comisiones, qué productos generan más ingresos, cómo convierten sus anuncios, qué plataformas ofrecen mejor retorno y qué engagement obtiene por plataforma y producto.

## Arquitectura del contenido

### Cabecera

- Identidad de Alba, nombre Studio Metrics, período del informe y acceso directo a los tres bloques mediante enlaces internos.
- Acciones visibles «Descargar informe» y «Nueva campaña», con los estados accesibles definidos en esta especificación.
- La cabecera no debe desplazar los KPI fuera de la primera pantalla móvil con contenido secundario excesivo.

### Bloque superior: indicadores principales

- Dar máxima prioridad visual a ventas atribuidas, comisiones de Alba, conversiones totales y engagement medio.
- Cada KPI tendrá etiqueta, valor, unidad y contexto; la tendencia aparecerá únicamente cuando exista un dato proporcionado.
- Los indicadores secundarios cubrirán volumen, ingresos recurrentes, retención, rendimiento, satisfacción y eficiencia sin competir con los cuatro principales.
- No inventar variaciones históricas adicionales para rellenar tarjetas.
- Diferenciar expresamente ventas generadas para las marcas de la remuneración de la influencer.

### Bloque intermedio: factores del resultado

- Funnel con alcance, visitas, carritos y compras, mediante etapas legibles y valores estáticos.
- Comparativa por plataforma de ingresos atribuidos, participación, engagement y retorno.
- Comparativa por producto de ingresos, comisiones, conversión y engagement.
- Resumen de calidad: leads cualificados, asistencia al directo y aprobación de solicitudes de colaboración.
- Actividad por red y desglose de interacciones.
- Gráficos de barras HTML/Tailwind con títulos, etiquetas y valores visibles; no depender de hover, canvas o imágenes para comunicar cifras.
- Las comparativas deberán mantener la misma unidad y métrica dentro de cada gráfico. No representar euros como alcance.

### Bloque inferior: detalles operacionales

- Tabla de productos: nombre, precio, ingresos, comisión aplicable, comisiones generadas, conversiones, tasa de conversión, engagement y ROI.
- Tabla de plataformas: alcance, ingresos atribuidos, engagement, conversiones y ROI; destacar con texto la plataforma líder por métrica.
- Tabla de campañas: marca, campaña, fechas, producto, estado, seguidores, ingresos, pago a Alba y ROI.
- Alertas estáticas sobre descenso de conversión, pico de conversiones y revisión de seguimiento.
- Listados de productos, plataformas y campañas destacados, además de oportunidades de mejora.
- Filtros visibles de período, plataforma, producto y estado. Su estado no operativo debe ser inequívoco.

## Datos y procedencia

### Datos confirmados por la cliente

| Producto | Precio | Comisión por venta |
| --- | --- | --- |
| Producto A, cuidado de la piel | 50 € | 15% |
| Producto B, moda | 120 € | 15% |
| Producto C, accesorios | 80 € | 15% |

La comisión del 15% corresponde a Alba, no a una tarifa que se descuenta para pagarle el 85%. La tarjeta de la captura «My Earnings (85%) / €36,125.00» queda descartada por contradecir esta información. No calcular importes por venta ni totales mediante código.

### Datos conservados de la captura

| Indicador | Valor | Contexto |
| --- | --- | --- |
| Ventas atribuidas a las marcas | 42.500,00 € | +12,5% frente al mes anterior |
| Impacto en la audiencia | 4,82% | Descenso mostrado de 0,4%; definición no facilitada |
| Engagement medio | 7,2% | Incremento mostrado de 2,1% |

El impacto en audiencia no se utilizará como tasa de conversión. Las variaciones de impacto y engagement no se describirán como puntos porcentuales, ya que la fuente no lo especifica.

| Plataforma | Ingresos atribuidos | Participación | Otros datos de la captura |
| --- | --- | --- | --- |
| Instagram | 22.100 € | 52% | 45,2 mil clics; 1,2 mil compartidos; crecimiento +18% |
| TikTok | 14.450 € | 34% | 890 mil visualizaciones; compleción 42%; crecimiento +32% |
| YouTube | 5.950 € | 14% | Visualización media 4 min 12 s; CTR 2,8%; caída del 2% |

Los porcentajes de crecimiento de plataforma no tienen una métrica identificada. Se conservarán como contexto de la fuente, sin atribuirlos a seguidores, ventas o conversiones ni utilizarlos como alertas de conversión.

| Producto | Ingresos | Tasa de conversión |
| --- | --- | --- |
| Producto A | 15.200 € | 5,2% |
| Producto B | 18.500 € | 4,1% |
| Producto C | 8.800 € | 3,8% |

| Marca / campaña | Estado | Seguidores | Ingresos | Pago a Alba | ROI |
| --- | --- | --- | --- | --- | --- |
| Luxe Skincare / Summer Campaign | Activa | 245 mil | 12.400,00 € | 1.860,00 € | 6,2x |
| Urban Apparel / Fall Collection | Activa | 82 mil | 4.200,00 € | 630,00 € | 4,8x |
| Tech Gadgets / Review Video | Pausada | 1,2 M | 21.900,00 € | 3.285,00 € | 5,4x |

### Datos ficticios aprobados para la demostración

Los siguientes datos completan los campos ausentes. Son independientes de las cifras confirmadas y de las capturas: no constituyen una contabilidad conciliada ni acreditan resultados reales. No se recalcularán para corregir diferencias entre vistas.

| Indicador | Valor estático |
| --- | --- |
| Comisiones de Alba, resumen de demostración | 6.375,00 € |
| Ventas / conversiones totales | 850 |
| Inscripciones | 320 |
| Usuarios activos | 2.400 |
| Impresiones | 1,8 M |
| MRR de membresía ficticia | 1.200 € |
| Precio medio de venta | 50 € |
| Interacciones totales | 86.400 |
| Tasa de conversión global | 3,4% |
| Churn de membresía | 2,3% |
| Permanencia media de membresía | 8 meses |
| Compleción de compra | 68% |
| CTR global | 2,8% |
| NPS | 62 |
| CSAT | 94% |
| Coste por conversión | 8,40 € |
| Margen | 72% |
| Tiempo hasta la compra | 2,4 días |
| Funnel | 250.000 personas alcanzadas; 25.000 visitas; 1.250 carritos; 850 compras |
| Leads cualificados | 64% |
| Asistencia al directo promocional | 73% |
| Aprobación de solicitudes de colaboración | 88% |

| Plataforma | Alcance | Engagement | Conversiones | ROI |
| --- | --- | --- | --- | --- |
| Instagram | 130.000 | 8,1% | 420 | 6,4x |
| TikTok | 85.000 | 7,6% | 290 | 5,8x |
| YouTube | 35.000 | 5,2% | 140 | 4,2x |

| Plataforma | Actividad | Me gusta | Comentarios | Compartidos | Guardados |
| --- | --- | --- | --- | --- | --- |
| Instagram | 8 posts, 24 stories, 6 reels | 24.000 | 2.100 | 1.200, de la captura | 4.500 |
| TikTok | 12 vídeos | 36.000 | 3.400 | 5.600 | 2.800 |
| YouTube | 4 vídeos, 6 shorts | 4.100 | 900 | 600 | 1.200 |

| Producto | Comisiones | Conversiones | Engagement ficticio | ROI |
| --- | --- | --- | --- | --- |
| Producto A | 2.280 € | 300 | 8,4% | 5,6x |
| Producto B | 2.775 € | 350 | 7,6% | 6,8x |
| Producto C | 1.320 € | 200 | 5,9% | 4,1x |

| Campaña | Fechas de 2026 | Producto |
| --- | --- | --- |
| Summer Campaign | 1–30 de septiembre | Producto A |
| Fall Collection | 5–30 de septiembre | Producto B |
| Review Video | 10–20 de septiembre | Producto C |

- Alertas de demostración: descenso de conversión del Producto C, pico de conversiones en Instagram y Review Video pausada por revisión de seguimiento. No añadir magnitudes de variación que no estén especificadas.
- Productos destacados: Producto B por ingresos y conversión; Producto A por engagement.
- Plataforma destacada: Instagram por ingresos, engagement, conversiones y ROI entre las tres redes.
- Campaña destacada: Summer Campaign por ROI entre las colaboraciones.
- Oportunidades: revisar la ficha del Producto C y la llamada a la acción de YouTube.
- El MRR, churn y permanencia describen una membresía ficticia adicional, no una característica confirmada del negocio ni una parte desglosada de las ventas de productos.
- Alcance, impresiones, seguidores, visualizaciones y clics tendrán etiquetas diferenciadas. El alcance entre plataformas no se presentará como audiencia única deduplicada.

## Contratos de bloques reutilizables

La reutilización será de patrones de marcado y clases, no de componentes ejecutables. Copiar una instancia no debe cambiar la semántica, el espaciado o los estados del patrón. No se exigirán archivos parciales que el navegador no pueda incluir por sí mismo.

| Patrón | Contenido variable | Requisitos comunes |
| --- | --- | --- |
| Tarjeta KPI | Etiqueta, valor, unidad, contexto y tendencia opcional | Jerarquía estable, altura consistente, tendencia con texto y sin cálculos |
| Encabezado de bloque | Título, contexto y enlace opcional | Niveles de encabezado ordenados y destino identificable |
| Comparativa de barras | Categoría, valor, unidad, color y ancho literal | Etiquetas visibles, alternativa textual completa y misma escala dentro del gráfico |
| Etapa del funnel | Nombre y valor literal | Orden lógico y lectura comprensible sin flechas ni color |
| Tabla de reporte | Título, columnas y filas | Tabla semántica, encabezados asociados y contenedor adaptable |
| Estado o tendencia | Texto y variante semántica | No depender exclusivamente del color o de un icono |
| Alerta | Título, detalle y severidad | Información estática legible, sin anunciarla como una notificación en vivo |
| Control | Etiqueta, valor, icono opcional y estado | Elemento nativo, nombre accesible, foco visible y estado honesto |

Los gráficos no requerirán una biblioteca de dominio: son representaciones estáticas simples con HTML y Tailwind. No se añadirán SVG manuales como decoración o sustituto de iconos de una biblioteca.

## Acciones y filtros accesibles

- «Descargar informe» y «Nueva campaña» permanecerán visibles como botones nativos deshabilitados en esta entrega, con una indicación breve asociada de «No disponible» y descripción accesible del estado.
- No simular descargas, aperturas de formularios, confirmaciones ni generación de campañas. Una implementación funcional de estas acciones pertenece a otro alcance.
- Los filtros serán controles nativos etiquetados, con valores iniciales del reporte y estado deshabilitado mientras no exista filtrado real. No permitir una selección que contradiga los datos visibles.
- Los enlaces internos a secciones sí funcionarán mediante HTML. No utilizar enlaces con `href="#"` para aparentar acciones.
- Los botones habilitados, enlaces y controles deberán funcionar por teclado y tener foco claramente visible. No habrá elementos interactivos anidados.
- Cuando exista un botón de icono, utilizar un recurso de iconos estático sin añadir runtime JavaScript; incluir nombre accesible y ayuda visible al foco y al hover. Los iconos decorativos estarán ocultos a tecnologías de asistencia.
- Evitar información disponible únicamente mediante tooltip. El estado deshabilitado tendrá contexto fuera del control, ya que no recibe foco.

## Responsive mobile-first

- El diseño base será de una columna; las columnas adicionales aparecerán progresivamente con los breakpoints de Tailwind.
- En móvil, los cuatro KPI principales precederán a gráficos, indicadores secundarios y detalle operacional. En escritorio podrán disponerse en una fila.
- Cabecera, navegación y acciones deberán ajustarse a varias líneas sin solapamientos ni anchuras mínimas que desborden la página.
- Las tablas conservarán su semántica y podrán desplazarse horizontalmente dentro de su propio contenedor, nunca provocando scroll horizontal global.
- Las regiones de tabla con desplazamiento serán identificables y accesibles por teclado cuando sea necesario.
- Los gráficos tendrán dimensiones estables y etiquetas que se ajusten al espacio disponible. No usar tamaños de fuente basados en unidades de viewport.
- Controles táctiles con área objetivo de al menos 44 × 44 px; texto de lectura cómodo y separación suficiente entre acciones.
- Comprobar el contenido a 320, 375, 768, 1024 y 1440 px de ancho, además de zoom al 200% sin pérdida de información o acciones.

## Accesibilidad y semántica

- El HTML deberá ser semántico: elegir los elementos por el significado del contenido, no por su apariencia visual.
- Utilizar `header` para la cabecera, `nav` para la navegación, un único `main` para el contenido principal y `section` con encabezado para cada bloque. Usar `article` solo para contenido independiente y `footer` si existe un pie de página.
- Representar listados con `ul` u `ol`, pares de etiqueta y valor con `dl`, `dt` y `dd` cuando corresponda, y gráficos con `figure` y `figcaption`. Reservar `div` y `span` para agrupaciones sin significado semántico propio.
- Preferir elementos HTML nativos a roles ARIA equivalentes: enlaces para navegar, botones para acciones y tablas para datos tabulares; no simular controles con `div` o `span`.
- Objetivo WCAG 2.2 AA: contraste mínimo de 4,5:1 en texto normal, 3:1 en texto grande y 3:1 en límites o indicadores esenciales de controles habilitados.
- Usar `lang="es"`, título de página descriptivo, un único `h1`, regiones semánticas y enlace de salto al contenido.
- Cada sección y tabla tendrá nombre identificable. Las tablas utilizarán `caption`, `thead`, `tbody` y `th` con `scope` según corresponda.
- Etiquetas de formularios explícitamente asociadas; no emplear el placeholder como único nombre.
- Expresar aumentos, descensos, alertas y estados con palabras además de color.
- Las cifras tendrán contexto, unidades y formato español consistente. Un valor ausente no se representará con cero.
- No imponer animaciones necesarias para comprender la información; cualquier movimiento opcional respetará la reducción de movimiento.

## Criterios de aceptación

1. El dashboard presenta los tres grandes bloques y prioriza los cuatro KPI acordados.
2. El contenido de la captura se reorganiza, sin reproducir obligatoriamente su composición visual.
3. Los precios de los tres productos y la comisión del 15% son visibles y no se mantiene la remuneración incorrecta del 85%.
4. Se distinguen ventas de marcas, comisiones de Alba, métricas ambiguas y datos de demostración.
5. Todos los campos solicitados tienen contenido estático definido y no existe lógica de cálculo o agregación.
6. Tarjetas, gráficos y tablas mantienen contratos visuales y semánticos reutilizables sin introducir un framework.
7. La paleta principal utiliza los dos colores solicitados y una tipografía sans serif redondeada.
8. La interfaz es usable en los anchos establecidos, sin solapamientos, contenido cortado ni scroll horizontal de página.
9. Las tablas, los gráficos y los estados son comprensibles sin depender del color, del ratón o de imágenes.
10. Las acciones y filtros están presentes y sus limitaciones estáticas se comunican mediante estados accesibles, sin prometer comportamiento inexistente.
11. La navegación interna es operativa con teclado, y las imágenes o fuentes externas no son necesarias para interpretar el reporte.
12. El alcance no incluye backend, nuevas dependencias de aplicación, plan de implementación ni lista de tareas.
13. El documento utiliza HTML semántico, con regiones, encabezados, listas, gráficos, tablas y controles nativos adecuados al significado de cada contenido.