# Tema 32 — Changelog

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.

---

## v1.3 — 2026-10-06 — Revisión de diagramas

**Motivo**: barrido de los diagramas de los 40 temas tras la revisión jurídica y de normas.

### Cambios

- Revisión visual de todos los diagramas, captura a captura (la medición automática no detecta contraste, flechas mal dirigidas ni textos pegados al borde): corregidos textos que se salían de su caja o del lienzo, cajas que se tocaban, flechas que no llegaban a su destino y textos con poco contraste. Sin cambios de contenido.

---

## v1.2 — 2026-10-02 — Normas vigentes y correcciones comunes de la revisión

**Motivo**: revisión de la serie del 01-10-2026 (decisiones de Joan y María): normas caducadas con el patrón de dos filas en Fuentes y correcciones comunes (referencias al cliente y al origen del material, promesas sobre el examen, AP → AAPP; en este tema no hay «AP» administrativo).

### Cambios

- **RFC 8446 → RFC 9846** (TLS 1.3, julio de 2026): fila vigente y fila histórica en Fuentes; las citas del contenido, los diagramas, el índice y el test apuntan al RFC 9846. Ninguna respuesta del test cambia.
- Fuera las promesas sobre el examen («se pregunta», «muy preguntado», «materia de examen», «alta probabilidad de aparecer en el test oficial»…): unas 45 frases en contenido, índice, diagramas, fuentes y validación, conservando el dato. Las frases en condicional («una opción que afirme… es falsa») se mantienen.
- Pestaña Inicio: la caja «Cómo estudiar» (escrita en el builder) sin promesas sobre el examen.
- Fuera las referencias internas al origen del material (rutas `Test_Prompting/…`, «esqueleto oficial», notas de secuencia de la serie) en índice y validación.
- Títulos de las cajas homogeneizados con los temas 1-10 (revisión jurídica): «Dato clave», «Ejemplo de aplicación en el Ayto» y «Relación con otros temas»; las cajas «Ejercicio resuelto» no cambian.

---

## v1.1 — 2026-09-06 — Ficha de extensión y tiempo de estudio

**Estado**: sin cambios de contenido. Solo se añade información sobre el propio tema.

**Motivo**: petición del IAM (Jesús Cuadrado, 02-09-2026) al validar el Tema 30. Acepta la extensión de los temas «compuestos» a condición de que se informe de «su extensión en palabras y tiempo estimado de estudio». Al revisarlo se vio que ese dato solo aparecía en 16 de los 40 temas, y que faltaba justo en los más largos.

### Alcance

- Ficha bajo la cabecera del tema, y al final de la pestaña Índice donde esa pestaña existe:
  - **Extensión**: ~26.000 palabras · 18 diagramas · 60 preguntas de test
  - **Tiempo estimado de estudio**: 22-24 horas (primera vuelta completa, sin contar repasos)
- La cifra de palabras de la tabla de entregables se sincroniza con la ficha, para que el tema no muestre dos recuentos distintos.
- Las horas salen de una fórmula común a los 40 temas, para que sean comparables entre sí: contenido a 1.500 palabras/hora (ritmo de estudio activo), diagramas a una hora por cada cinco y test a dos minutos por pregunta. Se publica como intervalo de dos horas.
- Generado con `_tools-qa/ficha_estudio.py`, idempotente y reejecutable tras cualquier regeneración con `build_tNN.py`.

---

## v1.0 — 2026-08-27 — Primera versión

Generación completa del tema desde el esqueleto oficial `Test_Prompting/temas agosto/32.md`, siguiendo el patrón de la serie técnica (plantilla de referencia: **T29**).

### Alcance de la v1.0

| Entregable | Cantidad |
|---|---|
| Contenido teórico | 6 secciones · 14 subsecciones · 22 epígrafes · **~25.000 palabras** |
| Diagramas SVG inline | **18** |
| Banco de test | **60 preguntas** A/B/C, balanceadas **20/20/20** |
| Casos prácticos | **3**, de 10 puntos cada uno |
| Fuentes | 40 Tier 1 · 21 Tier 2 · 4 Tier 3 |
| Pestañas del `index.html` | 8 (Inicio, Contenido, Índice, Diagramas, Test, Casos, Validación, Fuentes) |

