# Tema 32 — Test de Autoevaluación

> **Título**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.
> **Formato**: 60 preguntas tipo test A/B/C (formato oficial oposición)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-08-27
> **Fuentes**: ver tema-32-fuentes.md

---

## Instrucciones

- Cada pregunta tiene **3 opciones** (A, B, C). Solo una es correcta.
- Penalización en examen real: respuesta incorrecta descuenta **1/3** del valor de una correcta.
- Tiempo orientativo: 1 minuto por pregunta.
- Distribución: Conceptos, dimensiones, riesgo y marco normativo (P1-P12), Seguridad física (P13-P20), Seguridad lógica y control de acceso (P21-P30), Amenazas y vulnerabilidades (P31-P40), Criptografía y protocolos seguros (P41-P51), Firma electrónica, PKI y servicios de confianza (P52-P60).

---

### Pregunta 1

**¿Cuáles son las cinco dimensiones de la seguridad que establece el anexo I del Esquema Nacional de Seguridad?**

A) Confidencialidad, integridad, disponibilidad, autenticidad y no repudio
B) Confidencialidad, integridad, trazabilidad, autenticidad y disponibilidad
C) Confidencialidad, integridad, disponibilidad, resiliencia y trazabilidad

<details><summary>Respuesta</summary>

**Correcta: B) Confidencialidad, integridad, trazabilidad, autenticidad y disponibilidad** Se abrevian C-I-T-A-D. El **no repudio no es una dimensión del ENS**: es un efecto jurídico que se apoya en autenticidad, integridad y trazabilidad. La resiliencia aparece en el art. 32 del RGPD, no en el anexo I del ENS.

*Referencia: §1.1.2 [ENS]*
</details>

---

### Pregunta 2

**Un sistema de información presenta los siguientes niveles: confidencialidad MEDIO, integridad ALTO, trazabilidad BAJO, autenticidad MEDIO y disponibilidad BAJO. ¿Cuál es su categoría?**

A) ALTA
B) MEDIA, porque tres dimensiones son MEDIO o inferior
C) No puede determinarse sin conocer el valor económico de los activos

<details><summary>Respuesta</summary>

**Correcta: A) ALTA** La regla del anexo I.4 es que **manda la dimensión más alta**: basta con que **una** dimensión alcance nivel ALTO para que el sistema sea de categoría ALTA. Además, determinar la categoría no altera el nivel de las demás dimensiones: la trazabilidad sigue siendo BAJO a efectos de las medidas que se le aplican.

*Referencia: §1.2.1 [ENS]*
</details>

---

### Pregunta 3

**Señale la afirmación correcta sobre amenazas y vulnerabilidades.**

A) La vulnerabilidad es externa al activo y la amenaza es una debilidad propia de este
B) Amenaza y vulnerabilidad son sinónimos en la terminología de MAGERIT
C) La amenaza es externa al activo y no puede eliminarse; la vulnerabilidad es una debilidad propia del activo y sí puede corregirse

<details><summary>Respuesta</summary>

**Correcta: C) La amenaza es externa al activo y no puede eliminarse; la vulnerabilidad es una debilidad propia del activo y sí puede corregirse** Nadie elimina los incendios ni la existencia de atacantes; lo que se corrige es la debilidad que permite que produzcan daño. Las salvaguardas actúan sobre la vulnerabilidad y sobre el impacto, no sobre la amenaza.

*Referencia: §1.1.3 [MAGERIT]*
</details>

---

### Pregunta 4

**¿Qué es el riesgo residual?**

A) El riesgo que permanece después de aplicar las salvaguardas, que nunca es cero y debe ser aceptado formalmente
B) El riesgo que se ha transferido a un tercero mediante un contrato o una póliza de seguro
C) El riesgo cuya probabilidad de materialización se ha estimado como nula

<details><summary>Respuesta</summary>

**Correcta: A) El riesgo que permanece después de aplicar las salvaguardas, que nunca es cero y debe ser aceptado formalmente** La aceptación formal por la dirección es un requisito del proceso, no un trámite: si nadie asume expresamente el riesgo remanente, no hay decisión de gestión.

*Referencia: §1.1.3 [MAGERIT] [ENS]*
</details>

---

### Pregunta 5

**Una cámara de videovigilancia instalada en el acceso a la sala técnica es, atendiendo a su función, una salvaguarda:**

A) Exclusivamente preventiva, porque impide el acceso de personas no autorizadas
B) Disuasoria y detectiva, pero no preventiva, porque no impide físicamente el acceso
C) Correctiva, porque permite reparar el daño causado por el intruso

<details><summary>Respuesta</summary>

**Correcta: B) Disuasoria y detectiva, pero no preventiva, porque no impide físicamente el acceso** La cámara desanima (disuasoria) y registra lo ocurrido (detectiva). La salvaguarda preventiva del ejemplo sería la cerradura o el control de acceso.

*Referencia: §1.1.1 [MAGERIT]*
</details>

---

### Pregunta 6

**Según el art. 11 del ENS, sobre diferenciación de responsabilidades:**

A) El responsable de la seguridad debe depender jerárquicamente del responsable del sistema para garantizar la coordinación
B) Basta con designar un único responsable que asuma información, servicio, seguridad y sistema
C) La responsabilidad de la seguridad estará diferenciada de la responsabilidad sobre la explotación de los sistemas

<details><summary>Respuesta</summary>

**Correcta: C) La responsabilidad de la seguridad estará diferenciada de la responsabilidad sobre la explotación de los sistemas** El art. 13.3 añade que el responsable de la seguridad será **distinto** del responsable del sistema y que **no debe existir dependencia jerárquica** entre ambos; solo excepcionalmente pueden coincidir, aplicando medidas compensatorias.

*Referencia: §1.1.1 [ENS]*
</details>

---

### Pregunta 7

**¿Cuál de las siguientes NO es una de las cuatro opciones de tratamiento del riesgo?**

A) Transferir o compartir
B) Aceptar o asumir
C) Ignorar de forma tácita hasta que se materialice

<details><summary>Respuesta</summary>

**Correcta: C) Ignorar de forma tácita hasta que se materialice** Las cuatro opciones son evitar/eliminar, mitigar/reducir, transferir/compartir y aceptar/asumir. La aceptación es una decisión **expresa y documentada**; la inacción tácita no es una opción de gestión, es una ausencia de gestión.

