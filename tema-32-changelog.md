# Tema 32 — Changelog

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.

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

**D2 quedó truncado por un `sed` y ningún control lo detectó.** Al corregir las tildes del texto de los SVG se usó `sed -i ''` con patrones que terminaban en `<` justo antes del delimitador `/` (`s/>degradacion de las</>degradación de las</`). En **D2** eso se comió el `<` de un `</text>` de cierre, dejando `degradación de las/text>`: el SVG quedó **mal formado** y el navegador **descartó en silencio** todo lo que venía después —la caja RIESGO, las tres flechas, el bloque de tratamiento del riesgo y el riesgo residual—.

Lo grave no es la errata, es que **pasó los tres controles**:
- El **getBBox** dio «0 desbordes y 0 colisiones»: un SVG truncado no tiene elementos que desborden ni colisionen, así que devuelve un **falso OK**.
- El **recuento de `<svg`** seguía siendo 18, porque la etiqueta de apertura estaba intacta.
- La **revisión visual** se hizo **antes** de aplicar el `sed`, y no se repitió después.

Detectado por Joan al mirar el tema publicado.

**Dos lecciones incorporadas:**

1. **No usar `sed` sobre estos ficheros para tocar texto con acentos o marcado.** Usar Python con `str.replace()` y una aserción del número de coincidencias, como el `fix_tildes.py` de esta misma sesión, que no rompió nada.
2. **Validar los SVG como XML antes de medirlos.** Añadida al arranque del QA una pasada con `xml.etree.ElementTree.fromstring()` sobre cada `<svg>...</svg>`, que aborta si alguno está mal formado, más una comprobación de que el número de SVG del DOM coincide con el del fichero. Sin esa pasada, el getBBox miente.

**Regla general que se deriva:** después de cualquier retoque sobre los `.md`, hay que **repetir la captura visual**, no solo el QA programático.

### Origen

- **Esqueleto**: `Test_Prompting/temas agosto/32.md` (6 bloques de primer nivel, 14 subapartados, sin quinto nivel salvo el señalado).
- **Sin material de cliente**: no se ha facilitado documentación específica para este tema. Contenido generado desde normativa oficial y estándares, todo referenciado con ID inline.
- **Plantilla técnica**: T29 (`build_t29.py`, `_build_css.txt`, estructura de 8 pestañas y motor de test con penalización 1/3).
