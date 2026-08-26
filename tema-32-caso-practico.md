# Tema 32 — Casos Prácticos

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.
>
> **Formato**: 3 casos prácticos sobre supuestos reales del Ayuntamiento de Madrid. Cada caso suma **10 puntos**.
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

Los tres casos recorren el supuesto de referencia del tema (ver tema-32-contenido.md, «Convenciones»): el **sistema de tramitación de expedientes de la sede electrónica municipal**. El **Caso 1** trabaja la **categorización, el análisis de riesgos y la seguridad física** del sistema; el **Caso 2**, la **seguridad lógica y la respuesta a un incidente** con datos personales de por medio; y el **Caso 3**, el **diseño criptográfico y de firma electrónica** de un servicio nuevo.

---

## Caso 1 — Categorización, riesgo y protección física del sistema de expedientes

### Enunciado

El IAM va a poner en explotación una nueva versión del **sistema de tramitación de expedientes** de la sede electrónica municipal. El sistema:

- Trata **datos identificativos y de contacto** de la ciudadanía y documentación aportada en los procedimientos; no trata categorías especiales de datos.
- Produce **resoluciones administrativas** firmadas electrónicamente que despliegan efectos jurídicos y son recurribles.
- Debe permitir **imputar cada actuación** a un empleado municipal concreto.
- Es **accesible desde internet** y da servicio a las oficinas de los 21 distritos.
- Se ejecuta en el **centro de proceso de datos del IAM**, ubicado en la **planta baja** de un edificio municipal, en una sala **contigua a un aseo** con bajantes de agua, sin registro de entrada y salida de equipos y con una única acometida eléctrica respaldada por SAI, sin grupo electrógeno.
- Una **caída de un día** es asumible ampliando plazos administrativos.

La dirección pide un informe previo antes de autorizar la puesta en producción.

### Cuestiones

**Cuestión 1 — Categorización (3 puntos).** Asigne un **nivel** a cada una de las cinco dimensiones, **justificando** cada asignación, y determine la **categoría** del sistema explicando la regla aplicada.

**Cuestión 2 — Análisis de riesgo (2 puntos).** Para la amenaza «**inundación de la sala técnica**», identifique el **activo**, la **vulnerabilidad**, el **impacto**, la **dimensión afectada** y **dos salvaguardas** de tipos funcionales distintos.

**Cuestión 3 — Deficiencias de seguridad física (3 puntos).** Enumere las **deficiencias** del emplazamiento descrito, indicando en cada caso **qué medida `mp.if` incumple** y si esa medida es **exigible** al sistema según la categorización de la Cuestión 1.

**Cuestión 4 — Consecuencias de la categoría (2 puntos).** Indique **tres consecuencias normativas** que se derivan de la categoría obtenida y que no serían exigibles si el sistema fuera de categoría BÁSICA.

### Solución orientativa

- **C1**: (§1.2.1) Valoración razonada:

| Dimensión | Nivel | Justificación |
|---|---|---|
| **Confidencialidad** | **MEDIO** | Datos personales identificativos y de contacto: su revelación causa un perjuicio **grave** y de difícil reparación a los individuos, pero no muy grave al no haber categorías especiales |
| **Integridad** | **ALTO** | Una resolución alterada produce **efectos jurídicos indebidos**: incumplimiento grave del ordenamiento y perjuicio muy grave para el afectado |
| **Trazabilidad** | **MEDIO** | El enunciado exige imputar cada actuación; su pérdida impide exigir responsabilidades, con perjuicio grave, pero no anula la capacidad de la organización |
| **Autenticidad** | **ALTO** | La identidad del solicitante y del firmante **condiciona la validez del acto**: una suplantación produce actos administrativos nulos |
| **Disponibilidad** | **MEDIO** | El propio enunciado admite que una caída de un día es reparable ampliando plazos: perjuicio grave, no muy grave |

  **Categoría: ALTA.** Regla del anexo I.4: el sistema es de categoría ALTA porque **alguna** dimensión alcanza el nivel ALTO —aquí dos, integridad y autenticidad—. Es esencial añadir el matiz del anexo I.4.2: **determinar la categoría no eleva el nivel de las demás dimensiones**, de modo que confidencialidad, trazabilidad y disponibilidad siguen en MEDIO y se les aplican las medidas correspondientes a ese nivel, no al ALTO.

