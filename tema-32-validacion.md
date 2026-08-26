# Tema 32 — Validación

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.
>
> **Versión**: v1.0 — **Pendiente de validación por María, Ana y el IAM**
> **Fecha**: 2026-08-27

---

## 1. Cobertura del temario oficial

El enunciado oficial (BOAM 10.032, tema 32) enumera **seis materias**. Correspondencia con las secciones del contenido:

| Enunciado oficial | Sección | Estado |
|---|---|---|
| Conceptos de seguridad de los sistemas de información | §1 | ✅ Completo |
| Seguridad física | §2 | ✅ Completo |
| Seguridad lógica | §3 | ✅ Completo |
| Amenazas y vulnerabilidades | §4 | ✅ Completo |
| Técnicas criptográficas y protocolos seguros | §5 | ✅ Completo |
| Mecanismos de firma digital | §6 | ✅ Completo |

El **esqueleto de partida** (`Test_Prompting/temas agosto/32.md`) se ha seguido **literalmente** en sus seis bloques de primer nivel y en sus catorce subapartados. Ver la observación 1 sobre el único ajuste de estructura realizado.

## 2. Contenido teórico

- **6 secciones · 14 subsecciones · 22 epígrafes numerados** (numeración de tres niveles, `N.M.K`, coherente con el resto de la serie técnica).
- **~25.000 palabras** medidas con `wc -w`. Es **el tema más extenso de toda la serie** hasta la fecha, por delante de T29 (≈21.200) y T28 (≈18.900). La causa es estructural y no de estilo: el enunciado oficial reúne **seis materias** que en otros temarios son temas independientes.
- **4 tipos de callout**: `[DATO CLAVE EXAMEN]`, `[EJERCICIO RESUELTO]`, `[EJEMPLO AYTO MADRID]` y `[REFERENCIA CRUZADA]`.
- **Caso de referencia transversal**: el sistema de tramitación de expedientes de la sede electrónica municipal, que atraviesa las seis secciones y enlaza con los tres casos prácticos.
- Cierre con un bloque de **«los siete datos que no se pueden fallar»**, no numerado, a modo de resumen memorístico.

## 3. Fuentes

- **Tier 1**: 40 referencias (ENS, CCN-STIC, MAGERIT, ISO/IEC 27001/27002/27005/22301, RGPD, LOPDGDD, eIDAS, eIDAS 2, Ley 6/2020, Leyes 39 y 40 de 2015, RD 203/2021, ENI, RD 43/2021, NIS2, RD 704/2011, RFC del IETF, FIPS del NIST, normas EN/TS de ETSI).
- **Tier 2**: 21 referencias (OWASP 2025 y 2021, CVE, CVSS, CWE, MITRE ATT&CK, cadena de ataque, STRIDE, modelos formales, TIA-942, NFPA 75, ASHRAE, TPM, FIDO2, HSM, FNMT, CCN-CERT).
- **Tier 3**: 4 referencias de contexto municipal.
- **Verificación contra fuente oficial** (no de memoria):
  - **ENS**: descargado el PDF del BOE (`BOE-A-2022-7191`) y extraído con `pdftotext -layout`. De ahí proceden, literalmente, los arts. 5-27, 31 y 40, el anexo I (dimensiones, niveles y categorías), el anexo IV (glosario) y las medidas del anexo II citadas: `mp.if.1-7`, `op.acc.1-6`, `op.exp.4`, `op.exp.6`, `op.exp.10`, `mp.com.2-3`, `mp.si.2`, `mp.info.3-4`.
  - **Ley 39/2015**: arts. 9 y 10 contrastados contra el texto consolidado del BOE.
  - **OWASP Top 10:2025**: lista de las diez categorías contrastada contra `owasp.org/Top10/2025/`.
  - **eIDAS 2**: número, fecha y entrada en vigor del Reglamento (UE) 2024/1183 verificados.
  - **NIST post-cuántico**: FIPS 203/204/205 y su publicación en agosto de 2024, verificados.

## 4. Test (60 preguntas)

- **60 preguntas** de 3 opciones (A/B/C), formato oficial de la oposición, con penalización de **1/3** en el motor de corrección.
- **Distribución de la respuesta correcta: 20 A / 20 B / 20 C**, conseguida **a la primera** por haber fijado la secuencia de letras **antes** de redactar (lección aprendida en T23) y verificada por script.
- Reparto por materia: P1-P12 conceptos, dimensiones, riesgo y marco normativo · P13-P20 seguridad física · P21-P30 seguridad lógica · P31-P40 amenazas y vulnerabilidades · P41-P51 criptografía y protocolos · P52-P60 firma electrónica y PKI.
- Verificación automática: 60 preguntas, 3 opciones únicas por pregunta, coincidencia exacta entre el texto de la opción correcta y el de la solución, y referencia a epígrafe y fuente en las 60.