*Referencia: §1.1.3 [MAGERIT] [ISO27005]*
</details>

---

### Pregunta 8

**El art. 9 del ENS establece la existencia de líneas de defensa. ¿De qué naturaleza deben ser?**

A) Organizativa, física y lógica
B) Exclusivamente lógica, mediante cortafuegos, antivirus y control de acceso
C) Preventiva, detectiva y correctiva

<details><summary>Respuesta</summary>

**Correcta: A) Organizativa, física y lógica** Lo dice literalmente el art. 9.2. Preventiva, detectiva y correctiva es una clasificación **funcional** de las salvaguardas, no de la naturaleza de las líneas de defensa.

*Referencia: §1.1.1 [ENS]*
</details>

---

### Pregunta 9

**¿Qué garantiza el no repudio y con qué mecanismo se consigue?**

A) Que el mensaje no ha sido alterado, y se consigue con un código HMAC compartido entre emisor y receptor
B) Que el autor de una acción no puede negar válidamente haberla realizado, y se consigue con firma electrónica basada en una clave privada bajo control exclusivo del firmante
C) Que el receptor pueda descifrar el mensaje, y se consigue con criptografía simétrica

<details><summary>Respuesta</summary>

**Correcta: B) Que el autor de una acción no puede negar válidamente haberla realizado, y se consigue con firma electrónica basada en una clave privada bajo control exclusivo del firmante** El HMAC **no** da no repudio: su clave la conocen los dos extremos y cualquiera de ellos pudo generarlo. Solo la criptografía asimétrica lo proporciona.

*Referencia: §1.1.2 y §5.1.1 [RFC4949] [EIDAS]*
</details>

---

### Pregunta 10

**Respecto a la notificación de una violación de seguridad de datos personales a la autoridad de control:**

A) Debe efectuarse sin dilación indebida y, de ser posible, en un máximo de 72 horas desde que se tuvo constancia de ella
B) Debe efectuarse siempre en un máximo de 24 horas desde que se produjo la violación
C) Solo procede si la violación afecta a más de mil personas interesadas

<details><summary>Respuesta</summary>

**Correcta: A) Debe efectuarse sin dilación indebida y, de ser posible, en un máximo de 72 horas desde que se tuvo constancia de ella** [RGPD, art. 33]. El cómputo arranca desde que se **tiene constancia**, no desde que ocurrió, y si se supera el plazo hay que justificar la demora. No procede notificar si es improbable que la violación entrañe un riesgo para los derechos y libertades, pero **documentarla siempre es obligatorio**.

*Referencia: §1.2.2 [RGPD]*
</details>

---

### Pregunta 11

**Diferencia entre seudonimización y anonimización:**

A) Son términos equivalentes: ambos dejan los datos fuera del ámbito del RGPD
B) La anonimización es reversible con información adicional y la seudonimización es irreversible
C) La seudonimización es reversible con información adicional guardada aparte, por lo que los datos siguen siendo personales; la anonimización es irreversible y los deja fuera del RGPD

<details><summary>Respuesta</summary>

**Correcta: C) La seudonimización es reversible con información adicional guardada aparte, por lo que los datos siguen siendo personales; la anonimización es irreversible y los deja fuera del RGPD** El art. 32.1.a del RGPD cita la seudonimización y el cifrado como medidas de seguridad; precisamente porque los datos seudonimizados **siguen siendo datos personales**, necesitan protección.

*Referencia: §1.2.2 [RGPD]*
</details>

---

### Pregunta 12

**El plazo máximo de supresión de las imágenes captadas por un sistema de videovigilancia, según la LOPDGDD, es de:**

A) Setenta y dos horas
B) Un mes desde su captación, salvo que deban conservarse para acreditar actos contra la integridad de personas, bienes o instalaciones
C) Seis meses, prorrogables por resolución motivada

<details><summary>Respuesta</summary>

**Correcta: B) Un mes desde su captación, salvo que deban conservarse para acreditar actos contra la integridad de personas, bienes o instalaciones** [LOPDGDD, art. 22.3]. Es el cruce típico entre seguridad física y protección de datos: la cámara es una medida de seguridad, pero su régimen de conservación lo fija la normativa de protección de datos.

*Referencia: §1.2.2 [LOPDGDD]*
</details>

---

### Pregunta 13

**¿Qué exige la medida `mp.if.2` del ENS?**

A) Que el procedimiento de control de acceso identifique a las personas que accedan a los locales con equipamiento esencial, registrando entradas y salidas
B) Que el CPD disponga de sistemas de extinción por gas inerte
C) Que se cifren todos los soportes que salgan de un área controlada

<details><summary>Respuesta</summary>

**Correcta: A) Que el procedimiento de control de acceso identifique a las personas que accedan a los locales con equipamiento esencial, registrando entradas y salidas** Es la medida de **identificación de las personas**, aplicable en las tres categorías. La extinción entra en `mp.if.5` y el cifrado de soportes en `mp.si.2`.

*Referencia: §2.1.1 [ENS]*
</details>

---

### Pregunta 14

**¿Cuál de las siete medidas de la familia `mp.if` NO aplica en nivel BAJO?**

A) `mp.if.4`, energía eléctrica
B) `mp.if.5`, protección frente a incendios
C) `mp.if.6`, protección frente a inundaciones

<details><summary>Respuesta</summary>

**Correcta: C) `mp.if.6`, protección frente a inundaciones** Es la única de la familia con casilla «no aplica»: se exige en niveles MEDIO y ALTO de disponibilidad. `mp.if.4` sí aplica en BAJO (y añade el refuerzo R1 desde MEDIO), y `mp.if.5` aplica en los tres niveles.

*Referencia: §2.1.1 [ENS]*
</details>

---

### Pregunta 15

**Según el ENS, ¿qué es una «zona controlada»?**

A) Cualquier dependencia municipal en la que exista videovigilancia
B) Aquella que no es de acceso público y en la que el usuario, antes de acceder al equipo, se ha autenticado previamente de forma distinta al mecanismo de autenticación lógica
C) La zona de la red separada por un cortafuegos perimetral

<details><summary>Respuesta</summary>

**Correcta: B) Aquella que no es de acceso público y en la que el usuario, antes de acceder al equipo, se ha autenticado previamente de forma distinta al mecanismo de autenticación lógica** Es la definición del refuerzo `op.acc.6.r8`, que pone como ejemplo de zona **no** controlada **internet**. De ella depende que se admita o no el uso de contraseña sola.