- **C2**: (§1.1.3, §2.2.2)

| Elemento | Contenido |
|---|---|
| **Activo** | Los servidores y el equipamiento de la sala técnica (activos de soporte) y, por dependencia, el **servicio de tramitación** y la **información** de los expedientes (activos esenciales) |
| **Amenaza** | Daños por agua — grupo **[N] desastres naturales** o **[I] de origen industrial** según su origen (crecida o rotura de una conducción) |
| **Vulnerabilidad** | Ubicación **en planta baja**, **contigua a un aseo con bajantes**, sin detección de fugas ni barrera física |
| **Impacto** | Destrucción o parada del equipamiento → **indisponibilidad prolongada** del servicio de tramitación y, en el peor caso, **pérdida de información** |
| **Dimensión afectada** | Principalmente **disponibilidad**; secundariamente **integridad** si hay pérdida de datos no respaldados |
| **Salvaguardas** | **Preventiva**: reubicar la sala fuera de la vertical de conducciones o instalar barrera estanca y desviar bajantes. **Detectiva**: sensores de fuga de agua bajo el falso suelo con alarma. (Como **recuperativa** cabría añadir la restauración desde copia de seguridad en emplazamiento alternativo) |

  Conviene señalar expresamente que la amenaza **no se puede eliminar** —el agua seguirá existiendo—: lo que se corrige es la **vulnerabilidad** (la ubicación) y lo que se reduce es el **impacto** (detección temprana y recuperación).

- **C3**: (§2.1.1, §2.2)

| Deficiencia | Medida incumplida | ¿Exigible? |
|---|---|---|
| Sala en **planta baja y junto a bajantes de agua**, sin protección frente a inundación | **`mp.if.6`** — protección frente a inundaciones | **Sí**: aplica desde nivel **MEDIO** de disponibilidad, y aquí es MEDIO |
| **Sin registro de entrada y salida de equipamiento** | **`mp.if.7`** — registro pormenorizado con identificación de quien autoriza | **Sí**: aplica en las **tres categorías** |
| **Una sola acometida y sin grupo electrógeno** | **`mp.if.4` + R1** — suministro eléctrico de emergencia | **Sí**: el R1 se exige desde nivel **MEDIO** de disponibilidad. Ahora bien, el R1 solo obliga a garantizar el tiempo para una **terminación ordenada**; si el SAI lo cubre, el R1 se cumple, y el grupo electrógeno sería exigible por continuidad únicamente si la disponibilidad fuese ALTA |
| No consta que la sala sea **área separada y específica** con accesos controlados | **`mp.if.1`** — áreas separadas y con control de acceso | **Sí**: aplica en las tres categorías |
| No consta procedimiento de **identificación y registro de personas** que acceden | **`mp.if.2`** — identificación de las personas | **Sí**: aplica en las tres categorías |
| No consta control de **temperatura, humedad ni protección del cableado** | **`mp.if.3`** — acondicionamiento de los locales | **Sí**: aplica en las tres categorías |

  Se valora positivamente que la respuesta distinga entre **lo que el enunciado dice que falta** y **lo que el enunciado no acredita**, y que no se exija `op.cont.2` a `op.cont.4` (plan de continuidad, pruebas y medios alternativos), que el anexo II reserva al nivel **ALTO** de disponibilidad y aquí sería MEDIO.