## 5. Casos prácticos (3)

Los tres se sitúan en el Ayuntamiento de Madrid y comparten el sistema de referencia del tema:

1. **Categorización, riesgo y protección física** del sistema de expedientes (§1 y §2): valoración de las cinco dimensiones, descomposición del riesgo de inundación, deficiencias del emplazamiento contra `mp.if` y consecuencias normativas de la categoría ALTA.
2. **Incidente de seguridad en una oficina de distrito** (§3 y §4): secuestro de datos con exfiltración, fallos de control de acceso que agravaron el impacto, gestión de la vulnerabilidad no parcheada y mapa completo de notificaciones con sus plazos.
3. **Diseño criptográfico y de firma de un servicio nuevo** (§5 y §6): identificación y firma conforme a la Ley 39/2015 y a eIDAS, actuación automatizada con sello de órgano y CSV, protección de cuatro trayectos distintos y conservación a largo plazo con niveles -T, -LT y -LTA.

Cada caso suma **10 puntos** repartidos en cuatro cuestiones, con solución orientativa y tabla de criterios de evaluación.

## 6. Diagramas (18 SVG)

- **18 diagramas SVG inline**, sin dependencias externas, con `role="img"` y `aria-label` descriptivo en los 18.
- Clases CSS con **sufijo numérico único** por diagrama (`.t1`…`.n18`), para evitar el bug sistémico de colisión de estilos detectado en T5.
- Paleta del Ayuntamiento: `#0055a0` primario, `#d13c3c` alerta, `#2d8659` ventaja, `#e89822` callout.
- Todos con la línea `[Fuente: …]` a **8 px o más** del borde inferior del `viewBox` (regla derivada del QA de T28).
- Reparto por sección: §1 → D1-D4 · §2 → D5-D6 · §3 → D7-D9 · §4 → D10-D12 · §5 → D13-D15 · §6 → D16-D18.

## 7. Referencias cruzadas a otros temas

Validadas contra el temario oficial BOAM 10.032:

| Tema citado | Enunciado oficial | Motivo de la cita |
|---|---|---|
| **T6** | LPACAP: derechos y registros · transparencia | Derechos de la ciudadanía y registros |
| **T7** | Procedimiento administrativo y recursos | Efectos del acto firmado |
| **T12** | Periféricos, impresión, almacenamiento | Soportes de información |
| **T14** | Sistemas operativos | Bastionado y mecanismos del SO |
| **T15, T17, T19** | Bases de datos y SQL | Base sobre la que opera la inyección SQL |
| **T23** | Aplicaciones web, HTML, lenguajes de script | OWASP y ataques web |
| **T25** | Accesibilidad, confidencialidad y disponibilidad en el puesto · seguridad en el desarrollo | Puesto de usuario y desarrollo seguro |
| **T26** | Almacenamiento, backup y recuperación | Continuidad, RTO/RPO, copias |
| **T27** | Administración del SO · actualización y mantenimiento | Explotación de `op.exp.4` |
| **T28** | Virtualización de sistemas y de puestos | Recuperación en otro emplazamiento |
| **T29** | Control remoto y gestión de incidencias | Ciclo de vida de la incidencia |
| **T30** | Administración de redes de área local | Gestión de usuarios y dispositivos |
| **T31** | Cloud: IaaS, PaaS, SaaS | Emplazamiento alternativo y `op.nub.1` |
| **T34** | Modelo TCP/IP y OSI | Capa en que actúa cada protocolo seguro |
| **T35** | Internet · HTTP, HTTPS y SSL/TLS | Arquitectura de red de HTTPS |
| **T36** | Seguridad en redes · perimetral · VPN · puesto | Despliegue de cortafuegos, IDS/IPS y VPN |
| **T39** | Principios básicos del ENS y del ENI | Desarrollo completo del ENS y del ENI |

Todas correctas. **No** se ha citado ningún tema por «RGPD», siguiendo la advertencia registrada en el temario de referencia: el RGPD no es tema dedicado.

## 8. Calidad editorial

- Ortografía revisada con **hunspell es_ES** más barrido dirigido de tildes y eñes en prosa, tablas, texto visible de los SVG y `aria-label`. Los avisos restantes son vocabulario técnico inglés y siglas (*ransomware*, *phishing*, *hash*, *stapling*, RDP, CVSS…), tratados como falsos positivos según la lección registrada para temas técnicos.
- Terminología en español con el término inglés entre paréntesis y en cursiva la primera vez (*ransomware* → secuestro de datos; *phishing* → suplantación de identidad; *hardening* → bastionado; *forward secrecy* → confidencialidad directa).
- Comprobación de asteriscos crudos en el `index.html` generado, tras excluir `<script>`, `<svg>` y `<pre><code>` (bug del conversor detectado en T26 y T27, ya corregido en el builder de este tema).
- Sin fragmentos de código: el enunciado no incluye ningún lenguaje de programación y lo memorizable de este tema son **códigos de medida del ENS, puertos, números de protocolo, artículos y umbrales**, concentrados en tablas y en los diagramas D1, D5, D12, D15 y D18.