*Referencia: §2.1.1 [ENS]*
</details>

---

### Pregunta 16

**En un sistema biométrico, la tasa de falsa aceptación (FAR) mide:**

A) La proporción de usuarios legítimos que el sistema rechaza indebidamente
B) La proporción de impostores que el sistema admite indebidamente
C) El tiempo medio que tarda el sistema en resolver una comparación

<details><summary>Respuesta</summary>

**Correcta: B) La proporción de impostores que el sistema admite indebidamente** Es el error **grave para la seguridad**. La proporción de legítimos rechazados es la **FRR**, un error molesto pero no peligroso. El punto en que se igualan es la **EER**, y cuanto menor sea, mejor es el sistema.

*Referencia: §2.1.1 [SP800-63]*
</details>

---

### Pregunta 17

**En la cadena de protección eléctrica de un centro de proceso de datos, ¿qué papel cumple el SAI frente al grupo electrógeno?**

A) El SAI da suministro inmediato y sin corte durante minutos, cubriendo el arranque del generador, que a su vez cubre la indisponibilidad prolongada
B) El SAI sustituye al grupo electrógeno cuando la autonomía requerida supera las ocho horas
C) El grupo electrógeno entra en funcionamiento instantáneamente y el SAI solo filtra armónicos

<details><summary>Respuesta</summary>

**Correcta: A) El SAI da suministro inmediato y sin corte durante minutos, cubriendo el arranque del generador, que a su vez cubre la indisponibilidad prolongada** Un generador tarda decenas de segundos en tomar carga; sin SAI habría corte. El SAI además filtra la calidad de la onda. No se sustituyen: se complementan.

*Referencia: §2.2.1 [TIA942] [ENS]*
</details>

---

### Pregunta 18

**El refuerzo R1 de la medida `mp.if.4` (energía eléctrica) exige que, ante un fallo del suministro principal, el abastecimiento esté garantizado:**

A) Durante un mínimo de veinticuatro horas ininterrumpidas
B) Mediante dos acometidas procedentes de subestaciones distintas
C) Durante el tiempo suficiente para una terminación ordenada de los procesos y la salvaguarda de la información

<details><summary>Respuesta</summary>

**Correcta: C) Durante el tiempo suficiente para una terminación ordenada de los procesos y la salvaguarda de la información** Es el texto literal de `mp.if.4.r1.1`. No fija horas: fija un **objetivo funcional**. Seguir dando servicio de forma prolongada corresponde ya a la continuidad (`op.cont.4`, medios alternativos).

*Referencia: §2.2.1 [ENS]*
</details>

---

### Pregunta 19

**¿Cuál es la diferencia esencial entre un centro de datos de nivel Tier III y uno de nivel Tier IV?**

A) Tier III es mantenible concurrentemente y Tier IV es además tolerante a fallos, de modo que un fallo imprevisto no interrumpe el servicio
B) Tier III garantiza una disponibilidad del 99,671 % y Tier IV del 99,741 %
C) Tier III exige extinción por gas inerte y Tier IV por agentes halocarbonados

<details><summary>Respuesta</summary>

**Correcta: A) Tier III es mantenible concurrentemente y Tier IV es además tolerante a fallos, de modo que un fallo imprevisto no interrumpe el servicio** La diferencia es conceptual, no numérica: en Tier III puede hacerse mantenimiento sin parar, pero un fallo imprevisto puede afectar; en Tier IV, no. Las cifras de disponibilidad son una consecuencia.

*Referencia: §2.2.1 [TIA942]*
</details>

---

### Pregunta 20

**Sobre los agentes de extinción de incendios en salas técnicas, señale la afirmación correcta.**

A) Los halones siguen siendo el agente de referencia por su eficacia y su bajo residuo
B) Los gases inertes extinguen por reducción del nivel de oxígeno y los agentes halocarbonados por absorción de calor; los halones están prohibidos
C) El agua nebulizada es el agente recomendado sobre equipos electrónicos energizados

<details><summary>Respuesta</summary>

**Correcta: B) Los gases inertes extinguen por reducción del nivel de oxígeno y los agentes halocarbonados por absorción de calor; los halones están prohibidos** Los halones se prohibieron por su efecto sobre la capa de ozono. Sobre equipos electrónicos energizados **nunca se emplea agua**: se usan agentes limpios que no dejan residuo ni conducen la electricidad.

*Referencia: §2.2.1 [NFPA75]*
</details>

---

### Pregunta 21

**Ordene correctamente las etapas de un acceso a un sistema.**

A) Autorización, identificación, autenticación y trazabilidad
B) Autenticación, identificación, autorización y trazabilidad
C) Identificación, autenticación, autorización y trazabilidad

<details><summary>Respuesta</summary>

**Correcta: C) Identificación, autenticación, autorización y trazabilidad** Primero se dice quién se es, después se demuestra, después el sistema decide qué se puede hacer y, durante todo el proceso, se registra. Nótese que la **identificación es previa** y no forma parte del modelo AAA (autenticación, autorización y contabilidad).

*Referencia: §3.1 [ENS] [RFC2865]*
</details>

---

### Pregunta 22

**¿Por qué el uso de cuentas genéricas compartidas es incompatible con el ENS?**

A) Porque el art. 24.3 exige que cada usuario esté identificado de forma única, de modo que se sepa en todo momento quién ha realizado cada actividad
B) Porque las cuentas compartidas no admiten contraseñas de complejidad suficiente
C) Porque el ENS prohíbe expresamente que más de un usuario acceda simultáneamente a un mismo sistema

<details><summary>Respuesta</summary>

**Correcta: A) Porque el art. 24.3 exige que cada usuario esté identificado de forma única, de modo que se sepa en todo momento quién ha realizado cada actividad** Una cuenta compartida destruye la **trazabilidad**: ninguna actuación queda imputable a una persona concreta, que es justamente lo que la dimensión T pretende garantizar.

*Referencia: §3.1 [ENS]*
</details>

---

### Pregunta 23

**¿Cuál de las siguientes combinaciones constituye autenticación multifactor?**

A) Contraseña de acceso al equipo y PIN de la aplicación de tramitación
B) Certificado en tarjeta criptográfica y PIN que desbloquea la tarjeta
C) Pregunta de seguridad y patrón de desbloqueo

<details><summary>Respuesta</summary>