- **C4**: (§1.2.1, §4.2.1, §5.2.2, §6.2.1) Tres consecuencias de la categoría **ALTA** frente a la BÁSICA, a elegir entre:
  1. **Auditoría** de la seguridad **al menos cada dos años** [art. 31], frente a la simple **autoevaluación** que basta en BÁSICA.
  2. **`mp.info.3` + R1 + R2 + R3 + R4** para la firma electrónica: certificados **cualificados**, algoritmos autorizados por el CCN, **validación duradera** y **segundo factor** —frente a BÁSICA, donde bastaría cualquier firma admitida en derecho, incluido el CSV—. (Nota: por integridad y autenticidad ALTO, este bloque se aplica completo.)
  3. **`op.acc.6` + R5 + R6 + R7** además de R8 y R9: registro de accesos con éxito y fallidos, **reautenticación** en puntos definidos y **suspensión de credenciales por no utilización**.
  4. **`op.exp.6` + R1 + R2 + R3 + R4**: escaneo periódico, revisión al arranque, **lista blanca de aplicaciones** y **EDR**.
  5. **`op.acc.3`** (segregación de funciones) con refuerzo, y **`op.exp.5`** (gestión de cambios), que **no aplican** en categoría BÁSICA.
  6. **`mp.si.2` + R1 + R2** para los soportes: cifrado con productos certificados y **cifrado de las copias de seguridad**.

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Cinco niveles asignados con justificación y categoría correcta con la regla del máximo | 3 |
| Descomposición completa del riesgo de inundación y dos salvaguardas de tipos distintos | 2 |
| Deficiencias identificadas con la medida `mp.if` incumplida y su exigibilidad razonada | 3 |
| Tres consecuencias normativas correctas de la categoría ALTA | 2 |

---

## Caso 2 — Incidente de seguridad en una oficina de distrito

### Enunciado

Un lunes a las 8:55, el CAU recibe tres llamadas de la misma **oficina de un distrito**. Una tramitadora informa de que **los ficheros de su unidad de red aparecen renombrados y no se abren**, y de que ha aparecido un aviso en pantalla pidiendo un pago para recuperarlos. En la revisión inicial se comprueba que:

- El viernes anterior, esa tramitadora **abrió un adjunto** de un correo que suplantaba a un proveedor municipal.
- Su usuario tenía asignados los permisos de su puesto **actual y los de su puesto anterior** en otra unidad, porque en el cambio de destino nadie retiró los antiguos.
- La oficina comparte una **cuenta genérica** `mostrador02` que utilizan indistintamente cuatro personas para consultas rápidas.
- El servidor de ficheros comprometido llevaba **cuatro meses sin aplicar** un parche de una vulnerabilidad con `CVSS 8,8` y explotación pública conocida.
- Los atacantes han dejado un mensaje afirmando que, además de cifrar, **han descargado** una copia de los ficheros, que incluyen expedientes con datos personales de vecinos.

### Cuestiones

**Cuestión 1 — Dimensiones y cadena del ataque (2 puntos).** Indique **qué dimensiones de la seguridad** se han visto comprometidas y en qué **fases de la cadena de ataque** puede situarse lo ocurrido, señalando en cada fase **qué control habría podido cortarla**.

**Cuestión 2 — Fallos de seguridad lógica (3 puntos).** Identifique los **tres fallos de control de acceso** que el enunciado revela, indicando la **medida del ENS** que cada uno incumple y por qué agrava el incidente.

**Cuestión 3 — Gestión de la vulnerabilidad no parcheada (2 puntos).** Valore el retraso de cuatro meses y explique, con el vocabulario del tema, **por qué esa vulnerabilidad debía haberse tratado con prioridad** y qué medida del ENS regula el proceso.

**Cuestión 4 — Obligaciones de notificación (3 puntos).** Enumere las **notificaciones** que proceden, con su **destinatario**, su **plazo** y su **condición de procedencia**, y señale qué circunstancia del enunciado impide acogerse a la principal excepción de una de ellas.

### Solución orientativa

- **C1**: (§1.1.2, §4.1.2) **Dimensiones comprometidas**: **disponibilidad** (los ficheros están cifrados y la unidad no puede trabajar), **confidencialidad** (la exfiltración anunciada), **integridad** (los ficheros han sido alterados) y **trazabilidad** (la cuenta genérica impide imputar actuaciones a una persona concreta). La **autenticidad** se ve afectada en el vector de entrada: el correo suplantaba a un proveedor.

  Fases y controles de corte:

| Fase | Qué ocurrió | Control que habría cortado |
|---|---|---|
| **Entrega** | Correo con adjunto que suplanta a un proveedor | Filtrado de correo (`mp.s.1`), SPF/DKIM/DMARC y **concienciación** (`mp.per.3`) |
| **Explotación** | Ejecución del adjunto y aprovechamiento del servidor sin parchear | **Parcheo** (`op.exp.4`) y **bastionado** (`op.exp.2`) |
| **Instalación** | Persistencia del código dañino | **Lista blanca** (`op.exp.6.r3`) y **EDR** (`op.exp.6.r4`) |
| **Mando y control** | Comunicación con el servidor del atacante | Control de la **salida** y detección de intrusión (`op.mon.1`) |
| **Acciones sobre el objetivo** | Cifrado y exfiltración masiva | **Mínimo privilegio**, segmentación, y **copias aisladas** (`mp.info.6`) para recuperar |

- **C2**: (§3.1, §3.2.1)

| Fallo | Medida incumplida | Por qué agrava |
|---|---|---|
| **Acumulación de privilegios**: conserva los permisos del puesto anterior | **`op.acc.4`** (proceso de gestión de derechos de acceso) y art. 20 (**mínimo privilegio**) | El código dañino se ejecuta **con los permisos del usuario**: cuantos más tenga, más ficheros cifra y exfiltra. Es la causa directa de que el alcance sea mayor |
| **Cuenta genérica compartida** `mostrador02` | **`op.acc.1`** (identificación singular) y **art. 24.3** del ENS | Destruye la **trazabilidad**: impide saber quién hizo qué durante el incidente y compromete la investigación forense y la exigencia de responsabilidades |
| **No retirada de permisos al cambiar de destino** (fallo del procedimiento de modificación) | **`op.acc.4`** y, en su caso, **`op.acc.3`** (segregación de funciones) | El ciclo alta-modificación-revisión-baja falla en su punto más crítico. La **revisión periódica y recertificación** por los responsables funcionales lo habría detectado |

  Se valora que la respuesta señale que estos tres fallos **no causaron** el incidente —lo causaron el correo y la vulnerabilidad— pero **multiplicaron su impacto**, que es exactamente la función de las líneas de defensa interiores.

- **C3**: (§4.2.1) El retraso es **injustificable** con los datos del enunciado, y la razón no es la puntuación por sí sola. Riesgo = **gravedad × exposición × criticidad del activo**: aquí concurren una gravedad **alta** (CVSS 8,8), **explotación pública conocida** —lo que eleva la probabilidad de materialización de teórica a real— y un activo **crítico** (servidor de ficheros de una unidad tramitadora). Con esos tres factores, el caso exigía un **parche de emergencia fuera de la ventana ordinaria**, no el ciclo normal.

  La medida aplicable es **`op.exp.4`**, que obliga a (a) seguimiento continuo de los **anuncios de defectos** del fabricante, (b) disponer de un **procedimiento para analizar, priorizar y determinar cuándo aplicar** las actualizaciones, teniendo en cuenta **la variación del riesgo según se implante o no**, y (c) que el mantenimiento lo realice solo **personal autorizado**. Su refuerzo **R1** (pruebas en preproducción) y **R2** (mecanismo de reversión) son precisamente los que permiten parchear rápido **sin** asumir el riesgo de romper el servicio, de modo que no sirven como excusa para no parchear. Durante los cuatro meses de retraso, la **ventana de exposición** estuvo abierta con parche disponible y no aplicado.

- **C4**: (§1.2.2)