---

## Observaciones abiertas — a validar por María, Ana y el IAM

1. **Un único ajuste de estructura sobre el esqueleto.** El esqueleto oficial anida bajo `#### Concepto de Seguridad de la Información` un quinto nivel (`##### Confidencialidad, Integridad, Disponibilidad, Autenticidad y No Repudio`). Para no romper la numeración de tres niveles de toda la serie (`1.1.1.`) se ha **promovido** ese quinto nivel a epígrafe propio, quedando: 1.1.1 concepto de seguridad · **1.1.2 las cinco dimensiones** · 1.1.3 análisis y gestión de riesgos. La decisión favorece el estudio, porque las dimensiones son el contenido más preguntable de la sección, pero **conviene confirmarla**. Es el mismo tipo de ajuste que se documentó en T27.

2. **Frontera con el Tema 36 (seguridad en redes) y con el Tema 39 (ENS y ENI).** Es el punto más delicado del tema. El enunciado del T32 incluye «protocolos seguros» y «conceptos de seguridad», materias que se solapan con el T36 (seguridad perimetral, acceso remoto seguro, VPN, seguridad en el puesto) y con el T39 (principios básicos del ENS). El criterio aplicado ha sido: **en el T32 se desarrolla el mecanismo criptográfico y el marco de las dimensiones y medidas**; **se remite al T36 el despliegue perimetral** (cortafuegos, IDS/IPS, arquitectura de VPN) y **al T39 la gobernanza del ENS** (conformidad, distintivos, informe del estado de la seguridad, relación con el ENI). ¿Es el reparto que espera el IAM, o prefiere que el T32 desarrolle también el despliegue perimetral aun a costa de duplicar con el T36?

3. **Frontera con el Tema 35 (HTTPS y SSL/TLS).** El T35 incluye expresamente «Protocolos HTTP, HTTPS y SSL/TLS». Aquí se ha tratado TLS desde su **mecanismo criptográfico** (saludo, confidencialidad directa, validación del certificado, estado de las versiones) y se ha remitido al T35 la perspectiva de arquitectura de red. Mismo tipo de decisión que la anterior.

4. **Extensión.** Con ~25.000 palabras es el tema más largo de la serie. Se ha valorado dividirlo, pero el enunciado es unitario y el opositor lo estudiará como un solo tema. Si María o Ana consideran que la extensión es excesiva, los candidatos naturales a recorte son: el detalle de niveles Tier y de agentes de extinción (§2.2), la enumeración de ataques web (§4.1.2, ya cubiertos en el T23) y los modelos formales Bell-LaPadula/Biba/Clark-Wilson (§3.1.2). **No** conviene recortar §1 (dimensiones y riesgo) ni §6 (firma), que son el núcleo preguntable.

5. **OWASP: edición 2025 frente a 2021.** Se ha adoptado el **Top 10:2025** como lista vigente, con la de 2021 documentada en paralelo, porque el T23 se publicó citando la de 2021 y numerosos pliegos siguen usándola. Si el IAM prefiere que ambos temas citen la misma edición, habría que actualizar el T23. **Punto a decidir**, no un error.

6. **Datos volátiles a reverificar antes de cada convocatoria.** (a) Vigencia del **ENS** y de sus instrucciones técnicas de seguridad; (b) versión en vigor de la **CCN-STIC 807** y algoritmos autorizados, que cambian con el estado de la técnica; (c) despliegue de la **cartera europea de identidad digital** de eIDAS 2, cuyo calendario obliga a los Estados miembros a ofrecer una versión y puede alterar el mapa de identificación de la Ley 39/2015; (d) transposición española de la **Directiva NIS2**; (e) edición vigente del **OWASP Top 10** y versión del **CVSS** (v3.1 frente a v4.0); (f) avance de la **migración post-cuántica** y de los estándares FIPS 203/204/205.

7. **Umbrales del CVSS.** Se han recogido los de la **v3.1**, que es la versión que las bases de datos públicas siguen mostrando de forma mayoritaria. La **v4.0** (2023) mantiene el rango 0-10 y reordena las métricas. Si el IAM quiere que el tema se ciña a una sola versión, indicar cuál.

8. **Cifras de disponibilidad de los niveles Tier.** Las cifras del Uptime Institute se han marcado como **orientativas** en el contenido, porque son valores de referencia del sector y no un requisito normativo. Se ha priorizado la **definición conceptual** (Tier III mantenible concurrentemente, Tier IV tolerante a fallos), que es lo que se pregunta.