**Correcta: B) Certificado en tarjeta criptográfica y PIN que desbloquea la tarjeta** Combina «algo que se tiene» (la tarjeta) con «algo que se sabe» (el PIN), que son **categorías distintas**. Las otras dos opciones combinan dos elementos del mismo factor «algo que se sabe» y, por tanto, **no son multifactor**.

*Referencia: §3.1.1 [ENS] [SP800-63]*
</details>

---

### Pregunta 24

**El refuerzo R8 de `op.acc.6` exige doble factor de autenticación:**

A) Únicamente en sistemas de categoría ALTA
B) Solo cuando el sistema trate datos de categorías especiales
C) Para el acceso desde o a través de zonas no controladas, y en todos los niveles

<details><summary>Respuesta</summary>

**Correcta: C) Para el acceso desde o a través de zonas no controladas, y en todos los niveles** R8 y R9 (acceso remoto) se exigen ya desde el nivel BAJO. Lo que entra en MEDIO es R5 (registro de accesos con éxito y fallidos), y en ALTO, R6 (reautenticación) y R7 (suspensión por no utilización).

*Referencia: §3.1.1 [ENS]*
</details>

---

### Pregunta 25

**En un modelo de control de acceso discrecional (DAC):**

A) Es el propietario del recurso quien decide quién accede y con qué permisos, pudiendo delegar esa facultad
B) Los permisos vienen determinados por etiquetas de clasificación fijadas por una autoridad central
C) Los permisos se asignan a roles y los roles a las personas

<details><summary>Respuesta</summary>

**Correcta: A) Es el propietario del recurso quien decide quién accede y con qué permisos, pudiendo delegar esa facultad** Es el modelo de los permisos de los sistemas de ficheros. Las etiquetas centrales corresponden a **MAC** y la asignación por roles, a **RBAC**.

*Referencia: §3.1.2 [SP800-162]*
</details>

---

### Pregunta 26

**El modelo de Bell-LaPadula protege fundamentalmente:**

A) La disponibilidad, mediante redundancia de rutas de acceso a la información
B) La integridad, mediante las reglas de no leer abajo y no escribir arriba
C) La confidencialidad, mediante las reglas de no leer arriba y no escribir abajo

<details><summary>Respuesta</summary>

**Correcta: C) La confidencialidad, mediante las reglas de no leer arriba y no escribir abajo** La opción B describe **Biba**, que es su modelo dual y protege la **integridad**. Regla mnemotécnica: Bell-LaPadula = confidencialidad, «no leer arriba»; Biba = integridad, «no escribir arriba».

*Referencia: §3.1.2 [BLP]*
</details>

---

### Pregunta 27

**¿Qué caracteriza al control de acceso basado en atributos (ABAC)?**

A) Que los permisos se conceden en función del puesto que ocupa la persona en el organigrama
B) Que la decisión se toma evaluando reglas sobre atributos del sujeto, del objeto, de la acción y del entorno, incluido el contexto
C) Que solo la autoridad central puede modificar las etiquetas de seguridad de los objetos

<details><summary>Respuesta</summary>

**Correcta: B) Que la decisión se toma evaluando reglas sobre atributos del sujeto, del objeto, de la acción y del entorno, incluido el contexto** Permite políticas como «un tramitador puede modificar expedientes de su distrito, en horario laboral y desde equipo corporativo». Su inconveniente es la dificultad para responder a «¿quién puede acceder a esto?».

*Referencia: §3.1.2 [SP800-162]*
</details>

---

### Pregunta 28

**El art. 20 del ENS, sobre mínimo privilegio, establece entre otros aspectos que:**

A) El uso ordinario del sistema ha de ser sencillo y seguro, de forma que una utilización insegura requiera un acto consciente por parte del usuario
B) Todos los usuarios deben disponer de privilegios de administración local sobre su propio equipo
C) Los privilegios se revisarán exclusivamente cuando se produzca un incidente de seguridad

<details><summary>Respuesta</summary>

**Correcta: A) El uso ordinario del sistema ha de ser sencillo y seguro, de forma que una utilización insegura requiera un acto consciente por parte del usuario** Es texto casi literal del art. 20.c. El mismo artículo, en su apartado d, obliga a aplicar **guías de configuración de seguridad** (bastionado) adaptadas a la categorización del sistema.

*Referencia: §3.2.1 [ENS]*
</details>

---

### Pregunta 29

**La acumulación indebida de privilegios cuando una persona cambia de puesto y conserva los permisos anteriores se corrige mediante:**

A) El cifrado de los soportes que la persona utilizaba en su puesto anterior
B) La ampliación del periodo de conservación de los registros de actividad
C) El proceso de gestión de derechos de acceso de `op.acc.4`, con revisión periódica y recertificación por los responsables funcionales

<details><summary>Respuesta</summary>

**Correcta: C) El proceso de gestión de derechos de acceso de `op.acc.4`, con revisión periódica y recertificación por los responsables funcionales** El ciclo alta-modificación-revisión-baja es donde más falla el control de acceso en la práctica, y el momento crítico es la **modificación**, no el alta.

*Referencia: §3.2.1 [ENS]*
</details>

---

### Pregunta 30

**Respecto al registro de actividad del art. 24 del ENS, señale la afirmación correcta.**

A) Permite registrar y analizar sin límite cualquier comunicación del personal, por tratarse de medios propiedad de la Administración
B) Debe realizarse con plenas garantías del derecho al honor y a la intimidad, reteniendo la información estrictamente necesaria y respetando la limitación de la finalidad, la minimización y la limitación del plazo de conservación
C) Solo es exigible en sistemas de categoría ALTA

<details><summary>Respuesta</summary>

**Correcta: B) Debe realizarse con plenas garantías del derecho al honor y a la intimidad, reteniendo la información estrictamente necesaria y respetando la limitación de la finalidad, la minimización y la limitación del plazo de conservación** El análisis de las comunicaciones solo cabe «en la medida estrictamente necesaria y proporcionada» y **únicamente para fines de seguridad de la información**. Es el punto de contacto más directo entre el ENS, el RGPD y el art. 87 de la LOPDGDD.

*Referencia: §3.2.1 [ENS] [RGPD] [LOPDGDD]*
</details>

---
### Pregunta 31

**¿Cuál es la diferencia esencial entre un virus y un gusano?**