| Notificación | Destinatario | Plazo | Condición |
|---|---|---|---|
| **Ciberincidente** conforme al ENS y su instrucción técnica | **CCN-CERT** (CSIRT de referencia del sector público), según taxonomía y peligrosidad de la **CCN-STIC 817** | Según la clasificación del incidente | Siempre que se produzca un incidente de los previstos, art. 25 y `op.exp.7` |
| **Violación de seguridad de datos personales** | **AEPD** (autoridad de control) | Sin dilación indebida y, de ser posible, **72 horas** desde que se tuvo constancia | Salvo que sea **improbable** que suponga riesgo para derechos y libertades. Aquí **sí procede** |
| **Comunicación a los afectados** | **Personas interesadas** cuyos datos se han visto comprometidos | Sin dilación indebida | Solo si es probable que entrañe un **alto riesgo**. Con exfiltración de expedientes, **procede** |
| **Documentación interna** | Registro interno del responsable | — | **Siempre**, art. 33.5 del RGPD, se notifique o no |
| Comunicación interna | Responsable de seguridad, DPD, responsable del servicio y dirección | Inmediata | Siempre |

  La **excepción** que no puede invocarse es la del **art. 34.3.a del RGPD**: no procede eximirse de comunicar a los afectados alegando que los datos eran ininteligibles para el atacante, porque los ficheros **no estaban cifrados en reposo** —el cifrado lo aplicó el atacante, no la organización—. Es una distinción que conviene explicitar: el cifrado que exime es el que **impide al atacante leer** lo que se llevó, no el que el atacante impone.

  Se valora que la respuesta advierta de que **los plazos corren en paralelo**, no de forma sucesiva, y que el registro exigido por `op.exp.9` es lo que permite acreditar después que se cumplieron.

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Dimensiones comprometidas correctas y fases de la cadena con su control de corte | 2 |
| Tres fallos de control de acceso con medida incumplida y agravamiento explicado | 3 |
| Priorización razonada por gravedad, exposición y criticidad, y cita de `op.exp.4` | 2 |
| Notificaciones completas con destinatario, plazo y condición, y excepción del art. 34.3.a descartada | 3 |

---

## Caso 3 — Diseño criptográfico y de firma de un nuevo servicio de la sede

### Enunciado

El Ayuntamiento va a habilitar en su sede electrónica un nuevo procedimiento de **licencias de actividad**. El diseño previsto incluye:

1. La ciudadanía presenta la solicitud **identificándose electrónicamente** y adjuntando documentación técnica.
2. El personal municipal **tramita** el expediente desde las oficinas de distrito y desde el CPD.
3. El órgano competente **firma la resolución**, que puede ser recurrida en vía administrativa y contencioso-administrativa **durante años**.
4. Cada mes, un proceso **automatizado** genera y emite **certificados de situación** de expedientes, sin intervención de persona alguna.
5. Los expedientes se conservan en el **archivo electrónico** durante décadas.
6. Semanalmente se lleva una **copia de seguridad en soporte extraíble** al centro de respaldo, situado en otro edificio municipal.

El sistema es de **categoría ALTA**, con integridad y autenticidad en nivel ALTO y confidencialidad en MEDIO.

### Cuestiones

**Cuestión 1 — Identificación y firma (3 puntos).** Indique qué **sistemas de identificación** admite la Ley 39/2015 para el punto 1 y qué **modalidad y formato de firma** corresponde al punto 3, justificando la elección con los requisitos de eIDAS y con los refuerzos de `mp.info.3` aplicables.

**Cuestión 2 — La actuación automatizada (2 puntos).** Explique por qué el punto 4 **no** puede resolverse con la firma de una persona física, qué figura corresponde y cómo puede verificarse una copia en papel de esos certificados.

**Cuestión 3 — Protección de los canales y de los soportes (3 puntos).** Para los trayectos implicados —navegador de la ciudadanía, oficina de distrito, administración de los servidores y traslado de la copia de seguridad— indique el **mecanismo criptográfico** adecuado y la **medida del ENS** que lo obliga.

**Cuestión 4 — Conservación a largo plazo (2 puntos).** Explique qué problema plantea el punto 5 para la verificación de las firmas y qué mecanismos lo resuelven, relacionándolos con el refuerzo `mp.info.3.r3` y con `mp.info.4`.