### Decisiones de generación

1. **Estructura fiel al esqueleto, con un solo ajuste.** Los seis bloques de primer nivel y los catorce subapartados del esqueleto se han respetado literalmente. Único cambio: el quinto nivel `##### Confidencialidad, Integridad, Disponibilidad, Autenticidad y No Repudio` se ha **promovido** a epígrafe propio (§1.1.2) para conservar la numeración de tres niveles de toda la serie. Anotado como punto 1 de validación.

2. **Todo el ENS verificado contra el BOE.** Se descargó el PDF oficial (`BOE-A-2022-7191`, BOE núm. 106 de 4 de mayo de 2022) y se extrajo con `pdftotext -layout`. De ahí proceden, literalmente y no de memoria: los siete principios básicos (art. 5 y arts. 6-11), los requisitos mínimos (arts. 12-27), el régimen de auditoría (art. 31), el anexo I completo (dimensiones **C-I-T-A-D**, niveles BAJO/MEDIO/ALTO, categorías BÁSICA/MEDIA/ALTA y la regla del máximo), el glosario del anexo IV y las medidas del anexo II con sus tablas de aplicación: `mp.if.1` a `mp.if.7`, `op.acc.1` a `op.acc.6` con sus nueve refuerzos, `op.exp.4`, `op.exp.6`, `op.exp.10`, `mp.com.2`, `mp.com.3`, `mp.si.2`, `mp.info.3` y `mp.info.4`.

3. **Otras verificaciones online.** Artículos 9 y 10 de la Ley 39/2015 contra el texto consolidado del BOE; lista de categorías del **OWASP Top 10:2025** contra `owasp.org/Top10/2025/`; número, fecha y entrada en vigor del **Reglamento (UE) 2024/1183** (eIDAS 2); publicación de **FIPS 203/204/205** en agosto de 2024.

4. **Sin fragmentos de código.** Decisión deliberada, igual que en T28: el enunciado no menciona ningún lenguaje y lo memorizable son códigos de medida del ENS, puertos, números de protocolo, artículos y umbrales. Se han concentrado en tablas y en los diagramas D1, D5, D12, D15 y D18.

5. **Fronteras explícitas con T35, T36 y T39.** El tema declara desde las «Convenciones» qué remite a otros temas y por qué, para que el solapamiento del temario oficial no se lea como una omisión. Recogido como punto 2 y 3 de validación.

6. **Secuencia de letras del test fijada antes de redactar.** Aplicando la lección de T23, se definió de antemano la secuencia de 60 respuestas correctas con 20 de cada letra. Resultado: **20/20/20 a la primera**, verificado por script antes de dar el test por bueno.

7. **Bug del conversor ya incorporado.** El `build_t32.py` nace con el `inline()` corregido —la negrita admite cursiva anidada—, sin arrastrar el bug detectado en T26 y T27.

8. **Regla de margen de la atribución SVG aplicada desde el origen.** Todos los diagramas tienen la línea `[Fuente: …]` a **8 px o más** del borde inferior del `viewBox` (regla derivada del QA de T28). Siete diagramas se ajustaron automáticamente tras la comprobación por script.

9. **Tildes de los SVG revisadas.** El texto visible y los `aria-label` de los 18 diagramas se han revisado específicamente para evitar el fallo de tildes perdidas en SVG detectado en T22.

### QA realizado