A) El virus necesita un programa o fichero anfitrión y, normalmente, una acción del usuario; el gusano es autónomo y se propaga por sí mismo a través de la red
B) El virus se propaga por la red sin intervención del usuario y el gusano necesita ejecutarse manualmente
C) El virus cifra la información y el gusano solo la copia

<details><summary>Respuesta</summary>

**Correcta: A) El virus necesita un programa o fichero anfitrión y, normalmente, una acción del usuario; el gusano es autónomo y se propaga por sí mismo a través de la red** Un efecto colateral típico del gusano es la **saturación de la red**. El cifrado con extorsión es la carga útil del **secuestro de datos**, que puede llegar por cualquiera de las dos vías.

*Referencia: §4.1.1 [ENS] [SIEM]*
</details>

---

### Pregunta 32

**Un programa que se presenta como una utilidad legítima, oculta funcionalidad dañina y no se replica es:**

A) Un gusano
B) Un troyano
C) Una bomba lógica

<details><summary>Respuesta</summary>

**Correcta: B) Un troyano** Su rasgo diferencial es el **engaño**, y su carencia, la **replicación**. La bomba lógica es código latente que se activa al cumplirse una condición (una fecha, la desaparición de un empleado de la nómina).

*Referencia: §4.1.1 [ENS]*
</details>

---

### Pregunta 33

**Frente a un ataque de secuestro de datos (ransomware) con doble extorsión, la contramedida decisiva es:**

A) El antivirus basado en firmas correctamente actualizado
B) La segmentación de la red mediante VLAN
C) Disponer de copias de seguridad aisladas o inmutables y probadas, además de tratar el incidente como violación de datos personales por la exfiltración

<details><summary>Respuesta</summary>

**Correcta: C) Disponer de copias de seguridad aisladas o inmutables y probadas, además de tratar el incidente como violación de datos personales por la exfiltración** El antivirus por firmas no detiene variantes nuevas y la segmentación limita la propagación pero no recupera los datos. La doble extorsión —cifrar y además exfiltrar— convierte el incidente en notificable a la AEPD.

*Referencia: §4.1.1 [ENS] [RGPD]*
</details>

---

### Pregunta 34

**El refuerzo R3 de la medida `op.exp.6`, exigible en categoría ALTA, consiste en:**

A) Desplegar herramientas EDR de detección y respuesta en el puesto
B) Implementar una lista blanca, de modo que solo puedan ejecutarse aplicaciones previamente autorizadas
C) Escanear todo el sistema de forma regular para detectar código dañino

<details><summary>Respuesta</summary>

**Correcta: B) Implementar una lista blanca, de modo que solo puedan ejecutarse aplicaciones previamente autorizadas** El EDR es el refuerzo **R4**, y el escaneo regular, el **R1**. La lista blanca invierte el modelo: en lugar de prohibir lo malo conocido, solo permite lo bueno autorizado.

*Referencia: §4.1.1 [ENS]*
</details>

---

### Pregunta 35

**Señale la afirmación correcta sobre ataques pasivos y activos.**

A) El ataque pasivo no altera la información, es difícil de detectar y se combate previniéndolo mediante cifrado; el activo altera el flujo y se combate detectándolo y respondiendo
B) El ataque pasivo altera la información en tránsito y el activo se limita a observarla
C) Ambos se combaten exclusivamente mediante control de acceso lógico

<details><summary>Respuesta</summary>

**Correcta: A) El ataque pasivo no altera la información, es difícil de detectar y se combate previniéndolo mediante cifrado; el activo altera el flujo y se combate detectándolo y respondiendo** La medida `mp.com.3.2` del ENS enumera como ataques activos la alteración de la información en tránsito, la inyección de información espuria y el secuestro de la sesión.

*Referencia: §4.1 [ENS] [STALLINGS]*
</details>

---

### Pregunta 36

**En la clasificación de amenazas de MAGERIT, un corte del suministro eléctrico y una avería de un equipo pertenecen al grupo:**

A) [A] Ataques intencionados
B) [E] Errores y fallos no intencionados
C) [I] De origen industrial

<details><summary>Respuesta</summary>

**Correcta: C) [I] De origen industrial** Los cuatro grupos son [N] desastres naturales, [I] de origen industrial, [E] errores y fallos no intencionados y [A] ataques intencionados. Los errores del grupo [E] son fallos **de personas** sin intención dañina, y constituyen el origen de la mayoría de los incidentes reales.

*Referencia: §4.1 [MAGERIT]*
</details>

---

### Pregunta 37

**En el OWASP Top 10:2025, el primer riesgo de la lista es:**

A) Injection (inyección)
B) Broken Access Control (pérdida de control de acceso)
C) Cryptographic Failures (fallos criptográficos)

<details><summary>Respuesta</summary>

**Correcta: B) Broken Access Control (pérdida de control de acceso)** Encabeza la lista también en la edición de 2021. Otro cambio relevante de 2025: **Software Supply Chain Failures** pasa a ser categoría propia en tercer lugar, y el **SSRF**, que en 2021 era la categoría A10 independiente, se integra en A01.

*Referencia: §4.1.2 [OWASP2025]*
</details>

---

### Pregunta 38

**La contramedida técnica de referencia frente a la inyección SQL es:**

A) La codificación de la salida en función del contexto de presentación
B) El uso de un token anti-CSRF distinto en cada sesión
C) El uso de consultas parametrizadas o sentencias preparadas, en lugar de concatenar cadenas

<details><summary>Respuesta</summary>

**Correcta: C) El uso de consultas parametrizadas o sentencias preparadas, en lugar de concatenar cadenas** La codificación de salida es la contramedida del **XSS** y el token anti-CSRF, la de la **falsificación de petición en sitios cruzados**. A la parametrización se añaden la validación de entrada y el mínimo privilegio de la cuenta de base de datos.

*Referencia: §4.1.2 [OWASP2025] [CWE]*
</details>

---

### Pregunta 39

**Las contramedidas más eficaces frente a la ingeniería social son:**

A) Organizativas y humanas: concienciación y formación, verificación por canal alternativo y una cultura en la que notificar una sospecha no tenga coste
B) Exclusivamente técnicas: cortafuegos de nueva generación y sistemas de prevención de intrusiones
C) Jurídicas: la tipificación penal de la suplantación de identidad

<details><summary>Respuesta</summary>