### Solución orientativa

- **C1**: (§6.2.1) **Identificación** [L39-2015, art. 9.2]: (a) sistemas basados en **certificados electrónicos cualificados de firma electrónica** —incluido el **DNI electrónico**—; (b) sistemas basados en **certificados electrónicos cualificados de sello electrónico**; y (c) **cualquier otro sistema que las Administraciones consideren válido**, previa comunicación, categoría en la que se encuadra **Cl@ve**.

  **Firma de la resolución** [art. 10.2]: **firma electrónica avanzada basada en certificado electrónico cualificado** de firma, del titular del órgano competente, alojada en **tarjeta criptográfica** —el soporte físico garantiza el **control exclusivo** de los datos de creación que exige el art. 26.c de eIDAS y satisface a la vez el segundo factor—. Con integridad y autenticidad en **ALTO** se aplican `mp.info.3` **+ R1 + R2 + R3 + R4**: certificado **cualificado** (R1), **algoritmos y parámetros autorizados por el CCN** conforme a la **CCN-STIC 807** (R2), **verificación y validación durante el tiempo requerido** por la actividad administrativa (R3) y **segundo factor** del tipo «algo que se sabe» o «algo que se es» (R4), que el PIN de la tarjeta cumple.

  **Formato**: **PAdES** —la resolución es un PDF legible por la persona interesada y la firma queda incrustada y verificable en el propio visor— y, dada la conservación exigida, en nivel **PAdES-LTA**. Se valora que se justifique por qué **no basta -B**: sin sello de tiempo ni datos de validación embebidos, la firma dejaría de poder demostrarse cuando el certificado del firmante caduque.

  Se valora asimismo que se advierta de que **no es imprescindible la firma cualificada** en sentido estricto de eIDAS —la Ley 39/2015 admite la avanzada con certificado cualificado— pero que, de emplearse, tendría efecto equivalente al de la firma manuscrita en toda la Unión [art. 25.2].

- **C2**: (§6.2.1) En una **actuación administrativa automatizada** no hay voluntad de persona física que expresar: no hay firmante. La figura que corresponde es el **sello electrónico de órgano** basado en **certificado cualificado de sello**, previsto en el art. 42 de la Ley 40/2015, que garantiza el **origen y la integridad** del documento, no la voluntad. Es la distinción firma/sello: la **firma** es de persona **física**; el **sello**, de persona **jurídica** u órgano.

  La verificación de una copia en papel se resuelve con el **código seguro de verificación (CSV)**: un identificador único impreso en el documento que permite contrastar su autenticidad accediendo a la sede electrónica del Ayuntamiento. El ENS lo admite expresamente en `mp.info.3.1` entre las firmas previstas en el ordenamiento. Debe añadirse que el CSV es el **escalón básico**: sirve como mecanismo de verificación de la copia, no sustituye a la firma o el sello del documento electrónico original en un sistema de nivel ALTO.

- **C3**: (§5.2)

