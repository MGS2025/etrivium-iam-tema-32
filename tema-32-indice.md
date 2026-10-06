# Tema 32 — Índice

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.
>
> **Bloque**: Parte II — Técnico (Temas 11-40)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

---

## Estructura del tema

1. **Conceptos de seguridad de los sistemas de información**
   1.1. Principios generales y dimensiones de la seguridad
   1.1.1. Concepto de seguridad de la información
   1.1.2. Confidencialidad, integridad, disponibilidad, autenticidad y no repudio
   1.1.3. Análisis y gestión de riesgos
   1.2. Marco legal y normativo en el ámbito público
   1.2.1. El Esquema Nacional de Seguridad
   1.2.2. Protección de datos personales y garantía de derechos digitales

2. **Seguridad física**
   2.1. Protección perimetral y control de acceso físico
   2.1.1. Medidas de seguridad en entradas, edificios y áreas restringidas
   2.2. Protección ambiental y del equipamiento
   2.2.1. Suministro eléctrico, climatización y prevención de incendios
   2.2.2. Ubicación y acondicionamiento del centro de proceso de datos

3. **Seguridad lógica**
   3.1. Identificación, autenticación y autorización
   3.1.1. Mecanismos y factores de autenticación
   3.1.2. Modelos de control de acceso lógico
   3.2. Gestión de usuarios y accesos
   3.2.1. Mínimo privilegio, separación de funciones y registro de actividad

4. **Amenazas y vulnerabilidades**
   4.1. Análisis e identificación de amenazas
   4.1.1. Código malicioso y vectores de infección
   4.1.2. Ataques a redes, aplicaciones e ingeniería social
   4.2. Tratamiento de vulnerabilidades
   4.2.1. Detección, evaluación y gestión de parches

5. **Técnicas criptográficas y protocolos seguros**
   5.1. Fundamentos criptográficos
   5.1.1. Criptografía simétrica, asimétrica y funciones hash
   5.2. Protocolos de comunicación segura
   5.2.1. Protocolos de red y transporte: IPsec, TLS y SSL
   5.2.2. Protocolos de aplicación seguros: SSH y HTTPS

6. **Mecanismos de firma digital**
   6.1. Infraestructura de clave pública y certificados digitales
   6.1.1. Componentes de la PKI, certificados y listas de revocación
   6.2. Firma electrónica y servicios de confianza
   6.2.1. Modalidades de firma electrónica, sellado de tiempo y marco regulatorio

---

## Conceptos clave para memorizar