**Correcta: A) Organizativas y humanas: concienciación y formación, verificación por canal alternativo y una cultura en la que notificar una sospecha no tenga coste** La ingeniería social **rodea** el sistema en lugar de atacarlo. El ENS exige concienciación (`mp.per.3`) y formación (`mp.per.4`) en las tres categorías. Técnicamente se mitiga con MFA resistente a la suplantación de sitio y filtrado de correo.

*Referencia: §4.1.2 [ENS]*
</details>

---

### Pregunta 40

**¿Qué se entiende por vulnerabilidad de día cero?**

A) Aquella para la que no existe parche disponible en el momento en que se conoce o se explota
B) Aquella que fue descubierta hace menos de veinticuatro horas
C) Aquella cuya puntuación CVSS es igual o superior a 9,0

<details><summary>Respuesta</summary>

**Correcta: A) Aquella para la que no existe parche disponible en el momento en que se conoce o se explota** El término no significa «recién descubierta», sino «**sin corrección disponible**». La ventana de exposición termina al **aplicar** el parche, no al publicarlo: un parche publicado y no instalado no reduce la exposición en absoluto.

*Referencia: §4.2.1 [SP800-40]*
</details>

---

### Pregunta 41

**Relacione correctamente CVE, CVSS y CWE.**

A) CVE es la puntuación de gravedad, CVSS el identificador de la vulnerabilidad y CWE el catálogo de exploits
B) Los tres son sinónimos mantenidos por organizaciones distintas
C) CVE identifica de forma única una vulnerabilidad concreta, CVSS puntúa su gravedad de 0,0 a 10,0 y CWE clasifica el tipo de debilidad

<details><summary>Respuesta</summary>

**Correcta: C) CVE identifica de forma única una vulnerabilidad concreta, CVSS puntúa su gravedad de 0,0 a 10,0 y CWE clasifica el tipo de debilidad** El CVE es la **instancia** (`CVE-2026-12345`); el CWE, la **categoría** (`CWE-89`, inyección SQL). Umbrales del CVSS v3.1: 0,1-3,9 baja, 4,0-6,9 media, 7,0-8,9 alta y 9,0-10,0 crítica.

*Referencia: §4.2.1 [CVE] [CVSS] [CWE]*
</details>

---

### Pregunta 42

**Los refuerzos R1 y R2 de la medida `op.exp.4` (mantenimiento y actualizaciones de seguridad) exigen, respectivamente:**

A) Escaneo periódico del sistema y revisión de las funciones críticas al arrancar
B) Pruebas en un entorno de preproducción consistente en configuración con producción, y prever un mecanismo para revertir los cambios ante efectos adversos
C) Comprobación de la integridad del firmware y monitorización continua de amenazas

<details><summary>Respuesta</summary>

**Correcta: B) Pruebas en un entorno de preproducción consistente en configuración con producción, y prever un mecanismo para revertir los cambios ante efectos adversos** R1 se exige desde categoría MEDIA y R2 desde ALTA. La opción A describe refuerzos de `op.exp.6` y la opción C, los refuerzos R3 y R4 de `op.exp.4`, que no se activan por categoría.

*Referencia: §4.2.1 [ENS]*
</details>

---

### Pregunta 43

**El régimen de auditoría de seguridad del art. 31 del ENS establece que:**

A) Los sistemas de categoría MEDIA y ALTA se auditan al menos cada dos años, mientras que los de categoría BÁSICA solo requieren una autoevaluación
B) Todos los sistemas, con independencia de su categoría, se auditan anualmente
C) La auditoría solo procede tras un incidente de seguridad de impacto grave

<details><summary>Respuesta</summary>

**Correcta: A) Los sistemas de categoría MEDIA y ALTA se auditan al menos cada dos años, mientras que los de categoría BÁSICA solo requieren una autoevaluación** También procede auditoría **extraordinaria** cuando se produzcan modificaciones sustanciales. La autoevaluación de categoría BÁSICA debe documentarse de forma equivalente.

*Referencia: §4.2.1 [ENS]*
</details>

---

### Pregunta 44

**¿Cuál es la diferencia entre un análisis de vulnerabilidades y una prueba de penetración?**

A) El análisis lo realiza personal externo y la prueba de penetración, personal interno
B) El análisis se aplica a aplicaciones web y la prueba de penetración, exclusivamente a infraestructura de red
C) El análisis es automatizado, amplio y no explota los hallazgos; la prueba de penetración es manual, dirigida y sí los explota para demostrar el impacto real

<details><summary>Respuesta</summary>

**Correcta: C) El análisis es automatizado, amplio y no explota los hallazgos; la prueba de penetración es manual, dirigida y sí los explota para demostrar el impacto real** Ambas son distintas de la **auditoría del ENS**, que verifica la **conformidad** con el anexo II. Toda prueba ofensiva exige autorización previa por escrito con alcance y reglas definidas.

*Referencia: §4.2.1 [ENS] [SP800-53]*
</details>

---

### Pregunta 45

**Según el principio de Kerckhoffs:**

A) Todo algoritmo criptográfico debe mantenerse en secreto para dificultar el criptoanálisis
B) La seguridad de un sistema criptográfico debe residir únicamente en la clave, aunque todo lo demás sea de dominio público
C) La longitud de la clave debe duplicarse cada cinco años

<details><summary>Respuesta</summary>

**Correcta: B) La seguridad de un sistema criptográfico debe residir únicamente en la clave, aunque todo lo demás sea de dominio público** De él deriva el rechazo a la «seguridad por oscuridad»: un algoritmo secreto no es más seguro, solo está menos analizado. Por eso el ENS exige emplear **algoritmos autorizados por el CCN** y no soluciones propietarias.

*Referencia: §5.1 [KERCKHOFFS]*
</details>

---

### Pregunta 46

**En una red de 100 participantes que deben comunicarse por parejas, ¿cuántas claves se necesitan con criptografía simétrica y cuántas con asimétrica?**

A) 4.950 claves simétricas y 200 claves asimétricas
B) 100 claves simétricas y 100 claves asimétricas
C) 200 claves simétricas y 4.950 claves asimétricas

<details><summary>Respuesta</summary>

**Correcta: A) 4.950 claves simétricas y 200 claves asimétricas** Simétrica: n(n−1)/2 = 100 × 99 / 2 = **4.950**. Asimétrica: 2n = **200** (un par por participante). Es la razón matemática de que la criptografía de clave pública resuelva el problema de escalabilidad en la distribución de claves.

*Referencia: §5.1.1 [DH]*
</details>