| Trayecto | Mecanismo | Medida del ENS que lo obliga |
|---|---|---|
| Navegador de la ciudadanía ↔ sede | **HTTPS con TLS 1.2 o 1.3**, certificado de **sede electrónica** de prestador cualificado, **HSTS**, suites con **confidencialidad directa** (ECDHE) y cifrado **AEAD** | `mp.com.2` (confidencialidad) y `mp.com.3` (integridad y autenticidad, que exige **asegurar la autenticidad del otro extremo antes de intercambiar información**); `mp.s.2` protección de servicios web |
| Oficina de distrito ↔ CPD, si discurre fuera del propio dominio de seguridad | **VPN cifrada**, típicamente **IPsec con ESP en modo túnel** entre pasarelas, con **IKEv2** | `mp.com.2` («se emplearán redes privadas virtuales cifradas cuando la comunicación discurra por redes fuera del propio dominio de seguridad») + **R1** algoritmos autorizados por el CCN, y en nivel ALTO de confidencialidad **+R2 y +R3**. Aquí, con confidencialidad **MEDIO**, se exige `mp.com.2 + R1` |
| Administración remota de los servidores | **SSH** (puerto 22) con autenticación por **par de claves**, root deshabilitado, origen restringido y sesión registrada | `op.acc.6.r9` (acceso remoto: autorizado, **tráfico cifrado**, deshabilitado cuando no se use y con **registros de auditoría**), `op.acc.6.r8` (doble factor desde zona no controlada) y `op.exp.2` (configuración de seguridad) |
| Traslado semanal de la copia de seguridad en soporte extraíble | **Cifrado del soporte** con algoritmos autorizados por el CCN, más control de custodia y transporte | **`mp.si.2` Criptografía**, que se aplica **en particular a los dispositivos removibles cuando salen de un área controlada**; con confidencialidad MEDIO, `mp.si.2` aplica. Además `mp.si.3` custodia y `mp.si.4` transporte, y `mp.info.6` copias de seguridad |

  Se valora que se justifique la elección **por la capa** en la que actúa cada protocolo: IPsec en **red** protege todo el tráfico de forma transparente a las aplicaciones, TLS en **transporte** protege el tráfico de la aplicación que lo invoca, y SSH en **aplicación** protege la sesión de administración. Y que se recuerde la protección de las claves con **`op.exp.10`**, que exige custodiarlas en las cinco fases de su ciclo de vida y mantener **los medios de generación aislados de los de explotación**.

- **C4**: (§6.2.1) El problema es que **los certificados caducan a los pocos años y los expedientes se conservan durante décadas**. Sin medidas adicionales, llegado el momento no podría demostrarse que la firma se realizó **cuando el certificado estaba vigente y no revocado**, y una firma perfectamente legítima dejaría de poder acreditarse. A ello se suma que los **algoritmos envejecen**: lo que hoy es resistente puede no serlo en veinte años.

  Mecanismos que lo resuelven:

  1. **Sello de tiempo cualificado** sobre la firma, que prueba el **instante** en que se firmó (nivel **-T**). Es lo que permite validar el requisito de vigencia en el momento de la firma.
  2. **Incorporación de los datos de validación** —cadena completa de certificados y respuestas CRL u OCSP del momento de la firma— dentro del propio documento (nivel **-LT**), de modo que la validación no dependa de que los servicios de la autoridad de certificación sigan existiendo.
  3. **Sellos de tiempo de archivo renovables** (nivel **-LTA**), que se vuelven a aplicar antes de que el algoritmo anterior quede obsoleto, manteniendo viva la cadena de prueba.

  Relación normativa: el refuerzo **`mp.info.3.r3`** —garantizar la verificación y validación de la firma «durante el tiempo requerido por la actividad administrativa», adjuntando o referenciando toda la información pertinente— es, en términos técnicos, **exactamente la exigencia de un nivel -LT o -LTA**. Y **`mp.info.4` Sellos de tiempo** (dimensión **T**, exigible **solo en nivel ALTO**) obliga a aplicarlos a la información susceptible de ser **evidencia electrónica futura**, a proteger los datos de verificación con la misma seguridad que la información fechada, a **renovarlos regularmente** y a emplear **sellos cualificados**.

  Se valora que se advierta de que, en este caso, la dimensión de trazabilidad está en **MEDIO** y `mp.info.4` solo se exige en ALTO: el sellado de tiempo se incorpora aquí **por exigencia funcional** de la conservación y por `mp.info.3.r3`, no porque `mp.info.4` lo imponga. Distinguir lo que obliga la norma de lo que impone el buen diseño es parte de la respuesta.

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Sistemas de identificación del art. 9, modalidad y formato de firma justificados con eIDAS y `mp.info.3` | 3 |
| Sello de órgano correctamente diferenciado de la firma y CSV como mecanismo de verificación | 2 |
| Cuatro trayectos con mecanismo criptográfico adecuado y medida del ENS que lo obliga | 3 |
| Problema de la conservación a largo plazo y mecanismos -T, -LT y -LTA relacionados con la norma | 2 |