| Concepto | Dato clave |
|---|---|
| Dimensiones de la seguridad (ENS) | **Cinco**: **C**onfidencialidad, **I**ntegridad, **T**razabilidad, **A**utenticidad y **D**isponibilidad. Anexo I, apartado 2 del RD 311/2022. El «no repudio» **no** es una dimensión del ENS: es un efecto jurídico que se apoya en autenticidad + integridad + trazabilidad |
| Niveles y categorías (ENS) | **Niveles** por dimensión: BAJO, MEDIO, ALTO. **Categorías** del sistema: BÁSICA, MEDIA, ALTA. Manda **la dimensión más alta**; si una dimensión no se ve afectada, no se le asigna nivel |
| Riesgo | Función del **impacto** de un incidente y de la **probabilidad** de que ocurra. La **amenaza** es externa al activo; la **vulnerabilidad**, propia del activo. Sin vulnerabilidad que explotar, la amenaza no se materializa |
| Tratamiento del riesgo | Cuatro opciones: **evitar / eliminar**, **mitigar / reducir**, **transferir / compartir** (seguro, contrato) y **aceptar / asumir**. El riesgo que queda tras las salvaguardas es el **riesgo residual**, y debe ser **aceptado formalmente** |
| Salvaguardas por función | **Preventivas** (evitan), **disuasorias** (desaniman), **detectivas** (descubren), **correctivas** (reparan) y **recuperativas** (restauran). El ENS las ordena en **prevención, detección, respuesta y conservación** (art. 8) |
| Seguridad física en el ENS | Familia **mp.if** (protección de las instalaciones e infraestructuras): **mp.if.1** áreas separadas · **mp.if.2** identificación de las personas · **mp.if.3** acondicionamiento de los locales · **mp.if.4** energía eléctrica · **mp.if.5** incendios · **mp.if.6** inundaciones · **mp.if.7** registro de entrada y salida de equipamiento |
| Factores de autenticación | **Tres**: algo que **se sabe** (contraseña, PIN), algo que **se tiene** (tarjeta, token, OTP) y algo que **se es** (biometría). Multifactor = **dos o más de categorías distintas**. Contraseña + PIN **no** es multifactor |
| Modelos de control de acceso | **DAC** (el propietario decide) · **MAC** (lo decide una política obligatoria por etiquetas, Bell-LaPadula) · **RBAC** (por rol) · **ABAC** (por atributos y contexto). El ENS impone **mínimo privilegio** (art. 20) y **segregación de funciones** (op.acc.3) |
| Bell-LaPadula vs Biba | **Bell-LaPadula** protege la **confidencialidad**: *no leer arriba, no escribir abajo*. **Biba** protege la **integridad**: *no leer abajo, no escribir arriba*. Son duales |
| Malware: virus, gusano, troyano | **Virus**: necesita un **anfitrión** y una acción del usuario. **Gusano**: se propaga **solo** por la red, sin anfitrión. **Troyano**: se **disfraza** de programa legítimo y no se replica |
| Vulnerabilidad de día cero | Vulnerabilidad **sin parche disponible** en el momento en que se explota. La **ventana de exposición** va del descubrimiento a la aplicación efectiva del parche, no a su publicación |
| CVE y CVSS | **CVE** = identificador único de la vulnerabilidad (`CVE-AAAA-NNNN`). **CVSS** = puntuación de gravedad de 0,0 a 10,0. Umbrales v3.1: **0,1-3,9 baja · 4,0-6,9 media · 7,0-8,9 alta · 9,0-10,0 crítica** |
| Simétrica vs asimétrica | **Simétrica**: una sola clave, rápida, problema de **distribución de claves**; *n* usuarios → **n(n−1)/2** claves. **Asimétrica**: par pública/privada, lenta, resuelve la distribución; *n* usuarios → **2n** claves |
| Qué garantiza cada operación | **Cifrar con la clave pública del destinatario** → confidencialidad. **Cifrar (firmar) con la clave privada del emisor** → autenticidad, integridad y no repudio. Nunca al revés |
| Función hash | **Unidireccional**, salida de **longitud fija**, **efecto avalancha**, resistente a colisiones. **No** cifra y **no** tiene clave: no es reversible. **SHA-1 y MD5 están proscritos**; se usan **SHA-256/SHA-384/SHA-512** o SHA-3 |
| Cifrado híbrido | Los protocolos reales **combinan** ambos: la criptografía **asimétrica** negocia una **clave de sesión**, y con ella la **simétrica** cifra los datos. Es el «sobre digital» de TLS, S/MIME e IPsec |
| IPsec | Nivel de **red** (capa 3). **AH** (protocolo 51): integridad y autenticidad, **no** confidencialidad. **ESP** (protocolo 50): además **cifra**. **Modo transporte** (extremo a extremo, conserva la cabecera IP original) vs **modo túnel** (encapsula el paquete entero: VPN sitio a sitio). Negociación con **IKEv2, UDP/500** |
| TLS | Nivel de **transporte**. **SSL está muerto** (2.0 y 3.0 prohibidos, RFC 7568); TLS 1.0/1.1 **obsoletos** (RFC 8996). Vigentes **TLS 1.2** y **TLS 1.3** (RFC 9846, que sustituye en 2026 al RFC 8446): 1.3 elimina RSA como intercambio de claves, exige **confidencialidad directa** (*forward secrecy*) y hace el saludo en **1-RTT** |
| HTTPS y HSTS | HTTPS = HTTP sobre TLS, puerto **443**. **HSTS** (RFC 6797, cabecera `Strict-Transport-Security`) obliga al navegador a usar siempre HTTPS y evita el ataque de degradación |
| SSH | Puerto **22**. Sustituye a Telnet, rlogin y FTP. Autenticación por contraseña o por **par de claves**; permite túneles y transferencia (SFTP, SCP) |
| PKI: componentes | **AC** (autoridad de certificación, emite y revoca) · **AR** (autoridad de registro, identifica al solicitante) · **AV** (autoridad de validación, responde sobre el estado) · **repositorio** · **DPC** (declaración de prácticas de certificación) |
| Certificado X.509 | Vincula una **identidad** con una **clave pública**, y lo **firma la AC**. Estándar **X.509 v3** (RFC 5280): número de serie, emisor, sujeto, periodo de validez, clave pública, extensiones y firma de la AC |
| Revocación | **CRL**: lista firmada y publicada periódicamente → puede estar **desactualizada**. **OCSP** (RFC 6960): consulta **en línea** del estado de **un** certificado → información fresca, pero exige disponibilidad del respondedor. **OCSP stapling**: lo aporta el propio servidor |
| Firma electrónica (eIDAS) | Tres modalidades: **simple**, **avanzada** (vinculada al firmante, detecta cambios, control exclusivo) y **cualificada** (avanzada + **DCCFE/QSCD** + **certificado cualificado**). Solo la **cualificada** tiene efecto jurídico **equivalente a la manuscrita** en toda la UE (art. 25.2 del Reglamento 910/2014) |
| Formatos de firma | **CAdES** (binario, cualquier fichero) · **XAdES** (XML) · **PAdES** (PDF) · **ASiC** (contenedor). Niveles de longevidad **-B, -T, -LT, -LTA**: la **T** añade sello de tiempo y la **LTA** permite el archivo a largo plazo |
| Firma en el ENS | **mp.info.3**, dimensiones **I** y **A**: nivel BAJO = cualquier firma admitida en derecho (incluido el **CSV**); MEDIO = **+R1 certificados cualificados +R2 algoritmos autorizados por el CCN +R3 verificación y validación duraderas**; ALTO = **+R4 segundo factor** |
| Sellado de tiempo | **mp.info.4**, dimensión **T**, exigible solo en nivel **ALTO**. Aporta prueba de la **existencia de un dato en un instante**. Protocolo **TSP (RFC 3161)**; en la UE, **sello cualificado de tiempo electrónico** |