---

### Pregunta 47

**Para enviar un documento de forma confidencial mediante criptografía asimétrica, el emisor debe cifrarlo con:**

A) Su propia clave privada, de modo que solo él pueda haberlo generado
B) Su propia clave pública, que después difunde junto al documento
C) La clave pública del destinatario, de modo que solo este pueda descifrarlo con su clave privada

<details><summary>Respuesta</summary>

**Correcta: C) La clave pública del destinatario, de modo que solo este pueda descifrarlo con su clave privada** Cifrar con la **propia clave privada** es lo que se hace al **firmar**, y produce autenticidad, integridad y no repudio, no confidencialidad. Confundir ambas operaciones es el error más frecuente del bloque criptográfico.

*Referencia: §5.1.1 [RFC8017]*
</details>

---

### Pregunta 48

**Señale la afirmación correcta sobre las funciones hash.**

A) Cifran la información con una clave derivada del propio mensaje, por lo que son reversibles con esa clave
B) No tienen clave, no son reversibles y garantizan integridad, no confidencialidad; producen una salida de longitud fija con efecto avalancha
C) Su salida tiene una longitud proporcional al tamaño del mensaje de entrada

<details><summary>Respuesta</summary>

**Correcta: B) No tienen clave, no son reversibles y garantizan integridad, no confidencialidad; producen una salida de longitud fija con efecto avalancha** MD5 y SHA-1 están **rotos** para firma por existir colisiones prácticas. Para almacenar contraseñas se usa hash **con sal** y función de derivación lenta (bcrypt, scrypt, Argon2, PBKDF2).

*Referencia: §5.1.1 [FIPS180]*
</details>

---

### Pregunta 49

**El esquema de «sobre digital» o cifrado híbrido consiste en:**

A) Cifrar dos veces el mismo documento con dos claves simétricas distintas
B) Cifrar los datos con una clave de sesión simétrica y proteger esa clave de sesión con la clave pública del receptor
C) Firmar el documento antes de cifrarlo, siempre con el mismo par de claves

<details><summary>Respuesta</summary>

**Correcta: B) Cifrar los datos con una clave de sesión simétrica y proteger esa clave de sesión con la clave pública del receptor** Es el mecanismo de TLS, S/MIME, PGP e IPsec, y resuelve a la vez la lentitud de la asimétrica y el problema de distribución de claves de la simétrica: la asimétrica **negocia la clave** y la simétrica **cifra el tráfico**.

*Referencia: §5.1.1 [RFC9846]*
</details>

---

### Pregunta 50

**La confidencialidad directa (forward secrecy) impide que:**

A) Quien obtenga en el futuro la clave privada del servidor pueda descifrar el tráfico capturado y almacenado en el pasado
B) Un atacante situado en medio de la comunicación pueda leer el tráfico en tiempo real
C) El servidor pueda reutilizar el mismo certificado en varios dominios

<details><summary>Respuesta</summary>

**Correcta: A) Quien obtenga en el futuro la clave privada del servidor pueda descifrar el tráfico capturado y almacenado en el pasado** Se consigue negociando la clave de sesión con **Diffie-Hellman efímero** (DHE o ECDHE), con parámetros desechables en cada sesión. **TLS 1.3 la hace obligatoria** y por eso eliminó el intercambio de claves basado en RSA.

*Referencia: §5.1.1 y §5.2.1 [RFC9846]*
</details>

---

### Pregunta 51

**Sobre AH y ESP en IPsec, señale la afirmación correcta.**

A) AH es el protocolo IP número 50 y cifra la carga útil; ESP es el número 51 y solo autentica
B) Ambos cifran la carga útil, y se diferencian únicamente en el modo de encapsulado
C) AH es el protocolo IP número 51 y aporta integridad y autenticidad sin cifrar; ESP es el número 50 y añade confidencialidad

<details><summary>Respuesta</summary>

**Correcta: C) AH es el protocolo IP número 51 y aporta integridad y autenticidad sin cifrar; ESP es el número 50 y añade confidencialidad** AH es además incompatible con NAT en su forma pura, porque autentica campos de la cabecera IP que el NAT modifica. La combinación habitual en una VPN es **ESP en modo túnel**.

*Referencia: §5.2.1 [RFC4302] [RFC4303]*
</details>

---

### Pregunta 52

**La diferencia entre el modo transporte y el modo túnel de IPsec es que:**

A) El modo transporte protege solo la carga útil y conserva la cabecera IP original, mientras que el modo túnel encapsula el paquete IP completo dentro de otro con nueva cabecera
B) El modo transporte se emplea entre pasarelas y el modo túnel, entre equipos finales
C) El modo transporte utiliza AH obligatoriamente y el modo túnel, ESP

<details><summary>Respuesta</summary>

**Correcta: A) El modo transporte protege solo la carga útil y conserva la cabecera IP original, mientras que el modo túnel encapsula el paquete IP completo dentro de otro con nueva cabecera** El modo transporte es de **extremo a extremo**; el túnel, entre **pasarelas** (VPN sitio a sitio), y oculta el direccionamiento interno. La negociación se realiza con IKEv2 sobre UDP/500.

*Referencia: §5.2.1 [RFC4301] [RFC7296]*
</details>

---

### Pregunta 53

**¿Cuál es el estado actual de las versiones de SSL y TLS?**

A) SSL 3.0 sigue admitido para compatibilidad con clientes antiguos, y TLS 1.0 es la versión recomendada
B) SSL 2.0 y 3.0 están prohibidos, TLS 1.0 y 1.1 están declarados obsoletos y las versiones vigentes son TLS 1.2 y TLS 1.3
C) Solo TLS 1.3 está admitido; TLS 1.2 quedó prohibido al publicarse el RFC 9846

<details><summary>Respuesta</summary>

**Correcta: B) SSL 2.0 y 3.0 están prohibidos, TLS 1.0 y 1.1 están declarados obsoletos y las versiones vigentes son TLS 1.2 y TLS 1.3** SSL 3.0 se prohibió por el RFC 7568 y TLS 1.0/1.1 se declararon obsoletos por el RFC 8996. El **RFC 9846** (julio de 2026) reedita TLS 1.3 y obsoleta las especificaciones anteriores, incluida la del RFC 5246, pero **no prohíbe TLS 1.2**. Decir «certificado SSL» es un uso comercial heredado: lo que se despliega es TLS.