- **Integridad del test**: 60 preguntas, 3 opciones únicas por pregunta, coincidencia exacta entre el texto de la opción correcta y el de la solución, referencia presente en las 60. Distribución **20 A / 20 B / 20 C**.
- **SVG**: 18 diagramas, `role` y `aria-label` en todos, clases con sufijo único, atribución con margen suficiente.
- **Render real** con Chrome headless y sonda `getBBox` sobre el `index.html` generado, para detectar desbordes y colisiones de texto.
- **Motor de test** probado sobre HTTP (no sobre `file://`, donde el `<script>` no se ejecuta en este entorno).
- **Asteriscos crudos**: recuento en el `index.html` tras excluir `<script>`, `<svg>` y `<pre><code>`.
- **Ortografía**: hunspell es_ES más barrido dirigido de tildes y eñes, con revisión manual de los falsos positivos de vocabulario técnico inglés.
- **Referencias cruzadas**: 17 temas citados, todos validados contra el temario oficial BOAM 10.032.

### Pendientes para QA / próxima iteración

- Validación de contenido por **María y Ana**, y de los ocho puntos abiertos por el **IAM** (ver `tema-32-validacion.md`).
- Decidir si el **T23** se actualiza al OWASP Top 10:2025 para que ambos temas citen la misma edición.
- Reverificar los **datos volátiles** antes de cada convocatoria: vigencia del ENS y sus ITS, versión de la CCN-STIC 807, calendario de la cartera europea de identidad digital, transposición de NIS2, edición del OWASP Top 10 y versión del CVSS.

### Corrección posterior a la publicación (mismo día)

**D2 estaba truncado y ninguno de los tres controles lo detectó.** En el SVG del diagrama D2 un `</text>` de cierre había perdido su `<`, quedando `degradación de las/text>`. Consecuencia visible: se pintaban las tres primeras cajas y desaparecían la caja RIESGO, las tres flechas, el bloque de tratamiento del riesgo y el riesgo residual. Detectado por Joan sobre el tema ya publicado.

**Por qué no lo vio el QA (esto sí está medido).** Se reprodujo el fallo a propósito y se midió el DOM resultante:

- El parser **HTML es tolerante**: con el `</text>` roto, el navegador **sigue creando los 11 `<rect>` y los 30 `<text>`** del diagrama. Por eso el **recuento de elementos cuadraba** y no delataba nada.
- Esos elementos quedan anidados dentro del `<text>` que nunca se cierra y **no se pintan**: el último `<text>` mide `0×0`. Un elemento de anchura cero **ni desborda el viewBox ni colisiona con nadie**, así que el **`getBBox` devolvió «0 desbordes y 0 colisiones»** — un **falso OK**, el tercero de esta serie tras el «0 SVG evaluados» y el Chrome zombi.
- La altura pintada del SVG se deformaba (469 px frente a los ~340 del `viewBox`), única señal que quedaba, y no se estaba comprobando.

**Causa del tecleo: no determinada.** Se sospechó del `sed` usado para corregir tildes y **se descartó por medición**: se reprodujo el comando compuesto exacto sobre una línea aislada y sobre el fichero completo real, y también los otros tres `sed` posteriores a la revisión visual. **Ninguno rompe la cadena.** Lo más probable es un error en la escritura original del SVG; no se deja escrito un mecanismo que no se ha podido comprobar.

**Defensa incorporada al QA:** validación **XML** de cada `<svg>...</svg>` con `xml.etree.ElementTree.fromstring()` **antes** de medir nada, que aborta si alguno está mal formado, más comprobación de que el número de SVG del DOM coincide con el del fichero. Es el único control de los probados que detecta este fallo: el parser XML es estricto donde el del navegador es tolerante.

**Regla general:** el `getBBox` valida **composición**, no **integridad**. Hay que validar la estructura antes de medirla, y repetir la **captura visual** después de cualquier retoque de los `.md`, no solo el QA programático.

### Origen

- **Esqueleto**: `Test_Prompting/temas agosto/32.md` (6 bloques de primer nivel, 14 subapartados, sin quinto nivel salvo el señalado).
- **Sin material de cliente**: no se ha facilitado documentación específica para este tema. Contenido generado desde normativa oficial y estándares, todo referenciado con ID inline.
- **Plantilla técnica**: T29 (`build_t29.py`, `_build_css.txt`, estructura de 8 pestañas y motor de test con penalización 1/3).