*Referencia: §5.2.1 [RFC7568] [RFC8996] [RFC9846]*
</details>

---

### Pregunta 54

**¿Qué comprobaciones debe realizar un cliente al validar el certificado de un servidor TLS?**

A) Únicamente que la fecha de caducidad no haya vencido
B) Que la autoridad de certificación esté domiciliada en la Unión Europea y que la clave tenga al menos 2.048 bits
C) Cadena de confianza hasta una AC raíz reconocida, periodo de validez vigente, estado de revocación y correspondencia del nombre con el solicitado

<details><summary>Respuesta</summary>

**Correcta: C) Cadena de confianza hasta una AC raíz reconocida, periodo de validez vigente, estado de revocación y correspondencia del nombre con el solicitado** Fallar **una sola** de las cuatro debe abortar la conexión. Aceptar excepciones de seguridad de forma rutinaria anula el modelo, y es justamente lo que impide la cabecera **HSTS**.

*Referencia: §5.2.1 [RFC5280] [RFC6797]*
</details>

---

### Pregunta 55

**Señale la afirmación correcta sobre HTTPS.**

A) Cifra el contenido de las peticiones y respuestas, incluidas URL, cabeceras y cuerpo, pero no oculta la dirección IP de destino ni el volumen de tráfico, y no garantiza que el sitio sea legítimo o inofensivo
B) Garantiza que el sitio visitado no contiene contenido malicioso, porque el certificado acredita la honestidad del titular
C) Cifra el mensaje de extremo a extremo, de modo que ningún servidor intermedio puede leerlo

<details><summary>Respuesta</summary>

**Correcta: A) Cifra el contenido de las peticiones y respuestas, incluidas URL, cabeceras y cuerpo, pero no oculta la dirección IP de destino ni el volumen de tráfico, y no garantiza que el sitio sea legítimo o inofensivo** HTTPS significa «canal cifrado con un extremo identificado», no «sitio seguro»: hoy la suplantación de sitio usa masivamente certificados válidos. El cifrado de extremo a extremo del **mensaje** corresponde a S/MIME o PGP.

*Referencia: §5.2.2 [RFC9110]*
</details>

---

### Pregunta 56

**El modelo de confianza de SSH al conectarse por primera vez a un servidor se denomina:**

A) Validación extendida mediante autoridad de certificación reconocida
B) Confianza en el primer uso: se muestra la huella digital de la clave del servidor, se confirma y se almacena para futuras conexiones
C) Autenticación federada mediante proveedor de identidad externo

<details><summary>Respuesta</summary>

**Correcta: B) Confianza en el primer uso: se muestra la huella digital de la clave del servidor, se confirma y se almacena para futuras conexiones** Es la diferencia esencial con TLS: **SSH no usa una PKI con autoridades de certificación**, sino confianza directa en la clave del extremo. Si la huella cambia después, SSH avisa de posible interceptación y bloquea.

*Referencia: §5.2.2 [RFC4251]*
</details>

---

### Pregunta 57

**La medida `mp.com.2` del ENS (protección de la confidencialidad de las comunicaciones) exige, como requisito base:**

A) Emplear exclusivamente productos certificados por el Centro Criptológico Nacional en todos los niveles
B) Cifrar toda la información transmitida dentro del propio dominio de seguridad
C) Emplear redes privadas virtuales cifradas cuando la comunicación discurra por redes fuera del propio dominio de seguridad

<details><summary>Respuesta</summary>

**Correcta: C) Emplear redes privadas virtuales cifradas cuando la comunicación discurra por redes fuera del propio dominio de seguridad** Los productos certificados corresponden al refuerzo **R3**, exigible en nivel ALTO de confidencialidad, y el uso de **algoritmos autorizados por el CCN** al refuerzo R1, exigible desde nivel MEDIO.

*Referencia: §5.2.2 [ENS]*
</details>

---

### Pregunta 58

**En una infraestructura de clave pública, la autoridad de registro (AR):**

A) Identifica y verifica al solicitante antes de la emisión, pero no emite ni firma el certificado
B) Emite y firma los certificados con su clave privada
C) Responde en línea sobre el estado de revocación de los certificados

<details><summary>Respuesta</summary>

**Correcta: A) Identifica y verifica al solicitante antes de la emisión, pero no emite ni firma el certificado** Emitir y firmar corresponde a la **autoridad de certificación (AC)**; responder sobre el estado, a la **autoridad de validación (AV)**. Las oficinas de registro que comprueban el DNI del solicitante son AR, no AC.

*Referencia: §6.1.1 [RFC5280]*
</details>

---

### Pregunta 59

**¿Qué ventaja aporta el grapado OCSP (OCSP stapling) frente a la consulta OCSP tradicional?**

A) Permite validar el certificado sin necesidad de comprobar la cadena de confianza
B) Es el propio servidor quien obtiene y adjunta su respuesta OCSP firmada, lo que elimina la dependencia y la latencia del respondedor y protege la privacidad del usuario
C) Sustituye la firma de la autoridad de certificación por la del servidor, simplificando la validación

<details><summary>Respuesta</summary>

**Correcta: B) Es el propio servidor quien obtiene y adjunta su respuesta OCSP firmada, lo que elimina la dependencia y la latencia del respondedor y protege la privacidad del usuario** Sin grapado, el navegador consulta a un tercero y le revela qué sitios visita. La respuesta sigue estando **firmada por la autoridad**, no por el servidor.

*Referencia: §6.1.1 [RFC6960]*
</details>

---

### Pregunta 60

**¿Qué requisitos debe cumplir una firma electrónica para ser cualificada conforme al Reglamento eIDAS?**

A) Basta con que se base en un certificado electrónico cualificado emitido por un prestador cualificado
B) Basta con que cumpla los cuatro requisitos de la firma avanzada del art. 26
C) Debe ser una firma avanzada, creada mediante un dispositivo cualificado de creación de firma y basada en un certificado cualificado de firma electrónica

<details><summary>Respuesta</summary>

**Correcta: C) Debe ser una firma avanzada, creada mediante un dispositivo cualificado de creación de firma y basada en un certificado cualificado de firma electrónica** Un certificado cualificado **sin** dispositivo cualificado produce firma **avanzada**, no cualificada: es el error más repetido. Solo la cualificada tiene efecto jurídico equivalente al de la firma manuscrita [art. 25.2].

*Referencia: §6.2.1 [EIDAS]*
</details>
