# Tema 32 — Catálogo de Diagramas

> **Título oficial**: Conceptos de seguridad de los sistemas de información. Seguridad física. Seguridad lógica. Amenazas y vulnerabilidades. Técnicas criptográficas y protocolos seguros. Mecanismos de firma digital.
>
> **Versión**: v1.0
> **Fecha**: 2026-08-27
> **Autor**: ETRIVIUM
> **Formato**: SVG inline (zero-dependencias, escalable, imprimible, accesible con role/aria-label)
> **Paleta**: Ayuntamiento de Madrid #0055a0 (primario) + #d13c3c (alertas) + #2d8659 (ventajas) + #e89822 (callouts)
> **Nota técnica**: las clases CSS de cada SVG llevan sufijo numérico único (`.t1`, `.h1`…) para evitar colisiones de estilos entre los 18 diagramas embebidos en la misma página.

---

## Índice de diagramas

| ID | Título | Sección | Tipo | Formato |
|---|---|---|---|---|
| D1 | Las cinco dimensiones del ENS y la categorización del sistema | §1.1.2 | Esquema + algoritmo | 680×360 |
| D2 | El modelo del riesgo: del activo al riesgo residual | §1.1.3 | Flujo | 680×340 |
| D3 | Marco normativo aplicable a un sistema municipal | §1.2.2 | Capas | 680×340 |
| D4 | Defensa en profundidad: organizativa, física y lógica | §1.1.1 | Capas concéntricas | 680×344 |
| D5 | Anillos de seguridad física y medidas `mp.if` del ENS | §2.1.1 | Anillos + tabla | 680×360 |
| D6 | Suministro eléctrico y climatización de un CPD | §2.2.1 | Cadena + esquema | 680×352 |
| D7 | Identificación, autenticación, autorización y trazabilidad | §3.1 | Flujo | 680×324 |
| D8 | Los tres factores y la autenticación multifactor | §3.1.1 | Comparativa | 680×344 |
| D9 | Modelos de control de acceso: DAC, MAC, RBAC y ABAC | §3.1.2 | Comparativa | 680×354 |
| D10 | Taxonomía del código malicioso y vectores de infección | §4.1.1 | Árbol + entradas | 680×365 |
| D11 | La cadena de ataque y sus contramedidas por fase | §4.1.2 | Flujo por fases | 680×342 |
| D12 | Ciclo de vulnerabilidades y ventana de exposición | §4.2.1 | Ciclo + línea temporal | 680×352 |
| D13 | Simétrica, asimétrica y funciones hash comparadas | §5.1.1 | Comparativa | 680×364 |
| D14 | Cifrado híbrido (sobre digital) y saludo TLS | §5.1.1 | Flujo | 680×352 |
| D15 | IPsec: AH y ESP, modo transporte y modo túnel | §5.2.1 | Estructura de paquete | 680×352 |
| D16 | PKI: emisión, validación y revocación de certificados | §6.1.1 | Esquema de actores | 680×364 |
| D17 | Firma electrónica: generación y verificación | §6.2.1 | Flujo doble | 680×352 |
| D18 | Modalidades eIDAS, formatos y niveles de longevidad | §6.2.1 | Escalera + tabla | 680×374 |

---

## D1 · Las cinco dimensiones del ENS y la categorización del sistema

**Sección**: §1.1.2 — Confidencialidad, integridad, disponibilidad, autenticidad y no repudio · §1.2.1
**Propósito**: Fijar las cinco dimensiones C-I-T-A-D y el algoritmo exacto que lleva de los niveles por dimensión a la categoría del sistema, incluida la regla de que manda la dimensión más alta.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 360" role="img" aria-label="Las cinco dimensiones de la seguridad del Esquema Nacional de Seguridad: confidencialidad, integridad, trazabilidad, autenticidad y disponibilidad, con el algoritmo que determina la categoría básica, media o alta del sistema a partir del nivel bajo, medio o alto de cada dimensión">
  <style>.t1{font:700 11px system-ui,sans-serif;fill:#fff}.s1{font:9px system-ui,sans-serif;fill:#fff}.d1{font:9px system-ui,sans-serif;fill:#333}.h1{font:700 13px system-ui,sans-serif;fill:#0055a0}.k1{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n1{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h1">Cinco dimensiones, tres niveles, tres categorías</text>
  <text x="20" y="42" class="k1">LAS CINCO DIMENSIONES (anexo I, ap. 2)</text>
  <rect x="20" y="50" width="124" height="46" rx="5" fill="#0055a0"/><text x="82" y="68" text-anchor="middle" class="t1">C</text><text x="82" y="84" text-anchor="middle" class="s1">Confidencialidad</text>
  <rect x="152" y="50" width="124" height="46" rx="5" fill="#0055a0"/><text x="214" y="68" text-anchor="middle" class="t1">I</text><text x="214" y="84" text-anchor="middle" class="s1">Integridad</text>
  <rect x="284" y="50" width="124" height="46" rx="5" fill="#e89822"/><text x="346" y="68" text-anchor="middle" class="t1">T</text><text x="346" y="84" text-anchor="middle" class="s1">Trazabilidad</text>
  <rect x="416" y="50" width="124" height="46" rx="5" fill="#0055a0"/><text x="478" y="68" text-anchor="middle" class="t1">A</text><text x="478" y="84" text-anchor="middle" class="s1">Autenticidad</text>
  <rect x="548" y="50" width="112" height="46" rx="5" fill="#0055a0"/><text x="604" y="68" text-anchor="middle" class="t1">D</text><text x="604" y="84" text-anchor="middle" class="s1">Disponibilidad</text>
  <rect x="20" y="104" width="640" height="24" rx="4" fill="#fdf3e3"/>
  <text x="340" y="120" text-anchor="middle" class="d1">El NO REPUDIO no es dimensión del ENS: es efecto jurídico de autenticidad + integridad + trazabilidad</text>
  <text x="20" y="152" class="k1">PASO 1 · NIVEL DE CADA DIMENSIÓN (por gravedad del perjuicio)</text>
  <rect x="20" y="160" width="206" height="34" rx="4" fill="#eef3f8"/><text x="123" y="181" text-anchor="middle" class="d1">BAJO — perjuicio limitado</text>
  <rect x="237" y="160" width="206" height="34" rx="4" fill="#fdf3e3"/><text x="340" y="181" text-anchor="middle" class="d1">MEDIO — perjuicio grave</text>
  <rect x="454" y="160" width="206" height="34" rx="4" fill="#fbeaea"/><text x="557" y="181" text-anchor="middle" class="d1">ALTO — perjuicio muy grave</text>
  <text x="20" y="214" class="n1">Si una dimensión no se ve afectada, NO se le adscribe ningún nivel</text>
  <text x="20" y="238" class="k1">PASO 2 · CATEGORÍA DEL SISTEMA (manda la dimensión más alta)</text>
  <rect x="20" y="246" width="206" height="50" rx="4" fill="#2d8659"/><text x="123" y="266" text-anchor="middle" class="t1">BÁSICA</text><text x="123" y="283" text-anchor="middle" class="s1">alguna en BAJO, ninguna superior</text>
  <rect x="237" y="246" width="206" height="50" rx="4" fill="#e89822"/><text x="340" y="266" text-anchor="middle" class="t1">MEDIA</text><text x="340" y="283" text-anchor="middle" class="s1">alguna en MEDIO, ninguna superior</text>
  <rect x="454" y="246" width="206" height="50" rx="4" fill="#d13c3c"/><text x="557" y="266" text-anchor="middle" class="t1">ALTA</text><text x="557" y="283" text-anchor="middle" class="s1">alguna en ALTO</text>
  <rect x="20" y="306" width="640" height="34" rx="4" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="321" text-anchor="middle" class="k1">NIVEL se predica de la DIMENSIÓN · CATEGORÍA se predica del SISTEMA</text>
  <text x="340" y="334" text-anchor="middle" class="n1">Reevaluación anual o ante modificaciones significativas · las dimensiones que no fijaron la categoría conservan su nivel</text>
  <text x="670" y="352" text-anchor="end" class="n1">[Fuente: ENS, anexo I]</text>
</svg>
```

---

## D2 · El modelo del riesgo: del activo al riesgo residual

**Sección**: §1.1.3 — Análisis y gestión de riesgos
**Propósito**: Encadenar los seis términos del análisis de riesgos en el orden causal correcto y mostrar dónde actúa la salvaguarda, que es la pregunta conceptual más repetida.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Modelo del riesgo según MAGERIT: un activo tiene valor y vulnerabilidades, una amenaza externa las explota produciendo un impacto, la combinación de impacto y probabilidad es el riesgo, las salvaguardas lo reducen y lo que queda es el riesgo residual que debe aceptarse formalmente">
  <style>.t2{font:700 10.5px system-ui,sans-serif;fill:#fff}.s2{font:8.5px system-ui,sans-serif;fill:#fff}.d2{font:9px system-ui,sans-serif;fill:#333}.h2{font:700 13px system-ui,sans-serif;fill:#0055a0}.k2{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n2{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h2">La cadena del riesgo y donde actúa cada salvaguarda</text>
  <rect x="20" y="40" width="130" height="52" rx="5" fill="#0055a0"/><text x="85" y="60" text-anchor="middle" class="t2">ACTIVO</text><text x="85" y="74" text-anchor="middle" class="s2">tiene VALOR</text><text x="85" y="86" text-anchor="middle" class="s2">y VULNERABILIDADES</text>
  <rect x="196" y="40" width="130" height="52" rx="5" fill="#d13c3c"/><text x="261" y="60" text-anchor="middle" class="t2">AMENAZA</text><text x="261" y="74" text-anchor="middle" class="s2">externa al activo</text><text x="261" y="86" text-anchor="middle" class="s2">NO se puede eliminar</text>
  <rect x="372" y="40" width="130" height="52" rx="5" fill="#e89822"/><text x="437" y="60" text-anchor="middle" class="t2">IMPACTO</text><text x="437" y="74" text-anchor="middle" class="s2">degradación de las</text><text x="437" y="86" text-anchor="middle" class="s2">dimensiones</text>
  <rect x="548" y="40" width="112" height="52" rx="5" fill="#7a2f8a"/><text x="604" y="60" text-anchor="middle" class="t2">RIESGO</text><text x="604" y="74" text-anchor="middle" class="s2">impacto x</text><text x="604" y="86" text-anchor="middle" class="s2">probabilidad</text>
  <path d="M150 66 L192 66" stroke="#666" stroke-width="1.5" marker-end="url(#a2)"/>
  <path d="M326 66 L368 66" stroke="#666" stroke-width="1.5" marker-end="url(#a2)"/>
  <path d="M502 66 L544 66" stroke="#666" stroke-width="1.5" marker-end="url(#a2)"/>
  <defs><marker id="a2" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <text x="171" y="108" text-anchor="middle" class="n2">explota</text><text x="347" y="108" text-anchor="middle" class="n2">produce</text><text x="523" y="108" text-anchor="middle" class="n2">se estima</text>
  <rect x="20" y="122" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="139" text-anchor="middle" class="d2">Sin VULNERABILIDAD que explotar, la amenaza no se materializa: la salvaguarda actúa sobre la vulnerabilidad y sobre el impacto</text>
  <text x="20" y="172" class="k2">TRATAMIENTO DEL RIESGO · CUATRO OPCIONES</text>
  <rect x="20" y="180" width="155" height="44" rx="4" fill="#2d8659"/><text x="97" y="198" text-anchor="middle" class="t2">EVITAR</text><text x="97" y="213" text-anchor="middle" class="s2">suprimir la actividad</text>
  <rect x="182" y="180" width="155" height="44" rx="4" fill="#0055a0"/><text x="259" y="198" text-anchor="middle" class="t2">MITIGAR</text><text x="259" y="213" text-anchor="middle" class="s2">aplicar salvaguardas</text>
  <rect x="344" y="180" width="155" height="44" rx="4" fill="#e89822"/><text x="421" y="198" text-anchor="middle" class="t2">TRANSFERIR</text><text x="421" y="213" text-anchor="middle" class="s2">seguro o contrato</text>
  <rect x="506" y="180" width="154" height="44" rx="4" fill="#888"/><text x="583" y="198" text-anchor="middle" class="t2">ACEPTAR</text><text x="583" y="213" text-anchor="middle" class="s2">asumir el riesgo</text>
  <rect x="20" y="238" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="255" text-anchor="middle" class="d2">Transferir el riesgo NO transfiere la responsabilidad: la responsabilidad última sigue siendo de la entidad pública</text>
  <rect x="140" y="276" width="400" height="34" rx="5" fill="none" stroke="#7a2f8a" stroke-width="2"/>
  <text x="340" y="291" text-anchor="middle" class="k2">RIESGO RESIDUAL = el que permanece tras las salvaguardas</text>
  <text x="340" y="304" text-anchor="middle" class="n2">Nunca es cero y debe ser ACEPTADO FORMALMENTE por la dirección</text>
  <text x="670" y="332" text-anchor="end" class="n2">[Fuente: MAGERIT; ENS, arts. 7 y 14]</text>
</svg>
```

---

## D3 · Marco normativo aplicable a un sistema municipal

**Sección**: §1.2.2 — Protección de datos personales y garantía de derechos digitales
**Propósito**: Situar en capas las normas que se superponen sobre un mismo sistema público y aclarar qué protege cada una, que es la confusión más frecuente entre ENS y RGPD.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Capas normativas que se superponen sobre un sistema de información municipal: Esquema Nacional de Seguridad, Reglamento General de Protección de Datos y LOPDGDD, eIDAS y Ley 6 de 2020, leyes 39 y 40 de 2015, y normativa de ciberseguridad NIS2, con indicación de qué protege cada una">
  <style>.t3{font:700 10.5px system-ui,sans-serif;fill:#fff}.s3{font:8.5px system-ui,sans-serif;fill:#fff}.d3{font:9px system-ui,sans-serif;fill:#333}.h3{font:700 13px system-ui,sans-serif;fill:#0055a0}.k3{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n3{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h3">Cinco marcos sobre el mismo sistema</text>
  <text x="30" y="42" class="k3">NORMA</text><text x="250" y="42" class="k3">QUÉ PROTEGE</text><text x="520" y="42" class="k3">EN ESTE TEMA</text>
  <rect x="20" y="50" width="200" height="40" rx="4" fill="#0055a0"/><text x="120" y="67" text-anchor="middle" class="t3">ENS — RD 311/2022</text><text x="120" y="81" text-anchor="middle" class="s3">obligatorio para el sector público</text>
  <rect x="228" y="50" width="270" height="40" rx="4" fill="#eef3f8"/><text x="363" y="67" text-anchor="middle" class="d3">La información y los servicios de la</text><text x="363" y="81" text-anchor="middle" class="d3">organización</text>
  <rect x="506" y="50" width="154" height="40" rx="4" fill="#f5f5f5"/><text x="583" y="74" text-anchor="middle" class="d3">Secciones 1 a 6</text>
  <rect x="20" y="96" width="200" height="40" rx="4" fill="#7a2f8a"/><text x="120" y="113" text-anchor="middle" class="t3">RGPD + LOPDGDD</text><text x="120" y="127" text-anchor="middle" class="s3">UE 2016/679 y LO 3/2018</text>
  <rect x="228" y="96" width="270" height="40" rx="4" fill="#eef3f8"/><text x="363" y="113" text-anchor="middle" class="d3">Los derechos y libertades de las</text><text x="363" y="127" text-anchor="middle" class="d3">personas físicas</text>
  <rect x="506" y="96" width="154" height="40" rx="4" fill="#f5f5f5"/><text x="583" y="113" text-anchor="middle" class="d3">Art. 32 seguridad</text><text x="583" y="127" text-anchor="middle" class="d3">72 h brechas</text>
  <rect x="20" y="142" width="200" height="40" rx="4" fill="#2d8659"/><text x="120" y="159" text-anchor="middle" class="t3">eIDAS + Ley 6/2020</text><text x="120" y="173" text-anchor="middle" class="s3">UE 910/2014 y UE 2024/1183</text>
  <rect x="228" y="142" width="270" height="40" rx="4" fill="#eef3f8"/><text x="363" y="159" text-anchor="middle" class="d3">La confianza en la identidad y en la</text><text x="363" y="173" text-anchor="middle" class="d3">firma electrónicas</text>
  <rect x="506" y="142" width="154" height="40" rx="4" fill="#f5f5f5"/><text x="583" y="166" text-anchor="middle" class="d3">Sección 6</text>
  <rect x="20" y="188" width="200" height="40" rx="4" fill="#e89822"/><text x="120" y="205" text-anchor="middle" class="t3">Leyes 39 y 40 de 2015</text><text x="120" y="219" text-anchor="middle" class="s3">+ RD 203/2021 y ENI</text>
  <rect x="228" y="188" width="270" height="40" rx="4" fill="#eef3f8"/><text x="363" y="205" text-anchor="middle" class="d3">La validez jurídica del acto y del</text><text x="363" y="219" text-anchor="middle" class="d3">documento administrativo</text>
  <rect x="506" y="188" width="154" height="40" rx="4" fill="#f5f5f5"/><text x="583" y="205" text-anchor="middle" class="d3">Arts. 9 y 10 · CSV</text><text x="583" y="219" text-anchor="middle" class="d3">sello de órgano</text>
  <rect x="20" y="234" width="200" height="40" rx="4" fill="#d13c3c"/><text x="120" y="251" text-anchor="middle" class="t3">NIS2 y RD 43/2021</text><text x="120" y="265" text-anchor="middle" class="s3">servicios esenciales</text>
  <rect x="228" y="234" width="270" height="40" rx="4" fill="#eef3f8"/><text x="363" y="251" text-anchor="middle" class="d3">La resiliencia del servicio esencial</text><text x="363" y="265" text-anchor="middle" class="d3">y la notificación de incidentes</text>
  <rect x="506" y="234" width="154" height="40" rx="4" fill="#f5f5f5"/><text x="583" y="251" text-anchor="middle" class="d3">Alerta 24 h</text><text x="583" y="265" text-anchor="middle" class="d3">CSIRT de referencia</text>
  <rect x="20" y="286" width="640" height="30" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="305" text-anchor="middle" class="k3">Un mismo incidente puede activar tres relojes a la vez, y corren EN PARALELO</text>
  <text x="670" y="332" text-anchor="end" class="n3">[Fuente: ENS; RGPD; LOPDGDD; EIDAS; L39-2015; NIS2]</text>
</svg>
```

---

## D4 · Defensa en profundidad: organizativa, física y lógica

**Sección**: §1.1.1 — Concepto de seguridad de la información
**Propósito**: Visualizar el art. 9 del ENS, que exige líneas de defensa de las tres naturalezas, y asociar a cada capa las medidas del anexo II que la materializan.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 344" role="img" aria-label="Defensa en profundidad en capas sucesivas desde la política de seguridad y la formación hasta el dato cifrado, mostrando que las líneas de defensa han de ser de naturaleza organizativa, física y lógica según el artículo 9 del Esquema Nacional de Seguridad">
  <style>.t4{font:700 10.5px system-ui,sans-serif;fill:#fff}.s4{font:8.5px system-ui,sans-serif;fill:#fff}.d4{font:9px system-ui,sans-serif;fill:#333}.h4{font:700 13px system-ui,sans-serif;fill:#0055a0}.k4{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n4{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h4">Múltiples capas: si una cae, las demás siguen</text>
  <text x="30" y="42" class="k4">NATURALEZA</text><text x="200" y="42" class="k4">CAPA</text><text x="440" y="42" class="k4">MEDIDAS DEL ANEXO II</text>
  <rect x="20" y="50" width="140" height="44" rx="4" fill="#7a2f8a"/><text x="90" y="70" text-anchor="middle" class="t4">ORGANIZATIVA</text><text x="90" y="85" text-anchor="middle" class="s4">el papel y las personas</text>
  <rect x="168" y="50" width="250" height="44" rx="4" fill="#eef3f8"/><text x="293" y="70" text-anchor="middle" class="d4">Política, normativa, procedimientos,</text><text x="293" y="85" text-anchor="middle" class="d4">formación y concienciación</text>
  <rect x="426" y="50" width="234" height="44" rx="4" fill="#f5f5f5"/><text x="543" y="70" text-anchor="middle" class="d4">org.1 a org.4 · mp.per.1 a mp.per.4</text><text x="543" y="85" text-anchor="middle" class="d4">op.pl · op.exp.7</text>
  <rect x="20" y="100" width="140" height="44" rx="4" fill="#0055a0"/><text x="90" y="120" text-anchor="middle" class="t4">FÍSICA</text><text x="90" y="135" text-anchor="middle" class="s4">el edificio y la sala</text>
  <rect x="168" y="100" width="250" height="44" rx="4" fill="#eef3f8"/><text x="293" y="120" text-anchor="middle" class="d4">Perímetro, control de acceso,</text><text x="293" y="135" text-anchor="middle" class="d4">energía, clima e incendios</text>
  <rect x="426" y="100" width="234" height="44" rx="4" fill="#f5f5f5"/><text x="543" y="120" text-anchor="middle" class="d4">mp.if.1 a mp.if.7</text><text x="543" y="135" text-anchor="middle" class="d4">mp.eq.1 a mp.eq.4</text>
  <rect x="20" y="150" width="140" height="44" rx="4" fill="#2d8659"/><text x="90" y="170" text-anchor="middle" class="t4">LÓGICA — red</text><text x="90" y="185" text-anchor="middle" class="s4">el camino</text>
  <rect x="168" y="150" width="250" height="44" rx="4" fill="#eef3f8"/><text x="293" y="170" text-anchor="middle" class="d4">Segmentación, perímetro seguro,</text><text x="293" y="185" text-anchor="middle" class="d4">canal cifrado y monitorización</text>
  <rect x="426" y="150" width="234" height="44" rx="4" fill="#f5f5f5"/><text x="543" y="170" text-anchor="middle" class="d4">mp.com.1 a mp.com.4</text><text x="543" y="185" text-anchor="middle" class="d4">op.mon.1 a op.mon.3</text>
  <rect x="20" y="200" width="140" height="44" rx="4" fill="#2d8659"/><text x="90" y="220" text-anchor="middle" class="t4">LÓGICA — sistema</text><text x="90" y="235" text-anchor="middle" class="s4">el equipo</text>
  <rect x="168" y="200" width="250" height="44" rx="4" fill="#eef3f8"/><text x="293" y="220" text-anchor="middle" class="d4">Bastionado, parcheo, antimalware,</text><text x="293" y="235" text-anchor="middle" class="d4">control de acceso y registro</text>
  <rect x="426" y="200" width="234" height="44" rx="4" fill="#f5f5f5"/><text x="543" y="220" text-anchor="middle" class="d4">op.exp.2 · op.exp.4 · op.exp.6</text><text x="543" y="235" text-anchor="middle" class="d4">op.acc.1 a op.acc.6 · op.exp.8</text>
  <rect x="20" y="250" width="140" height="44" rx="4" fill="#e89822"/><text x="90" y="270" text-anchor="middle" class="t4">LÓGICA — dato</text><text x="90" y="285" text-anchor="middle" class="s4">el activo esencial</text>
  <rect x="168" y="250" width="250" height="44" rx="4" fill="#eef3f8"/><text x="293" y="270" text-anchor="middle" class="d4">Cifrado, firma, copias de seguridad</text><text x="293" y="285" text-anchor="middle" class="d4">y borrado seguro</text>
  <rect x="426" y="250" width="234" height="44" rx="4" fill="#f5f5f5"/><text x="543" y="270" text-anchor="middle" class="d4">mp.si.2 · mp.si.5 · mp.info.3</text><text x="543" y="285" text-anchor="middle" class="d4">mp.info.6 · op.exp.10</text>
  <rect x="20" y="302" width="640" height="20" rx="4" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="316" text-anchor="middle" class="k4">Art. 9.2 del ENS: las líneas de defensa han de ser organizativas, físicas Y lógicas</text>
  <text x="670" y="336" text-anchor="end" class="n4">[Fuente: ENS, arts. 8 y 9, anexo II]</text>
</svg>
```

---

## D5 · Anillos de seguridad física y medidas `mp.if` del ENS

**Sección**: §2.1.1 — Medidas de seguridad en entradas, edificios y áreas restringidas
**Propósito**: Recorrer los cinco anillos concéntricos de protección física y anclar cada uno a la medida `mp.if` correspondiente, con sus condiciones de aplicación por categoría o nivel.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 360" role="img" aria-label="Cinco anillos concéntricos de seguridad física desde el perímetro exterior hasta el bastidor, con los controles típicos de cada anillo y la tabla de las siete medidas mp punto if del Esquema Nacional de Seguridad y su aplicación por categoría o nivel de disponibilidad">
  <style>.t5{font:700 10px system-ui,sans-serif;fill:#fff}.s5{font:8.5px system-ui,sans-serif;fill:#fff}.d5{font:9px system-ui,sans-serif;fill:#333}.h5{font:700 13px system-ui,sans-serif;fill:#0055a0}.k5{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n5{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h5">Anillos de protección física y medidas mp.if</text>
  <rect x="20" y="34" width="320" height="30" rx="4" fill="#0055a0"/><text x="180" y="53" text-anchor="middle" class="t5">1 · PERÍMETRO — vallado, iluminación, CCTV</text>
  <rect x="42" y="68" width="276" height="30" rx="4" fill="#1a6bb0"/><text x="180" y="87" text-anchor="middle" class="t5">2 · EDIFICIO — recepción, tarjeta, registro</text>
  <rect x="64" y="102" width="232" height="30" rx="4" fill="#3781c0"/><text x="180" y="121" text-anchor="middle" class="t5">3 · ZONAS — segmentación por planta</text>
  <rect x="86" y="136" width="188" height="30" rx="4" fill="#e89822"/><text x="180" y="155" text-anchor="middle" class="t5">4 · SALA TÉCNICA — doble factor</text>
  <rect x="108" y="170" width="144" height="30" rx="4" fill="#d13c3c"/><text x="180" y="189" text-anchor="middle" class="t5">5 · BASTIDOR — cerradura</text>
  <text x="180" y="216" text-anchor="middle" class="n5">Cada anillo exige un control más estricto que el anterior</text>
  <rect x="368" y="34" width="292" height="166" rx="5" fill="#eef3f8"/>
  <text x="380" y="52" class="k5">ZONA CONTROLADA (definición del ENS)</text>
  <text x="380" y="70" class="d5">Zona NO de acceso público en la que el usuario</text>
  <text x="380" y="84" class="d5">ya se ha autenticado físicamente antes de llegar</text>
  <text x="380" y="98" class="d5">al equipo, de forma distinta al acceso lógico.</text>
  <text x="380" y="120" class="k5">EJEMPLO DE ZONA NO CONTROLADA: INTERNET</text>
  <rect x="380" y="130" width="268" height="58" rx="4" fill="#fbeaea"/>
  <text x="514" y="148" text-anchor="middle" class="d5">Consecuencia [op.acc.6.r8]: acceso desde o a</text>
  <text x="514" y="162" text-anchor="middle" class="d5">través de zona NO controlada exige DOBLE</text>
  <text x="514" y="176" text-anchor="middle" class="d5">FACTOR, y en TODOS los niveles</text>
  <text x="20" y="240" class="k5">LAS SIETE MEDIDAS mp.if · PROTECCIÓN DE LAS INSTALACIONES E INFRAESTRUCTURAS</text>
  <rect x="20" y="248" width="106" height="46" rx="4" fill="#0055a0"/><text x="73" y="265" text-anchor="middle" class="t5">mp.if.1</text><text x="73" y="279" text-anchor="middle" class="s5">áreas separadas</text><text x="73" y="290" text-anchor="middle" class="s5">todas las categorías</text>
  <rect x="132" y="248" width="106" height="46" rx="4" fill="#0055a0"/><text x="185" y="265" text-anchor="middle" class="t5">mp.if.2</text><text x="185" y="279" text-anchor="middle" class="s5">identificar personas</text><text x="185" y="290" text-anchor="middle" class="s5">todas las categorías</text>
  <rect x="244" y="248" width="106" height="46" rx="4" fill="#0055a0"/><text x="297" y="265" text-anchor="middle" class="t5">mp.if.3</text><text x="297" y="279" text-anchor="middle" class="s5">acondicionamiento</text><text x="297" y="290" text-anchor="middle" class="s5">todas las categorías</text>
  <rect x="356" y="248" width="106" height="46" rx="4" fill="#e89822"/><text x="409" y="265" text-anchor="middle" class="t5">mp.if.4</text><text x="409" y="279" text-anchor="middle" class="s5">energía eléctrica</text><text x="409" y="290" text-anchor="middle" class="s5">D · MEDIO+ = +R1</text>
  <rect x="468" y="248" width="106" height="46" rx="4" fill="#e89822"/><text x="521" y="265" text-anchor="middle" class="t5">mp.if.5</text><text x="521" y="279" text-anchor="middle" class="s5">incendios</text><text x="521" y="290" text-anchor="middle" class="s5">D · los tres niveles</text>
  <rect x="580" y="248" width="80" height="46" rx="4" fill="#d13c3c"/><text x="620" y="265" text-anchor="middle" class="t5">mp.if.6</text><text x="620" y="279" text-anchor="middle" class="s5">inundaciones</text><text x="620" y="290" text-anchor="middle" class="s5">n.a. en BAJO</text>
  <rect x="20" y="300" width="640" height="30" rx="4" fill="#f5f5f5"/>
  <text x="340" y="313" text-anchor="middle" class="d5">mp.if.7 · Registro pormenorizado de entrada y salida de equipamiento esencial, con identificación de QUIÉN AUTORIZA</text>
  <text x="340" y="326" text-anchor="middle" class="n5">Aplica en las tres categorías · única medida de la familia que no aplica en algún caso: mp.if.6 en nivel BAJO</text>
  <text x="670" y="352" text-anchor="end" class="n5">[Fuente: ENS, art. 18 y anexo II, 5.1]</text>
</svg>
```

---

## D6 · Suministro eléctrico y climatización de un CPD

**Sección**: §2.2.1 — Suministro eléctrico, climatización y prevención de incendios
**Propósito**: Mostrar la cadena eléctrica completa con lo que cubre cada eslabón y el reparto temporal entre SAI y grupo electrógeno, junto con la disciplina de pasillo frío y caliente.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Cadena de suministro eléctrico de un centro de proceso de datos: red eléctrica, sistema de alimentación ininterrumpida por baterías y grupo electrógeno, con el reparto temporal entre ambos, y esquema de climatización con pasillo frío y pasillo caliente confinados">
  <style>.t6{font:700 10.5px system-ui,sans-serif;fill:#fff}.s6{font:8.5px system-ui,sans-serif;fill:#fff}.d6{font:9px system-ui,sans-serif;fill:#333}.h6{font:700 13px system-ui,sans-serif;fill:#0055a0}.k6{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n6{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h6">La cadena eléctrica: quién cubre qué, y durante cuánto</text>
  <rect x="20" y="36" width="120" height="46" rx="5" fill="#888"/><text x="80" y="55" text-anchor="middle" class="t6">RED ELÉCTRICA</text><text x="80" y="70" text-anchor="middle" class="s6">2 acometidas</text>
  <rect x="176" y="36" width="120" height="46" rx="5" fill="#0055a0"/><text x="236" y="55" text-anchor="middle" class="t6">SAI / UPS</text><text x="236" y="70" text-anchor="middle" class="s6">baterías, 10-30 min</text>
  <rect x="332" y="36" width="120" height="46" rx="5" fill="#2d8659"/><text x="392" y="55" text-anchor="middle" class="t6">GRUPO</text><text x="392" y="70" text-anchor="middle" class="s6">combustible, horas</text>
  <rect x="488" y="36" width="172" height="46" rx="5" fill="#e89822"/><text x="574" y="55" text-anchor="middle" class="t6">PDU Y BASTIDORES</text><text x="574" y="70" text-anchor="middle" class="s6">doble vía A y B</text>
  <path d="M140 59 L172 59" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <path d="M296 59 L328 59" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <path d="M452 59 L484 59" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <defs><marker id="a6" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <text x="20" y="106" class="k6">LÍNEA TEMPORAL DE UN CORTE DE SUMINISTRO</text>
  <rect x="20" y="114" width="640" height="26" rx="4" fill="#f5f5f5"/>
  <rect x="20" y="114" width="130" height="26" rx="4" fill="#0055a0"/><text x="85" y="131" text-anchor="middle" class="s6">SAI (inmediato, sin corte)</text>
  <rect x="150" y="114" width="510" height="26" fill="#2d8659"/><text x="405" y="131" text-anchor="middle" class="s6">GRUPO ELECTRÓGENO (arranque en decenas de segundos, autonomía de horas o días)</text>
  <text x="20" y="156" class="n6">El SAI cubre el ARRANQUE del generador y filtra la calidad de la onda; el generador cubre la DURACIÓN. No se sustituyen.</text>
  <rect x="20" y="168" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="185" text-anchor="middle" class="d6">mp.if.4 R1: el abastecimiento debe garantizarse el tiempo suficiente para TERMINAR ORDENADAMENTE y salvaguardar la información</text>
  <text x="20" y="216" class="k6">REDUNDANCIA</text>
  <rect x="20" y="224" width="100" height="34" rx="4" fill="#eef3f8"/><text x="70" y="245" text-anchor="middle" class="d6">N — sin margen</text>
  <rect x="128" y="224" width="100" height="34" rx="4" fill="#eef3f8"/><text x="178" y="245" text-anchor="middle" class="d6">N+1 — 1 reserva</text>
  <rect x="236" y="224" width="100" height="34" rx="4" fill="#eef3f8"/><text x="286" y="245" text-anchor="middle" class="d6">2N — duplicado</text>
  <rect x="344" y="224" width="100" height="34" rx="4" fill="#eef3f8"/><text x="394" y="245" text-anchor="middle" class="d6">2(N+1) — máximo</text>
  <rect x="460" y="224" width="200" height="34" rx="4" fill="#0055a0"/><text x="560" y="239" text-anchor="middle" class="s6">Tier III = mantenible sin parar</text><text x="560" y="252" text-anchor="middle" class="s6">Tier IV = tolerante a fallos</text>
  <text x="20" y="280" class="k6">CLIMATIZACIÓN · PASILLO FRÍO Y PASILLO CALIENTE</text>
  <rect x="20" y="288" width="70" height="34" rx="3" fill="#666"/><text x="55" y="309" text-anchor="middle" class="s6">RACK</text>
  <rect x="96" y="288" width="90" height="34" rx="3" fill="#cfe4f7"/><text x="141" y="309" text-anchor="middle" class="d6">PASILLO FRÍO</text>
  <rect x="192" y="288" width="70" height="34" rx="3" fill="#666"/><text x="227" y="309" text-anchor="middle" class="s6">RACK</text>
  <rect x="268" y="288" width="90" height="34" rx="3" fill="#f7cfcf"/><text x="313" y="309" text-anchor="middle" class="d6">PASILLO CALIENTE</text>
  <rect x="364" y="288" width="70" height="34" rx="3" fill="#666"/><text x="399" y="309" text-anchor="middle" class="s6">RACK</text>
  <rect x="444" y="288" width="216" height="34" rx="4" fill="#f5f5f5"/><text x="552" y="303" text-anchor="middle" class="d6">Frentes enfrentados y pasillo confinado</text><text x="552" y="316" text-anchor="middle" class="d6">ASHRAE clase A1: 18-27 °C de entrada</text>
  <text x="670" y="344" text-anchor="end" class="n6">[Fuente: ENS, mp.if.3-5; TIA942; ASHRAE]</text>
</svg>
```

---

## D7 · Identificación, autenticación, autorización y trazabilidad

**Sección**: §3.1 — Identificación, autenticación y autorización
**Propósito**: Separar cuatro conceptos que el lenguaje corriente confunde, situándolos en su orden temporal y asociando a cada uno la medida del ENS que lo exige.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 324" role="img" aria-label="Secuencia de identificación, autenticación, autorización y trazabilidad en un acceso, con la pregunta que responde cada etapa, un ejemplo concreto y la medida del Esquema Nacional de Seguridad que la exige">
  <style>.t7{font:700 11px system-ui,sans-serif;fill:#fff}.s7{font:8.5px system-ui,sans-serif;fill:#fff}.d7{font:9px system-ui,sans-serif;fill:#333}.h7{font:700 13px system-ui,sans-serif;fill:#0055a0}.k7{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n7{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h7">Cuatro etapas, cuatro preguntas distintas</text>
  <rect x="20" y="38" width="152" height="42" rx="5" fill="#0055a0"/><text x="96" y="56" text-anchor="middle" class="t7">1 · IDENTIFICACIÓN</text><text x="96" y="72" text-anchor="middle" class="s7">Quién dices que eres</text>
  <rect x="184" y="38" width="152" height="42" rx="5" fill="#2d8659"/><text x="260" y="56" text-anchor="middle" class="t7">2 · AUTENTICACIÓN</text><text x="260" y="72" text-anchor="middle" class="s7">Puedes demostrarlo</text>
  <rect x="348" y="38" width="152" height="42" rx="5" fill="#e89822"/><text x="424" y="56" text-anchor="middle" class="t7">3 · AUTORIZACIÓN</text><text x="424" y="72" text-anchor="middle" class="s7">Qué puedes hacer</text>
  <rect x="512" y="38" width="148" height="42" rx="5" fill="#7a2f8a"/><text x="586" y="56" text-anchor="middle" class="t7">4 · TRAZABILIDAD</text><text x="586" y="72" text-anchor="middle" class="s7">Qué has hecho</text>
  <path d="M172 59 L180 59" stroke="#666" stroke-width="1.5"/><path d="M336 59 L344 59" stroke="#666" stroke-width="1.5"/><path d="M500 59 L508 59" stroke="#666" stroke-width="1.5"/>
  <text x="20" y="102" class="k7">EJEMPLO EN LA SEDE MUNICIPAL</text>
  <rect x="20" y="110" width="152" height="40" rx="4" fill="#eef3f8"/><text x="96" y="126" text-anchor="middle" class="d7">Se inserta la tarjeta</text><text x="96" y="140" text-anchor="middle" class="d7">del empleado</text>
  <rect x="184" y="110" width="152" height="40" rx="4" fill="#eef3f8"/><text x="260" y="126" text-anchor="middle" class="d7">Se teclea el PIN y la</text><text x="260" y="140" text-anchor="middle" class="d7">tarjeta firma un reto</text>
  <rect x="348" y="110" width="152" height="40" rx="4" fill="#eef3f8"/><text x="424" y="126" text-anchor="middle" class="d7">Rol tramitador: solo</text><text x="424" y="140" text-anchor="middle" class="d7">su distrito</text>
  <rect x="512" y="110" width="148" height="40" rx="4" fill="#eef3f8"/><text x="586" y="126" text-anchor="middle" class="d7">Queda registrado el</text><text x="586" y="140" text-anchor="middle" class="d7">expediente y la hora</text>
  <text x="20" y="172" class="k7">MEDIDA DEL ENS QUE LO EXIGE</text>
  <rect x="20" y="180" width="152" height="30" rx="4" fill="#f5f5f5"/><text x="96" y="199" text-anchor="middle" class="d7">op.acc.1</text>
  <rect x="184" y="180" width="152" height="30" rx="4" fill="#f5f5f5"/><text x="260" y="199" text-anchor="middle" class="d7">op.acc.5 y op.acc.6</text>
  <rect x="348" y="180" width="152" height="30" rx="4" fill="#f5f5f5"/><text x="424" y="199" text-anchor="middle" class="d7">op.acc.2 y op.acc.4</text>
  <rect x="512" y="180" width="148" height="30" rx="4" fill="#f5f5f5"/><text x="586" y="199" text-anchor="middle" class="d7">op.exp.8</text>
  <rect x="20" y="224" width="316" height="52" rx="4" fill="#fdf3e3"/>
  <text x="178" y="242" text-anchor="middle" class="k7">MODELO AAA</text>
  <text x="178" y="258" text-anchor="middle" class="d7">Authentication, Authorization, Accounting</text>
  <text x="178" y="271" text-anchor="middle" class="n7">La identificación es PREVIA y no es una de las tres A</text>
  <rect x="348" y="224" width="312" height="52" rx="4" fill="#fbeaea"/>
  <text x="504" y="242" text-anchor="middle" class="k7">ART. 24.3 DEL ENS</text>
  <text x="504" y="258" text-anchor="middle" class="d7">Cada usuario, identificado de FORMA ÚNICA</text>
  <text x="504" y="271" text-anchor="middle" class="n7">Las cuentas genéricas compartidas destruyen la trazabilidad</text>
  <rect x="20" y="284" width="640" height="20" rx="4" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="298" text-anchor="middle" class="k7">Se identifica UNA vez, se autentica para probarlo, se autoriza CADA vez que se pide un recurso</text>
  <text x="670" y="316" text-anchor="end" class="n7">[Fuente: ENS, arts. 17 y 24, op.acc; RFC2865]</text>
</svg>
```

---

## D8 · Los tres factores y la autenticación multifactor

**Sección**: §3.1.1 — Mecanismos y factores de autenticación
**Propósito**: Fijar los tres factores canónicos con sus ejemplos y aclarar la regla de que multifactor exige categorías distintas, con la escalera de refuerzos de `op.acc.6`.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 344" role="img" aria-label="Los tres factores de autenticación: algo que se sabe, algo que se tiene y algo que se es, con ejemplos y debilidades de cada uno, la regla de que la autenticación multifactor exige factores de categorías distintas, y la escalera de refuerzos R1 a R4 de la medida op punto acc punto 6 del ENS">
  <style>.t8{font:700 11px system-ui,sans-serif;fill:#fff}.s8{font:8.5px system-ui,sans-serif;fill:#fff}.d8{font:9px system-ui,sans-serif;fill:#333}.h8{font:700 13px system-ui,sans-serif;fill:#0055a0}.k8{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n8{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h8">Tres factores · multifactor exige CATEGORÍAS distintas</text>
  <rect x="20" y="36" width="208" height="40" rx="5" fill="#0055a0"/><text x="124" y="54" text-anchor="middle" class="t8">ALGO QUE SE SABE</text><text x="124" y="69" text-anchor="middle" class="s8">conocimiento</text>
  <rect x="236" y="36" width="208" height="40" rx="5" fill="#2d8659"/><text x="340" y="54" text-anchor="middle" class="t8">ALGO QUE SE TIENE</text><text x="340" y="69" text-anchor="middle" class="s8">posesión</text>
  <rect x="452" y="36" width="208" height="40" rx="5" fill="#e89822"/><text x="556" y="54" text-anchor="middle" class="t8">ALGO QUE SE ES</text><text x="556" y="69" text-anchor="middle" class="s8">inherencia</text>
  <rect x="20" y="82" width="208" height="46" rx="4" fill="#eef3f8"/><text x="124" y="99" text-anchor="middle" class="d8">Contraseña, PIN, patrón,</text><text x="124" y="113" text-anchor="middle" class="d8">pregunta de seguridad</text><text x="124" y="125" text-anchor="middle" class="n8">Se olvida, se comparte, se adivina</text>
  <rect x="236" y="82" width="208" height="46" rx="4" fill="#eef3f8"/><text x="340" y="99" text-anchor="middle" class="d8">Tarjeta criptográfica, OTP,</text><text x="340" y="113" text-anchor="middle" class="d8">llave FIDO2, móvil</text><text x="340" y="125" text-anchor="middle" class="n8">Se pierde, se roba, se olvida en casa</text>
  <rect x="452" y="82" width="208" height="46" rx="4" fill="#eef3f8"/><text x="556" y="99" text-anchor="middle" class="d8">Huella, iris, rostro, voz,</text><text x="556" y="113" text-anchor="middle" class="d8">patrón venoso</text><text x="556" y="125" text-anchor="middle" class="n8">No se cambia si se compromete</text>
  <rect x="20" y="138" width="316" height="30" rx="4" fill="#2d8659"/><text x="178" y="157" text-anchor="middle" class="s8">SÍ ES MULTIFACTOR: contraseña + tarjeta · PIN + huella</text>
  <rect x="344" y="138" width="316" height="30" rx="4" fill="#d13c3c"/><text x="502" y="157" text-anchor="middle" class="s8">NO ES MULTIFACTOR: contraseña + PIN (mismo factor)</text>
  <text x="20" y="190" class="k8">ESCALERA DE MECANISMOS ADMITIDOS POR op.acc.6</text>
  <rect x="20" y="198" width="155" height="44" rx="4" fill="#888"/><text x="97" y="216" text-anchor="middle" class="t8">R1 · Contraseña</text><text x="97" y="232" text-anchor="middle" class="s8">solo desde zona controlada</text>
  <rect x="182" y="198" width="155" height="44" rx="4" fill="#0055a0"/><text x="259" y="216" text-anchor="middle" class="t8">R2 · Contraseña + 2F</text><text x="259" y="232" text-anchor="middle" class="s8">dispositivo u OTP</text>
  <rect x="344" y="198" width="155" height="44" rx="4" fill="#2d8659"/><text x="421" y="216" text-anchor="middle" class="t8">R3 · Certificado</text><text x="421" y="232" text-anchor="middle" class="s8">cualificado + PIN o biometría</text>
  <rect x="506" y="198" width="154" height="44" rx="4" fill="#7a2f8a"/><text x="583" y="216" text-anchor="middle" class="t8">R4 · Cert. en tarjeta</text><text x="583" y="232" text-anchor="middle" class="s8">soporte físico + 2F</text>
  <rect x="20" y="252" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="269" text-anchor="middle" class="d8">R8: desde o a través de zona NO controlada, doble factor OBLIGATORIO (R2, R3 o R4) — en todos los niveles</text>
  <rect x="20" y="288" width="316" height="32" rx="4" fill="#eef3f8"/><text x="178" y="303" text-anchor="middle" class="d8">FAR: impostores admitidos — grave</text><text x="178" y="316" text-anchor="middle" class="d8">FRR: legítimos rechazados — molesto</text>
  <rect x="344" y="288" width="316" height="32" rx="4" fill="#eef3f8"/><text x="502" y="303" text-anchor="middle" class="d8">EER: punto donde FAR = FRR</text><text x="502" y="316" text-anchor="middle" class="d8">Cuanto MENOR sea la EER, mejor el sistema</text>
  <text x="670" y="336" text-anchor="end" class="n8">[Fuente: ENS, op.acc.6 y anexo IV; SP800-63]</text>
</svg>
```

---

## D9 · Modelos de control de acceso: DAC, MAC, RBAC y ABAC

**Sección**: §3.1.2 — Modelos de control de acceso lógico
**Propósito**: Comparar los cuatro modelos por quién decide y sobre qué base, e incorporar la dualidad Bell-LaPadula / Biba, que es el par más preguntado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 354" role="img" aria-label="Comparativa de los cuatro modelos de control de acceso lógico: discrecional DAC, obligatorio MAC, basado en roles RBAC y basado en atributos ABAC, indicando quién decide, sobre qué base y su uso típico, más la dualidad entre los modelos formales de Bell-LaPadula para confidencialidad y Biba para integridad">
  <style>.t9{font:700 11px system-ui,sans-serif;fill:#fff}.s9{font:8.5px system-ui,sans-serif;fill:#fff}.d9{font:9px system-ui,sans-serif;fill:#333}.h9{font:700 13px system-ui,sans-serif;fill:#0055a0}.k9{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n9{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h9">Cuatro modelos: quién decide y con qué criterio</text>
  <rect x="20" y="36" width="155" height="36" rx="5" fill="#888"/><text x="97" y="59" text-anchor="middle" class="t9">DAC — discrecional</text>
  <rect x="182" y="36" width="155" height="36" rx="5" fill="#d13c3c"/><text x="259" y="59" text-anchor="middle" class="t9">MAC — obligatorio</text>
  <rect x="344" y="36" width="155" height="36" rx="5" fill="#0055a0"/><text x="421" y="59" text-anchor="middle" class="t9">RBAC — por roles</text>
  <rect x="506" y="36" width="154" height="36" rx="5" fill="#2d8659"/><text x="583" y="59" text-anchor="middle" class="t9">ABAC — por atributos</text>
  <text x="20" y="90" class="k9">QUIÉN DECIDE</text>
  <rect x="20" y="96" width="155" height="28" rx="4" fill="#eef3f8"/><text x="97" y="114" text-anchor="middle" class="d9">El propietario</text>
  <rect x="182" y="96" width="155" height="28" rx="4" fill="#eef3f8"/><text x="259" y="114" text-anchor="middle" class="d9">La política central</text>
  <rect x="344" y="96" width="155" height="28" rx="4" fill="#eef3f8"/><text x="421" y="114" text-anchor="middle" class="d9">La organización</text>
  <rect x="506" y="96" width="154" height="28" rx="4" fill="#eef3f8"/><text x="583" y="114" text-anchor="middle" class="d9">La organización</text>
  <text x="20" y="142" class="k9">BASE DE LA DECISIÓN</text>
  <rect x="20" y="148" width="155" height="28" rx="4" fill="#f5f5f5"/><text x="97" y="166" text-anchor="middle" class="d9">Identidad y ACL</text>
  <rect x="182" y="148" width="155" height="28" rx="4" fill="#f5f5f5"/><text x="259" y="166" text-anchor="middle" class="d9">Etiquetas de seguridad</text>
  <rect x="344" y="148" width="155" height="28" rx="4" fill="#f5f5f5"/><text x="421" y="166" text-anchor="middle" class="d9">Rol del usuario</text>
  <rect x="506" y="148" width="154" height="28" rx="4" fill="#f5f5f5"/><text x="583" y="166" text-anchor="middle" class="d9">Atributos y contexto</text>
  <text x="20" y="194" class="k9">USO TÍPICO Y LÍMITE</text>
  <rect x="20" y="200" width="155" height="42" rx="4" fill="#eef3f8"/><text x="97" y="217" text-anchor="middle" class="d9">Ficheros y ofimática</text><text x="97" y="232" text-anchor="middle" class="n9">No auditable en conjunto</text>
  <rect x="182" y="200" width="155" height="42" rx="4" fill="#eef3f8"/><text x="259" y="217" text-anchor="middle" class="d9">Entornos clasificados</text><text x="259" y="232" text-anchor="middle" class="n9">Rígido y costoso</text>
  <rect x="344" y="200" width="155" height="42" rx="4" fill="#eef3f8"/><text x="421" y="217" text-anchor="middle" class="d9">Aplicaciones de gestión</text><text x="421" y="232" text-anchor="middle" class="n9">Explosión de roles</text>
  <rect x="506" y="200" width="154" height="42" rx="4" fill="#eef3f8"/><text x="583" y="217" text-anchor="middle" class="d9">Nube y federación</text><text x="583" y="232" text-anchor="middle" class="n9">Difícil de depurar</text>
  <rect x="20" y="256" width="316" height="60" rx="4" fill="#0055a0"/>
  <text x="178" y="274" text-anchor="middle" class="t9">BELL-LaPADULA — CONFIDENCIALIDAD</text>
  <text x="178" y="291" text-anchor="middle" class="s9">NO LEER ARRIBA (propiedad simple)</text>
  <text x="178" y="306" text-anchor="middle" class="s9">NO ESCRIBIR ABAJO (propiedad estrella)</text>
  <rect x="344" y="256" width="316" height="60" rx="4" fill="#2d8659"/>
  <text x="502" y="274" text-anchor="middle" class="t9">BIBA — INTEGRIDAD (el dual)</text>
  <text x="502" y="291" text-anchor="middle" class="s9">NO LEER ABAJO</text>
  <text x="502" y="306" text-anchor="middle" class="s9">NO ESCRIBIR ARRIBA</text>
  <text x="340" y="332" text-anchor="middle" class="n9">Matriz de control de acceso: por columnas da ACL (quién accede a este objeto), por filas da capacidades (a qué accede este sujeto)</text>
  <text x="670" y="346" text-anchor="end" class="n9">[Fuente: SP800-162; BLP; ENS, op.acc]</text>
</svg>
```

---
## D10 · Taxonomía del código malicioso y vectores de infección

**Sección**: §4.1.1 — Código malicioso y vectores de infección
**Propósito**: Separar la clasificación por forma de propagación de la clasificación por carga útil, que es donde se produce el error de examen, y enumerar los vectores de entrada con su contramedida.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 365" role="img" aria-label="Taxonomía del código malicioso separando la clasificación por forma de propagación (virus, gusano, troyano y bomba lógica) de la clasificación por carga útil (secuestro de datos, programa espía, puerta trasera, encubridor y red de equipos zombi), más los vectores de infección y su contramedida en el Esquema Nacional de Seguridad">
  <style>.t10{font:700 10.5px system-ui,sans-serif;fill:#fff}.s10{font:8.5px system-ui,sans-serif;fill:#fff}.d10{font:9px system-ui,sans-serif;fill:#333}.h10{font:700 13px system-ui,sans-serif;fill:#0055a0}.k10{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n10{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h10">Dos clasificaciones distintas: cómo se propaga y qué hace</text>
  <text x="20" y="42" class="k10">A · POR SU FORMA DE PROPAGACIÓN</text>
  <rect x="20" y="50" width="155" height="52" rx="5" fill="#0055a0"/><text x="97" y="68" text-anchor="middle" class="t10">VIRUS</text><text x="97" y="83" text-anchor="middle" class="s10">necesita ANFITRIÓN</text><text x="97" y="96" text-anchor="middle" class="s10">y acción del usuario</text>
  <rect x="182" y="50" width="155" height="52" rx="5" fill="#d13c3c"/><text x="259" y="68" text-anchor="middle" class="t10">GUSANO</text><text x="259" y="83" text-anchor="middle" class="s10">se propaga SOLO</text><text x="259" y="96" text-anchor="middle" class="s10">por la red, sin anfitrión</text>
  <rect x="344" y="50" width="155" height="52" rx="5" fill="#e89822"/><text x="421" y="68" text-anchor="middle" class="t10">TROYANO</text><text x="421" y="83" text-anchor="middle" class="s10">se DISFRAZA</text><text x="421" y="96" text-anchor="middle" class="s10">y NO se replica</text>
  <rect x="506" y="50" width="154" height="52" rx="5" fill="#7a2f8a"/><text x="583" y="68" text-anchor="middle" class="t10">BOMBA LÓGICA</text><text x="583" y="83" text-anchor="middle" class="s10">latente hasta que</text><text x="583" y="96" text-anchor="middle" class="s10">se cumple una condición</text>
  <text x="20" y="126" class="k10">B · POR SU CARGA ÚTIL (independiente de lo anterior)</text>
  <rect x="20" y="134" width="126" height="40" rx="4" fill="#eef3f8"/><text x="83" y="150" text-anchor="middle" class="d10">SECUESTRO</text><text x="83" y="164" text-anchor="middle" class="d10">cifra y extorsiona</text>
  <rect x="153" y="134" width="126" height="40" rx="4" fill="#eef3f8"/><text x="216" y="150" text-anchor="middle" class="d10">ESPÍA</text><text x="216" y="164" text-anchor="middle" class="d10">captura teclado y datos</text>
  <rect x="286" y="134" width="126" height="40" rx="4" fill="#eef3f8"/><text x="349" y="150" text-anchor="middle" class="d10">PUERTA TRASERA</text><text x="349" y="164" text-anchor="middle" class="d10">acceso alternativo</text>
  <rect x="419" y="134" width="126" height="40" rx="4" fill="#eef3f8"/><text x="482" y="150" text-anchor="middle" class="d10">ENCUBRIDOR</text><text x="482" y="164" text-anchor="middle" class="d10">se oculta en el núcleo</text>
  <rect x="552" y="134" width="108" height="40" rx="4" fill="#eef3f8"/><text x="606" y="150" text-anchor="middle" class="d10">ZOMBI</text><text x="606" y="164" text-anchor="middle" class="d10">obedece a un C2</text>
  <text x="20" y="198" class="k10">VECTORES DE INFECCIÓN Y CONTRAMEDIDA DEL ENS</text>
  <rect x="20" y="206" width="300" height="26" rx="4" fill="#f5f5f5"/><text x="30" y="223" class="d10">Correo electrónico — adjunto o enlace</text>
  <rect x="328" y="206" width="332" height="26" rx="4" fill="#eef3f8"/><text x="338" y="223" class="d10">mp.s.1 protección del correo + concienciación mp.per.3</text>
  <rect x="20" y="236" width="300" height="26" rx="4" fill="#f5f5f5"/><text x="30" y="253" class="d10">Navegación web y descarga al paso</text>
  <rect x="328" y="236" width="332" height="26" rx="4" fill="#eef3f8"/><text x="338" y="253" class="d10">mp.s.3 protección de la navegación</text>
  <rect x="20" y="266" width="300" height="26" rx="4" fill="#f5f5f5"/><text x="30" y="283" class="d10">Soporte extraíble — memoria USB</text>
  <rect x="328" y="266" width="332" height="26" rx="4" fill="#eef3f8"/><text x="338" y="283" class="d10">op.exp.6.3 analizar todo fichero externo + R5 al conectar</text>
  <rect x="20" y="296" width="300" height="26" rx="4" fill="#f5f5f5"/><text x="30" y="313" class="d10">Servicio expuesto sin parchear</text>
  <rect x="328" y="296" width="332" height="26" rx="4" fill="#eef3f8"/><text x="338" y="313" class="d10">op.exp.4 actualizaciones + op.exp.2 bastionado</text>
  <rect x="20" y="326" width="300" height="26" rx="4" fill="#fbeaea"/><text x="30" y="343" class="d10">Cadena de suministro del software</text>
  <rect x="328" y="326" width="332" height="26" rx="4" fill="#fbeaea"/><text x="338" y="343" class="d10">op.ext.3 · OWASP A03:2025, nueva categoría propia</text>
  <text x="670" y="357" text-anchor="end" class="n10">[Fuente: ENS, op.exp.6; OWASP2025]</text>
</svg>
```

---

## D11 · La cadena de ataque y sus contramedidas por fase

**Sección**: §4.1.2 — Ataques a redes, aplicaciones e ingeniería social
**Propósito**: Presentar el ataque como un proceso por fases y demostrar que cada fase ofrece una oportunidad de corte distinta, que es el fundamento de la defensa en profundidad.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 342" role="img" aria-label="Las siete fases de la cadena de ataque de Lockheed Martin: reconocimiento, preparación del arma, entrega, explotación, instalación, mando y control, y acciones sobre el objetivo, con la contramedida defensiva correspondiente a cada fase y la idea de que cuanto antes se corta la cadena menor es el daño">
  <style>.t11{font:700 10px system-ui,sans-serif;fill:#fff}.s11{font:8.5px system-ui,sans-serif;fill:#fff}.d11{font:9px system-ui,sans-serif;fill:#333}.h11{font:700 13px system-ui,sans-serif;fill:#0055a0}.k11{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n11{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h11">Siete fases · siete oportunidades de cortar</text>
  <rect x="20" y="36" width="88" height="44" rx="4" fill="#0055a0"/><text x="64" y="54" text-anchor="middle" class="t11">1 RECONOC.</text><text x="64" y="69" text-anchor="middle" class="s11">busca objetivo</text>
  <rect x="113" y="36" width="88" height="44" rx="4" fill="#1a6bb0"/><text x="157" y="54" text-anchor="middle" class="t11">2 ARMA</text><text x="157" y="69" text-anchor="middle" class="s11">prepara el envío</text>
  <rect x="206" y="36" width="88" height="44" rx="4" fill="#3781c0"/><text x="250" y="54" text-anchor="middle" class="t11">3 ENTREGA</text><text x="250" y="69" text-anchor="middle" class="s11">correo o web</text>
  <rect x="299" y="36" width="88" height="44" rx="4" fill="#e89822"/><text x="343" y="54" text-anchor="middle" class="t11">4 EXPLOTA</text><text x="343" y="69" text-anchor="middle" class="s11">usa el fallo</text>
  <rect x="392" y="36" width="88" height="44" rx="4" fill="#d95d3c"/><text x="436" y="54" text-anchor="middle" class="t11">5 INSTALA</text><text x="436" y="69" text-anchor="middle" class="s11">persiste</text>
  <rect x="485" y="36" width="88" height="44" rx="4" fill="#d13c3c"/><text x="529" y="54" text-anchor="middle" class="t11">6 MANDO C2</text><text x="529" y="69" text-anchor="middle" class="s11">recibe órdenes</text>
  <rect x="578" y="36" width="82" height="44" rx="4" fill="#8e1c1c"/><text x="619" y="54" text-anchor="middle" class="t11">7 OBJETIVO</text><text x="619" y="69" text-anchor="middle" class="s11">roba o cifra</text>
  <path d="M108 58 L111 58" stroke="#666"/><path d="M201 58 L204 58" stroke="#666"/><path d="M294 58 L297 58" stroke="#666"/><path d="M387 58 L390 58" stroke="#666"/><path d="M480 58 L483 58" stroke="#666"/><path d="M573 58 L576 58" stroke="#666"/>
  <text x="20" y="102" class="k11">CONTRAMEDIDA EN CADA FASE</text>
  <rect x="20" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="64" y="128" text-anchor="middle" class="d11">Reducir la</text><text x="64" y="141" text-anchor="middle" class="d11">superficie</text><text x="64" y="154" text-anchor="middle" class="d11">expuesta</text>
  <rect x="113" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="157" y="128" text-anchor="middle" class="d11">Inteligencia</text><text x="157" y="141" text-anchor="middle" class="d11">de amenazas</text><text x="157" y="154" text-anchor="middle" class="d11">CCN-CERT</text>
  <rect x="206" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="250" y="128" text-anchor="middle" class="d11">Filtrado de</text><text x="250" y="141" text-anchor="middle" class="d11">correo y web</text><text x="250" y="154" text-anchor="middle" class="d11">mp.s.1 y mp.s.3</text>
  <rect x="299" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="343" y="128" text-anchor="middle" class="d11">Parcheo y</text><text x="343" y="141" text-anchor="middle" class="d11">bastionado</text><text x="343" y="154" text-anchor="middle" class="d11">op.exp.4 y 2</text>
  <rect x="392" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="436" y="128" text-anchor="middle" class="d11">Lista blanca</text><text x="436" y="141" text-anchor="middle" class="d11">y EDR</text><text x="436" y="154" text-anchor="middle" class="d11">op.exp.6 R3 y R4</text>
  <rect x="485" y="110" width="88" height="52" rx="4" fill="#eef3f8"/><text x="529" y="128" text-anchor="middle" class="d11">Salida</text><text x="529" y="141" text-anchor="middle" class="d11">controlada</text><text x="529" y="154" text-anchor="middle" class="d11">op.mon.1</text>
  <rect x="578" y="110" width="82" height="52" rx="4" fill="#eef3f8"/><text x="619" y="128" text-anchor="middle" class="d11">Cifrado y</text><text x="619" y="141" text-anchor="middle" class="d11">copias</text><text x="619" y="154" text-anchor="middle" class="d11">mp.info.6</text>
  <rect x="20" y="176" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="193" text-anchor="middle" class="d11">Cuanto ANTES se corta la cadena, menor es el daño: por eso hacen falta controles en TODAS las fases, no solo en el perímetro</text>
  <text x="20" y="224" class="k11">MODELADO DE AMENAZAS · STRIDE Y LA PROPIEDAD QUE VULNERA CADA UNA</text>
  <rect x="20" y="232" width="106" height="44" rx="4" fill="#0055a0"/><text x="73" y="250" text-anchor="middle" class="t11">S · Spoofing</text><text x="73" y="266" text-anchor="middle" class="s11">Autenticidad</text>
  <rect x="132" y="232" width="106" height="44" rx="4" fill="#0055a0"/><text x="185" y="250" text-anchor="middle" class="t11">T · Tampering</text><text x="185" y="266" text-anchor="middle" class="s11">Integridad</text>
  <rect x="244" y="232" width="106" height="44" rx="4" fill="#7a2f8a"/><text x="297" y="250" text-anchor="middle" class="t11">R · Repudiation</text><text x="297" y="266" text-anchor="middle" class="s11">No repudio</text>
  <rect x="356" y="232" width="106" height="44" rx="4" fill="#0055a0"/><text x="409" y="250" text-anchor="middle" class="t11">I · Info. disclos.</text><text x="409" y="266" text-anchor="middle" class="s11">Confidencialidad</text>
  <rect x="468" y="232" width="106" height="44" rx="4" fill="#d13c3c"/><text x="521" y="250" text-anchor="middle" class="t11">D · Denial of s.</text><text x="521" y="266" text-anchor="middle" class="s11">Disponibilidad</text>
  <rect x="580" y="232" width="80" height="44" rx="4" fill="#e89822"/><text x="620" y="250" text-anchor="middle" class="t11">E · Elevation</text><text x="620" y="266" text-anchor="middle" class="s11">Autorización</text>
  <rect x="20" y="288" width="640" height="26" rx="4" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="305" text-anchor="middle" class="k11">Ataque PASIVO: solo observa, difícil de detectar, se PREVIENE cifrando · Ataque ACTIVO: altera, se DETECTA y se responde</text>
  <text x="670" y="334" text-anchor="end" class="n11">[Fuente: KILLCHAIN; ATTACK; STRIDE; ENS, mp.com.3]</text>
</svg>
```

---

## D12 · Ciclo de vulnerabilidades y ventana de exposición

**Sección**: §4.2.1 — Detección, evaluación y gestión de parches
**Propósito**: Mostrar las cinco fases del ciclo y, sobre una línea temporal, dónde empieza y dónde termina realmente la ventana de exposición, que es la trampa habitual del enunciado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Ciclo de gestión de vulnerabilidades en cinco fases y línea temporal que muestra la ventana de exposición desde el descubrimiento de la vulnerabilidad hasta la aplicación efectiva del parche, con los umbrales de la puntuación CVSS y la diferencia entre CVE, CVSS y CWE">
  <style>.t12{font:700 10.5px system-ui,sans-serif;fill:#fff}.s12{font:8.5px system-ui,sans-serif;fill:#fff}.d12{font:9px system-ui,sans-serif;fill:#333}.h12{font:700 13px system-ui,sans-serif;fill:#0055a0}.k12{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n12{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h12">El ciclo y la ventana que hay que cerrar</text>
  <text x="20" y="42" class="k12">CICLO DE GESTIÓN DE VULNERABILIDADES</text>
  <rect x="20" y="50" width="122" height="44" rx="4" fill="#0055a0"/><text x="81" y="68" text-anchor="middle" class="t12">1 · INVENTARIO</text><text x="81" y="84" text-anchor="middle" class="s12">op.exp.1</text>
  <rect x="150" y="50" width="122" height="44" rx="4" fill="#1a6bb0"/><text x="211" y="68" text-anchor="middle" class="t12">2 · DETECCIÓN</text><text x="211" y="84" text-anchor="middle" class="s12">escáner, SCA, SAST</text>
  <rect x="280" y="50" width="122" height="44" rx="4" fill="#e89822"/><text x="341" y="68" text-anchor="middle" class="t12">3 · PRIORIZACIÓN</text><text x="341" y="84" text-anchor="middle" class="s12">op.exp.4.2</text>
  <rect x="410" y="50" width="122" height="44" rx="4" fill="#2d8659"/><text x="471" y="68" text-anchor="middle" class="t12">4 · CORRECCIÓN</text><text x="471" y="84" text-anchor="middle" class="s12">parche o mitigación</text>
  <rect x="540" y="50" width="120" height="44" rx="4" fill="#7a2f8a"/><text x="600" y="68" text-anchor="middle" class="t12">5 · VERIFICACIÓN</text><text x="600" y="84" text-anchor="middle" class="s12">y vuelta a empezar</text>
  <text x="20" y="118" class="k12">LÍNEA TEMPORAL DE UNA VULNERABILIDAD</text>
  <line x1="30" y1="150" x2="650" y2="150" stroke="#333" stroke-width="1.5"/>
  <circle cx="70" cy="150" r="5" fill="#d13c3c"/><text x="70" y="140" text-anchor="middle" class="n12">existe</text>
  <circle cx="210" cy="150" r="5" fill="#d13c3c"/><text x="210" y="140" text-anchor="middle" class="n12">se descubre</text>
  <circle cx="370" cy="150" r="5" fill="#e89822"/><text x="370" y="140" text-anchor="middle" class="n12">parche publicado</text>
  <circle cx="560" cy="150" r="5" fill="#2d8659"/><text x="560" y="140" text-anchor="middle" class="n12">parche aplicado</text>
  <rect x="70" y="158" width="140" height="20" fill="#fbeaea"/><text x="140" y="172" text-anchor="middle" class="d12">latente</text>
  <rect x="210" y="158" width="160" height="20" fill="#d13c3c"/><text x="290" y="172" text-anchor="middle" class="s12">DÍA CERO: sin parche</text>
  <rect x="370" y="158" width="190" height="20" fill="#e89822"/><text x="465" y="172" text-anchor="middle" class="s12">parche disponible pero NO instalado</text>
  <rect x="560" y="158" width="90" height="20" fill="#2d8659"/><text x="605" y="172" text-anchor="middle" class="s12">protegido</text>
  <line x1="210" y1="188" x2="560" y2="188" stroke="#d13c3c" stroke-width="2"/>
  <text x="385" y="202" text-anchor="middle" class="k12">VENTANA DE EXPOSICIÓN — termina al APLICAR el parche, no al publicarlo</text>
  <text x="20" y="228" class="k12">TRES SISTEMAS QUE NO SON LO MISMO</text>
  <rect x="20" y="236" width="206" height="42" rx="4" fill="#eef3f8"/><text x="123" y="253" text-anchor="middle" class="d12">CVE — identificador único</text><text x="123" y="268" text-anchor="middle" class="d12">de la vulnerabilidad concreta</text>
  <rect x="237" y="236" width="206" height="42" rx="4" fill="#eef3f8"/><text x="340" y="253" text-anchor="middle" class="d12">CVSS — puntuación</text><text x="340" y="268" text-anchor="middle" class="d12">de gravedad, de 0,0 a 10,0</text>
  <rect x="454" y="236" width="206" height="42" rx="4" fill="#eef3f8"/><text x="557" y="253" text-anchor="middle" class="d12">CWE — tipo de debilidad</text><text x="557" y="268" text-anchor="middle" class="d12">la categoría, no la instancia</text>
  <rect x="20" y="288" width="152" height="24" rx="3" fill="#2d8659"/><text x="96" y="304" text-anchor="middle" class="s12">0,1 - 3,9 BAJA</text>
  <rect x="178" y="288" width="152" height="24" rx="3" fill="#e89822"/><text x="254" y="304" text-anchor="middle" class="s12">4,0 - 6,9 MEDIA</text>
  <rect x="336" y="288" width="152" height="24" rx="3" fill="#d95d3c"/><text x="412" y="304" text-anchor="middle" class="s12">7,0 - 8,9 ALTA</text>
  <rect x="494" y="288" width="166" height="24" rx="3" fill="#8e1c1c"/><text x="577" y="304" text-anchor="middle" class="s12">9,0 - 10,0 CRÍTICA</text>
  <text x="340" y="330" text-anchor="middle" class="n12">La puntuación CVSS NO es el riesgo: riesgo = gravedad × exposición × criticidad del activo</text>
  <text x="670" y="344" text-anchor="end" class="n12">[Fuente: CVE; CVSS v3.1; CWE; ENS, op.exp.4]</text>
</svg>
```

---

## D13 · Simétrica, asimétrica y funciones hash comparadas

**Sección**: §5.1.1 — Criptografía simétrica, asimétrica y funciones hash
**Propósito**: Comparar las tres primitivas por número de claves, velocidad, propiedades que garantizan y algoritmos, incluida la regla de las claves n(n−1)/2 frente a 2n.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 364" role="img" aria-label="Comparativa entre criptografía simétrica, criptografía asimétrica y funciones hash, indicando número y tipo de claves, velocidad, propiedades de seguridad que garantiza cada una, algoritmos vigentes y algoritmos proscritos, y la fórmula del número de claves necesarias en una red de n participantes">
  <style>.t13{font:700 11px system-ui,sans-serif;fill:#fff}.s13{font:8.5px system-ui,sans-serif;fill:#fff}.d13{font:9px system-ui,sans-serif;fill:#333}.h13{font:700 13px system-ui,sans-serif;fill:#0055a0}.k13{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n13{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h13">Tres primitivas, tres funciones distintas</text>
  <rect x="20" y="34" width="208" height="38" rx="5" fill="#0055a0"/><text x="124" y="52" text-anchor="middle" class="t13">SIMÉTRICA</text><text x="124" y="66" text-anchor="middle" class="s13">una sola clave secreta</text>
  <rect x="236" y="34" width="208" height="38" rx="5" fill="#2d8659"/><text x="340" y="52" text-anchor="middle" class="t13">ASIMÉTRICA</text><text x="340" y="66" text-anchor="middle" class="s13">par pública / privada</text>
  <rect x="452" y="34" width="208" height="38" rx="5" fill="#e89822"/><text x="556" y="52" text-anchor="middle" class="t13">FUNCIÓN HASH</text><text x="556" y="66" text-anchor="middle" class="s13">SIN clave</text>
  <text x="20" y="90" class="k13">VELOCIDAD</text>
  <rect x="20" y="96" width="208" height="24" rx="4" fill="#eef3f8"/><text x="124" y="112" text-anchor="middle" class="d13">Muy rápida — grandes volúmenes</text>
  <rect x="236" y="96" width="208" height="24" rx="4" fill="#fbeaea"/><text x="340" y="112" text-anchor="middle" class="d13">Lenta — solo para poco dato</text>
  <rect x="452" y="96" width="208" height="24" rx="4" fill="#eef3f8"/><text x="556" y="112" text-anchor="middle" class="d13">Muy rápida</text>
  <text x="20" y="138" class="k13">QUÉ GARANTIZA</text>
  <rect x="20" y="144" width="208" height="38" rx="4" fill="#f5f5f5"/><text x="124" y="160" text-anchor="middle" class="d13">Confidencialidad</text><text x="124" y="175" text-anchor="middle" class="n13">NO da no repudio: la clave la saben dos</text>
  <rect x="236" y="144" width="208" height="38" rx="4" fill="#f5f5f5"/><text x="340" y="160" text-anchor="middle" class="d13">Confidencialidad, autenticidad</text><text x="340" y="175" text-anchor="middle" class="n13">ÚNICA que da NO REPUDIO</text>
  <rect x="452" y="144" width="208" height="38" rx="4" fill="#f5f5f5"/><text x="556" y="160" text-anchor="middle" class="d13">Integridad</text><text x="556" y="175" text-anchor="middle" class="n13">NO cifra y NO es reversible</text>
  <text x="20" y="200" class="k13">ALGORITMOS</text>
  <rect x="20" y="206" width="208" height="38" rx="4" fill="#eef3f8"/><text x="124" y="222" text-anchor="middle" class="d13">AES 128/192/256, ChaCha20</text><text x="124" y="237" text-anchor="middle" class="n13">Proscritos: DES (56 bits), RC4</text>
  <rect x="236" y="206" width="208" height="38" rx="4" fill="#eef3f8"/><text x="340" y="222" text-anchor="middle" class="d13">RSA, DH/ECDH, ECDSA, EdDSA</text><text x="340" y="237" text-anchor="middle" class="n13">ECC 256 bits ≈ RSA 3.072 bits</text>
  <rect x="452" y="206" width="208" height="38" rx="4" fill="#eef3f8"/><text x="556" y="222" text-anchor="middle" class="d13">SHA-256/384/512, SHA-3</text><text x="556" y="237" text-anchor="middle" class="n13">Rotos: MD5 y SHA-1</text>
  <rect x="20" y="256" width="316" height="56" rx="4" fill="#0055a0"/>
  <text x="178" y="274" text-anchor="middle" class="t13">NÚMERO DE CLAVES PARA n USUARIOS</text>
  <text x="178" y="291" text-anchor="middle" class="s13">Simétrica: n(n−1)/2 · Asimétrica: 2n</text>
  <text x="178" y="306" text-anchor="middle" class="s13">Con n = 100 → 4.950 frente a 200</text>
  <rect x="344" y="256" width="316" height="56" rx="4" fill="#2d8659"/>
  <text x="502" y="274" text-anchor="middle" class="t13">QUÉ CLAVE SE USA</text>
  <text x="502" y="291" text-anchor="middle" class="s13">Confidencialidad → PÚBLICA del receptor</text>
  <text x="502" y="306" text-anchor="middle" class="s13">Firma → PRIVADA del emisor</text>
  <rect x="20" y="322" width="640" height="22" rx="4" fill="#fdf3e3"/>
  <text x="340" y="337" text-anchor="middle" class="d13">Un HMAC da integridad y autenticidad, pero NO da no repudio: la clave es compartida y cualquiera de los dos pudo generarlo</text>
  <text x="670" y="356" text-anchor="end" class="n13">[Fuente: FIPS197; FIPS180; FIPS186; RFC2104]</text>
</svg>
```

---

## D14 · Cifrado híbrido (sobre digital) y saludo TLS

**Sección**: §5.1.1 — Criptografía simétrica, asimétrica y funciones hash · §5.2.1
**Propósito**: Explicar por qué ningún protocolo real usa una sola familia y trazar los cinco pasos del sobre digital, aterrizándolos en el saludo de TLS y en la confidencialidad directa.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Esquema del cifrado híbrido o sobre digital en cinco pasos, en el que una clave de sesión simétrica aleatoria cifra los datos y la criptografía asimétrica protege esa clave de sesión, y su aplicación en el saludo de TLS con confidencialidad directa mediante Diffie-Hellman efímero">
  <style>.t14{font:700 10.5px system-ui,sans-serif;fill:#fff}.s14{font:8.5px system-ui,sans-serif;fill:#fff}.d14{font:9px system-ui,sans-serif;fill:#333}.h14{font:700 13px system-ui,sans-serif;fill:#0055a0}.k14{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n14{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h14">El sobre digital: lo mejor de cada familia</text>
  <rect x="20" y="36" width="124" height="46" rx="4" fill="#0055a0"/><text x="82" y="54" text-anchor="middle" class="t14">1 · GENERAR</text><text x="82" y="69" text-anchor="middle" class="s14">clave de sesión aleatoria</text>
  <rect x="152" y="36" width="124" height="46" rx="4" fill="#0055a0"/><text x="214" y="54" text-anchor="middle" class="t14">2 · CIFRAR DATOS</text><text x="214" y="69" text-anchor="middle" class="s14">simétrico, rápido</text>
  <rect x="284" y="36" width="124" height="46" rx="4" fill="#2d8659"/><text x="346" y="54" text-anchor="middle" class="t14">3 · CIFRAR CLAVE</text><text x="346" y="69" text-anchor="middle" class="s14">con la pública del receptor</text>
  <rect x="416" y="36" width="124" height="46" rx="4" fill="#e89822"/><text x="478" y="54" text-anchor="middle" class="t14">4 · ENVIAR AMBOS</text><text x="478" y="69" text-anchor="middle" class="s14">criptograma + sobre</text>
  <rect x="548" y="36" width="112" height="46" rx="4" fill="#7a2f8a"/><text x="604" y="54" text-anchor="middle" class="t14">5 · ABRIR</text><text x="604" y="69" text-anchor="middle" class="s14">con la privada propia</text>
  <rect x="20" y="92" width="640" height="24" rx="4" fill="#fdf3e3"/>
  <text x="340" y="108" text-anchor="middle" class="d14">La ASIMÉTRICA negocia la clave · la SIMÉTRICA cifra el tráfico — así funcionan TLS, IPsec, S/MIME y PGP</text>
  <text x="20" y="138" class="k14">EL SALUDO DE TLS, PASO A PASO</text>
  <rect x="20" y="146" width="90" height="132" rx="4" fill="#eef3f8"/><text x="65" y="164" text-anchor="middle" class="k14">CLIENTE</text>
  <rect x="570" y="146" width="90" height="132" rx="4" fill="#eef3f8"/><text x="615" y="164" text-anchor="middle" class="k14">SERVIDOR</text>
  <rect x="118" y="150" width="444" height="24" rx="3" fill="#0055a0"/><text x="340" y="166" text-anchor="middle" class="s14">1 · ClientHello: versiones, suites de cifrado y valor aleatorio</text>
  <rect x="118" y="178" width="444" height="24" rx="3" fill="#2d8659"/><text x="340" y="194" text-anchor="middle" class="s14">2 · ServerHello + CERTIFICADO X.509 del servidor</text>
  <rect x="118" y="206" width="444" height="24" rx="3" fill="#e89822"/><text x="340" y="222" text-anchor="middle" class="s14">3 · El cliente VALIDA: cadena, vigencia, revocación y nombre</text>
  <rect x="118" y="234" width="444" height="24" rx="3" fill="#7a2f8a"/><text x="340" y="250" text-anchor="middle" class="s14">4 · Negociación de la clave de sesión con ECDHE (efímero)</text>
  <rect x="118" y="262" width="444" height="16" rx="3" fill="#333"/><text x="340" y="274" text-anchor="middle" class="s14">5 · Canal cifrado: a partir de aquí, simétrico</text>
  <rect x="20" y="288" width="316" height="44" rx="4" fill="#0055a0"/>
  <text x="178" y="306" text-anchor="middle" class="t14">CONFIDENCIALIDAD DIRECTA (PFS)</text>
  <text x="178" y="323" text-anchor="middle" class="s14">Comprometer la clave privada del servidor NO descifra el tráfico pasado</text>
  <rect x="344" y="288" width="316" height="44" rx="4" fill="#2d8659"/>
  <text x="502" y="306" text-anchor="middle" class="t14">TLS 1.3 · RFC 8446</text>
  <text x="502" y="323" text-anchor="middle" class="s14">1-RTT · sin RSA de intercambio · solo AEAD · PFS obligatoria</text>
  <text x="670" y="344" text-anchor="end" class="n14">[Fuente: RFC8446; RFC5246; DH]</text>
</svg>
```

---

## D15 · IPsec: AH y ESP, modo transporte y modo túnel

**Sección**: §5.2.1 — Protocolos de red y transporte: IPsec, TLS y SSL
**Propósito**: Fijar los dos datos más preguntados —números de protocolo de AH y ESP— y visualizar sobre la estructura del paquete la diferencia entre modo transporte y modo túnel.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Estructura de los paquetes IPsec comparando la cabecera de autenticación AH que es el protocolo IP 51 y no cifra, con la carga de seguridad encapsulada ESP que es el protocolo IP 50 y sí cifra, y comparación del modo transporte que conserva la cabecera IP original con el modo túnel que encapsula el paquete completo con una nueva cabecera">
  <style>.t15{font:700 10px system-ui,sans-serif;fill:#fff}.s15{font:8px system-ui,sans-serif;fill:#fff}.d15{font:9px system-ui,sans-serif;fill:#333}.h15{font:700 13px system-ui,sans-serif;fill:#0055a0}.k15{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n15{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h15">IPsec: dos protocolos y dos modos</text>
  <rect x="20" y="34" width="316" height="52" rx="5" fill="#0055a0"/>
  <text x="178" y="52" text-anchor="middle" class="t15">AH — Authentication Header</text>
  <text x="178" y="68" text-anchor="middle" class="s15">PROTOCOLO IP 51 · integridad y autenticidad</text>
  <text x="178" y="81" text-anchor="middle" class="s15">NO CIFRA · incompatible con NAT</text>
  <rect x="344" y="34" width="316" height="52" rx="5" fill="#2d8659"/>
  <text x="502" y="52" text-anchor="middle" class="t15">ESP — Encapsulating Security Payload</text>
  <text x="502" y="68" text-anchor="middle" class="s15">PROTOCOLO IP 50 · integridad, autenticidad</text>
  <text x="502" y="81" text-anchor="middle" class="s15">Y CONFIDENCIALIDAD (cifra la carga útil)</text>
  <text x="20" y="106" class="k15">PAQUETE ORIGINAL</text>
  <rect x="20" y="112" width="120" height="26" rx="3" fill="#888"/><text x="80" y="129" text-anchor="middle" class="s15">CABECERA IP</text>
  <rect x="144" y="112" width="120" height="26" rx="3" fill="#aaa"/><text x="204" y="129" text-anchor="middle" class="s15">CABECERA TCP</text>
  <rect x="268" y="112" width="200" height="26" rx="3" fill="#ccc"/><text x="368" y="129" text-anchor="middle" style="font:8px system-ui;fill:#333">DATOS</text>
  <text x="20" y="160" class="k15">MODO TRANSPORTE — extremo a extremo, conserva la cabecera IP original</text>
  <rect x="20" y="166" width="120" height="26" rx="3" fill="#888"/><text x="80" y="183" text-anchor="middle" class="s15">CABECERA IP</text>
  <rect x="144" y="166" width="76" height="26" rx="3" fill="#2d8659"/><text x="182" y="183" text-anchor="middle" class="s15">ESP</text>
  <rect x="224" y="166" width="120" height="26" rx="3" fill="#aaa"/><text x="284" y="183" text-anchor="middle" class="s15">CABECERA TCP</text>
  <rect x="348" y="166" width="200" height="26" rx="3" fill="#ccc"/><text x="448" y="183" text-anchor="middle" style="font:8px system-ui;fill:#333">DATOS</text>
  <rect x="552" y="166" width="88" height="26" rx="3" fill="#2d8659"/><text x="596" y="183" text-anchor="middle" class="s15">ESP cola</text>
  <line x1="224" y1="198" x2="548" y2="198" stroke="#d13c3c" stroke-width="2"/>
  <text x="386" y="212" text-anchor="middle" class="n15">cifrado con ESP</text>
  <text x="20" y="236" class="k15">MODO TÚNEL — pasarela a pasarela, encapsula el paquete ENTERO</text>
  <rect x="20" y="242" width="110" height="26" rx="3" fill="#d13c3c"/><text x="75" y="259" text-anchor="middle" class="s15">NUEVA CAB. IP</text>
  <rect x="134" y="242" width="66" height="26" rx="3" fill="#2d8659"/><text x="167" y="259" text-anchor="middle" class="s15">ESP</text>
  <rect x="204" y="242" width="110" height="26" rx="3" fill="#888"/><text x="259" y="259" text-anchor="middle" class="s15">CAB. IP ORIGINAL</text>
  <rect x="318" y="242" width="106" height="26" rx="3" fill="#aaa"/><text x="371" y="259" text-anchor="middle" class="s15">CABECERA TCP</text>
  <rect x="428" y="242" width="140" height="26" rx="3" fill="#ccc"/><text x="498" y="259" text-anchor="middle" style="font:8px system-ui;fill:#333">DATOS</text>
  <rect x="572" y="242" width="68" height="26" rx="3" fill="#2d8659"/><text x="606" y="259" text-anchor="middle" class="s15">ESP cola</text>
  <line x1="204" y1="274" x2="568" y2="274" stroke="#d13c3c" stroke-width="2"/>
  <text x="386" y="288" text-anchor="middle" class="n15">cifrado con ESP — el direccionamiento interno queda oculto</text>
  <rect x="20" y="298" width="316" height="34" rx="4" fill="#eef3f8"/>
  <text x="178" y="313" text-anchor="middle" class="d15">IKEv2 negocia las asociaciones de seguridad</text>
  <text x="178" y="326" text-anchor="middle" class="d15">UDP 500 · UDP 4500 con travesía de NAT</text>
  <rect x="344" y="298" width="316" height="34" rx="4" fill="#fdf3e3"/>
  <text x="502" y="313" text-anchor="middle" class="d15">Cada SA es UNIDIRECCIONAL: una comunicación</text>
  <text x="502" y="326" text-anchor="middle" class="d15">bidireccional necesita DOS · combinación típica: ESP en túnel</text>
  <text x="670" y="344" text-anchor="end" class="n15">[Fuente: RFC4301; RFC4302; RFC4303; RFC7296]</text>
</svg>
```

---

## D16 · PKI: emisión, validación y revocación de certificados

**Sección**: §6.1.1 — Componentes de la PKI, certificados y listas de revocación
**Propósito**: Separar los papeles de AC, AR y AV —que es la confusión más frecuente— y contraponer CRL y OCSP como mecanismos de comprobación del estado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 364" role="img" aria-label="Componentes de una infraestructura de clave pública: autoridad de registro que identifica al solicitante, autoridad de certificación que emite y firma el certificado, autoridad de validación que informa del estado, repositorio y declaración de prácticas de certificación, más la jerarquía de confianza y la comparación entre listas de revocación CRL y el protocolo en línea OCSP">
  <style>.t16{font:700 10.5px system-ui,sans-serif;fill:#fff}.s16{font:8.5px system-ui,sans-serif;fill:#fff}.d16{font:9px system-ui,sans-serif;fill:#333}.h16{font:700 13px system-ui,sans-serif;fill:#0055a0}.k16{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n16{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h16">Quién identifica, quién emite y quién responde</text>
  <rect x="20" y="36" width="150" height="52" rx="5" fill="#e89822"/><text x="95" y="55" text-anchor="middle" class="t16">SOLICITANTE</text><text x="95" y="70" text-anchor="middle" class="s16">genera su par de claves</text><text x="95" y="83" text-anchor="middle" class="s16">y envía la petición (CSR)</text>
  <rect x="196" y="36" width="150" height="52" rx="5" fill="#2d8659"/><text x="271" y="55" text-anchor="middle" class="t16">AR · REGISTRO</text><text x="271" y="70" text-anchor="middle" class="s16">IDENTIFICA y verifica</text><text x="271" y="83" text-anchor="middle" class="s16">NO emite</text>
  <rect x="372" y="36" width="150" height="52" rx="5" fill="#0055a0"/><text x="447" y="55" text-anchor="middle" class="t16">AC · CERTIFICACIÓN</text><text x="447" y="70" text-anchor="middle" class="s16">EMITE, FIRMA y revoca</text><text x="447" y="83" text-anchor="middle" class="s16">con su clave privada</text>
  <rect x="548" y="36" width="112" height="52" rx="5" fill="#7a2f8a"/><text x="604" y="55" text-anchor="middle" class="t16">AV · VALIDACIÓN</text><text x="604" y="70" text-anchor="middle" class="s16">informa del ESTADO</text><text x="604" y="83" text-anchor="middle" class="s16">ni emite ni identifica</text>
  <path d="M170 62 L192 62" stroke="#666" stroke-width="1.5"/><path d="M346 62 L368 62" stroke="#666" stroke-width="1.5"/><path d="M522 62 L544 62" stroke="#666" stroke-width="1.5"/>
  <text x="20" y="112" class="k16">JERARQUÍA DE CONFIANZA</text>
  <rect x="20" y="120" width="200" height="34" rx="4" fill="#0055a0"/><text x="120" y="135" text-anchor="middle" class="s16">AC RAÍZ — autofirmada</text><text x="120" y="148" text-anchor="middle" class="s16">clave privada FUERA DE LÍNEA en HSM</text>
  <rect x="240" y="120" width="200" height="34" rx="4" fill="#3781c0"/><text x="340" y="135" text-anchor="middle" class="s16">AC SUBORDINADA</text><text x="340" y="148" text-anchor="middle" class="s16">firmada por la raíz, opera a diario</text>
  <rect x="460" y="120" width="200" height="34" rx="4" fill="#eef3f8"/><text x="560" y="135" text-anchor="middle" class="d16">CERTIFICADO FINAL</text><text x="560" y="148" text-anchor="middle" class="d16">del titular o del servidor</text>
  <path d="M220 137 L236 137" stroke="#666" stroke-width="1.5"/><path d="M440 137 L456 137" stroke="#666" stroke-width="1.5"/>
  <rect x="20" y="164" width="640" height="24" rx="4" fill="#fdf3e3"/>
  <text x="340" y="180" text-anchor="middle" class="d16">El certificado contiene la clave PÚBLICA, nunca la privada · es información pública y se puede publicar sin riesgo</text>
  <text x="20" y="210" class="k16">COMPROBACIÓN DEL ESTADO: DOS MECANISMOS</text>
  <rect x="20" y="218" width="316" height="94" rx="4" fill="#eef3f8"/>
  <text x="178" y="236" text-anchor="middle" class="k16">CRL · lista de revocados</text>
  <text x="178" y="254" text-anchor="middle" class="d16">La AC publica periódicamente una lista</text>
  <text x="178" y="268" text-anchor="middle" class="d16">FIRMADA con los números de serie revocados</text>
  <text x="178" y="286" text-anchor="middle" class="n16">+ Funciona sin conexión una vez descargada</text>
  <text x="178" y="300" text-anchor="middle" class="n16">− Latencia y tamaño creciente · CRL delta lo mitiga</text>
  <rect x="344" y="218" width="316" height="94" rx="4" fill="#eef3f8"/>
  <text x="502" y="236" text-anchor="middle" class="k16">OCSP · consulta en línea</text>
  <text x="502" y="254" text-anchor="middle" class="d16">Se pregunta por UN certificado concreto</text>
  <text x="502" y="268" text-anchor="middle" class="d16">Respuesta firmada: good, revoked o unknown</text>
  <text x="502" y="286" text-anchor="middle" class="n16">+ Información fresca y respuesta ligera</text>
  <text x="502" y="300" text-anchor="middle" class="n16">− Depende del respondedor y revela qué se visita</text>
  <rect x="20" y="320" width="640" height="24" rx="4" fill="none" stroke="#2d8659" stroke-width="1.5"/>
  <text x="340" y="336" text-anchor="middle" class="k16">OCSP STAPLING: el propio servidor adjunta su respuesta firmada — quita carga, latencia y problema de privacidad</text>
  <text x="670" y="356" text-anchor="end" class="n16">[Fuente: RFC5280; RFC6960]</text>
</svg>
```

---

## D17 · Firma electrónica: generación y verificación

**Sección**: §6.2.1 — Modalidades de firma electrónica, sellado de tiempo y marco regulatorio
**Propósito**: Trazar los dos procesos simétricos de firma y verificación, y dejar fijado que firmar no cifra y que se firma el resumen, no el documento.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Proceso de generación de una firma electrónica calculando el resumen hash del documento y cifrándolo con la clave privada del firmante, y proceso de verificación descifrando la firma con la clave pública, recalculando el resumen y comparando, con los cinco puntos que hay que comprobar al validar una firma">
  <style>.t17{font:700 10.5px system-ui,sans-serif;fill:#fff}.s17{font:8.5px system-ui,sans-serif;fill:#fff}.d17{font:9px system-ui,sans-serif;fill:#333}.h17{font:700 13px system-ui,sans-serif;fill:#0055a0}.k17{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n17{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h17">Firmar y verificar: dos procesos simétricos</text>
  <text x="20" y="42" class="k17">GENERACIÓN · LO HACE EL FIRMANTE</text>
  <rect x="20" y="50" width="118" height="42" rx="4" fill="#888"/><text x="79" y="68" text-anchor="middle" class="t17">DOCUMENTO</text><text x="79" y="83" text-anchor="middle" class="s17">en claro</text>
  <rect x="152" y="50" width="118" height="42" rx="4" fill="#e89822"/><text x="211" y="68" text-anchor="middle" class="t17">RESUMEN</text><text x="211" y="83" text-anchor="middle" class="s17">SHA-256, tamaño fijo</text>
  <rect x="284" y="50" width="150" height="42" rx="4" fill="#2d8659"/><text x="359" y="68" text-anchor="middle" class="t17">CIFRAR EL RESUMEN</text><text x="359" y="83" text-anchor="middle" class="s17">con la clave PRIVADA</text>
  <rect x="448" y="50" width="212" height="42" rx="4" fill="#0055a0"/><text x="554" y="68" text-anchor="middle" class="t17">DOCUMENTO + FIRMA + CERTIFICADO</text><text x="554" y="83" text-anchor="middle" class="s17">se envía o se archiva</text>
  <path d="M138 71 L148 71" stroke="#666" stroke-width="1.5"/><path d="M270 71 L280 71" stroke="#666" stroke-width="1.5"/><path d="M434 71 L444 71" stroke="#666" stroke-width="1.5"/>
  <text x="20" y="116" class="k17">VERIFICACIÓN · LO HACE QUIEN RECIBE</text>
  <rect x="20" y="124" width="150" height="42" rx="4" fill="#2d8659"/><text x="95" y="142" text-anchor="middle" class="t17">DESCIFRAR LA FIRMA</text><text x="95" y="157" text-anchor="middle" class="s17">con la clave PÚBLICA</text>
  <rect x="184" y="124" width="150" height="42" rx="4" fill="#e89822"/><text x="259" y="142" text-anchor="middle" class="t17">RECALCULAR RESUMEN</text><text x="259" y="157" text-anchor="middle" class="s17">del documento recibido</text>
  <rect x="348" y="124" width="150" height="42" rx="4" fill="#0055a0"/><text x="423" y="142" text-anchor="middle" class="t17">COMPARAR</text><text x="423" y="157" text-anchor="middle" class="s17">los dos resúmenes</text>
  <rect x="512" y="124" width="148" height="42" rx="4" fill="#7a2f8a"/><text x="586" y="142" text-anchor="middle" class="t17">VALIDAR EL CERT.</text><text x="586" y="157" text-anchor="middle" class="s17">cadena y revocación</text>
  <rect x="20" y="176" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="193" text-anchor="middle" class="d17">FIRMAR NO CIFRA: el documento firmado sigue siendo legible · la firma da integridad, autenticidad y no repudio, NO confidencialidad</text>
  <text x="20" y="224" class="k17">LOS CINCO PUNTOS QUE HAY QUE COMPROBAR AL VALIDAR</text>
  <rect x="20" y="232" width="126" height="52" rx="4" fill="#eef3f8"/><text x="83" y="250" text-anchor="middle" class="d17">1 · INTEGRIDAD</text><text x="83" y="265" text-anchor="middle" class="n17">los resúmenes</text><text x="83" y="277" text-anchor="middle" class="n17">coinciden</text>
  <rect x="153" y="232" width="126" height="52" rx="4" fill="#eef3f8"/><text x="216" y="250" text-anchor="middle" class="d17">2 · CADENA</text><text x="216" y="265" text-anchor="middle" class="n17">hasta una AC raíz</text><text x="216" y="277" text-anchor="middle" class="n17">de confianza</text>
  <rect x="286" y="232" width="126" height="52" rx="4" fill="#fdf3e3"/><text x="349" y="250" text-anchor="middle" class="d17">3 · VIGENCIA</text><text x="349" y="265" text-anchor="middle" class="n17">EN EL MOMENTO</text><text x="349" y="277" text-anchor="middle" class="n17">DE LA FIRMA</text>
  <rect x="419" y="232" width="126" height="52" rx="4" fill="#fdf3e3"/><text x="482" y="250" text-anchor="middle" class="d17">4 · REVOCACIÓN</text><text x="482" y="265" text-anchor="middle" class="n17">no revocado</text><text x="482" y="277" text-anchor="middle" class="n17">en ese instante</text>
  <rect x="552" y="232" width="108" height="52" rx="4" fill="#eef3f8"/><text x="606" y="250" text-anchor="middle" class="d17">5 · POLÍTICA</text><text x="606" y="265" text-anchor="middle" class="n17">uso de clave y</text><text x="606" y="277" text-anchor="middle" class="n17">política de firma</text>
  <rect x="20" y="296" width="640" height="34" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="311" text-anchor="middle" class="k17">Sin SELLO DE TIEMPO, el punto 3 no se puede probar años después</text>
  <text x="340" y="325" text-anchor="middle" class="n17">Una firma hecha ANTES de la revocación es válida; una hecha DESPUÉS, no. Validar es demostrarlo dentro de treinta años</text>
  <text x="670" y="344" text-anchor="end" class="n17">[Fuente: EIDAS, arts. 26 y 32; RFC5280; RFC3161]</text>
</svg>
```

---

## D18 · Modalidades eIDAS, formatos y niveles de longevidad

**Sección**: §6.2.1 — Modalidades de firma electrónica, sellado de tiempo y marco regulatorio
**Propósito**: Cerrar el tema con la escalera de las tres modalidades de firma, su correspondencia con los refuerzos de `mp.info.3` del ENS y los formatos con sus niveles de longevidad.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 374" role="img" aria-label="Escalera de las tres modalidades de firma electrónica del Reglamento eIDAS: simple, avanzada y cualificada, con los requisitos de cada una y su efecto jurídico, la correspondencia con los refuerzos R1 a R4 de la medida mp punto info punto 3 del Esquema Nacional de Seguridad, y los formatos CAdES, XAdES y PAdES con sus niveles de longevidad B, T, LT y LTA">
  <style>.t18{font:700 10.5px system-ui,sans-serif;fill:#fff}.s18{font:8.5px system-ui,sans-serif;fill:#fff}.d18{font:9px system-ui,sans-serif;fill:#333}.h18{font:700 13px system-ui,sans-serif;fill:#0055a0}.k18{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n18{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h18">Tres modalidades, un solo efecto equivalente a la manuscrita</text>
  <rect x="20" y="34" width="206" height="76" rx="5" fill="#888"/>
  <text x="123" y="52" text-anchor="middle" class="t18">1 · SIMPLE</text>
  <text x="123" y="70" text-anchor="middle" class="s18">Datos electrónicos que el</text>
  <text x="123" y="83" text-anchor="middle" class="s18">firmante usa para firmar</text>
  <text x="123" y="101" text-anchor="middle" class="s18">No se le niegan efectos por ser electrónica</text>
  <rect x="237" y="34" width="206" height="76" rx="5" fill="#0055a0"/>
  <text x="340" y="52" text-anchor="middle" class="t18">2 · AVANZADA (art. 26)</text>
  <text x="340" y="68" text-anchor="middle" class="s18">Vinculada de forma única · identifica</text>
  <text x="340" y="81" text-anchor="middle" class="s18">al firmante · control exclusivo ·</text>
  <text x="340" y="94" text-anchor="middle" class="s18">detecta cualquier cambio posterior</text>
  <text x="340" y="106" text-anchor="middle" class="s18">Mayor valor probatorio</text>
  <rect x="454" y="34" width="206" height="76" rx="5" fill="#2d8659"/>
  <text x="557" y="52" text-anchor="middle" class="t18">3 · CUALIFICADA</text>
  <text x="557" y="70" text-anchor="middle" class="s18">Avanzada + certificado</text>
  <text x="557" y="83" text-anchor="middle" class="s18">CUALIFICADO + dispositivo QSCD</text>
  <text x="557" y="101" text-anchor="middle" class="s18">EQUIVALE A LA FIRMA MANUSCRITA (art. 25.2)</text>
  <rect x="20" y="118" width="640" height="24" rx="4" fill="#fbeaea"/>
  <text x="340" y="134" text-anchor="middle" class="d18">Certificado cualificado SIN dispositivo cualificado = firma AVANZADA, no cualificada. Es el error más repetido.</text>
  <text x="20" y="164" class="k18">CORRESPONDENCIA CON mp.info.3 DEL ENS (dimensiones I y A)</text>
  <rect x="20" y="172" width="206" height="54" rx="4" fill="#eef3f8"/><text x="123" y="189" text-anchor="middle" class="d18">NIVEL BAJO</text><text x="123" y="205" text-anchor="middle" class="n18">cualquier firma admitida en</text><text x="123" y="218" text-anchor="middle" class="n18">derecho, incluido el CSV</text>
  <rect x="237" y="172" width="206" height="54" rx="4" fill="#fdf3e3"/><text x="340" y="189" text-anchor="middle" class="d18">MEDIO · +R1 +R2 +R3</text><text x="340" y="205" text-anchor="middle" class="n18">certificados cualificados ·</text><text x="340" y="218" text-anchor="middle" class="n18">algoritmos CCN · validación</text>
  <rect x="454" y="172" width="206" height="54" rx="4" fill="#fbeaea"/><text x="557" y="189" text-anchor="middle" class="d18">ALTO · +R4</text><text x="557" y="205" text-anchor="middle" class="n18">además, un segundo factor:</text><text x="557" y="218" text-anchor="middle" class="n18">algo que se sabe o que se es</text>
  <text x="20" y="248" class="k18">FORMATOS Y NIVELES DE LONGEVIDAD</text>
  <rect x="20" y="256" width="150" height="60" rx="4" fill="#0055a0"/><text x="95" y="274" text-anchor="middle" class="t18">CAdES</text><text x="95" y="290" text-anchor="middle" class="s18">cualquier binario</text><text x="95" y="305" text-anchor="middle" class="s18">sobre CMS</text>
  <rect x="184" y="256" width="150" height="60" rx="4" fill="#2d8659"/><text x="259" y="274" text-anchor="middle" class="t18">XAdES</text><text x="259" y="290" text-anchor="middle" class="s18">documentos XML</text><text x="259" y="305" text-anchor="middle" class="s18">Facturae, expediente</text>
  <rect x="348" y="256" width="150" height="60" rx="4" fill="#e89822"/><text x="423" y="274" text-anchor="middle" class="t18">PAdES</text><text x="423" y="290" text-anchor="middle" class="s18">documentos PDF</text><text x="423" y="305" text-anchor="middle" class="s18">firma visible en el visor</text>
  <rect x="512" y="256" width="148" height="60" rx="4" fill="#7a2f8a"/><text x="586" y="274" text-anchor="middle" class="t18">ASiC</text><text x="586" y="290" text-anchor="middle" class="s18">contenedor que agrupa</text><text x="586" y="305" text-anchor="middle" class="s18">datos y firmas</text>
  <rect x="20" y="324" width="152" height="26" rx="3" fill="#eef3f8"/><text x="96" y="341" text-anchor="middle" class="d18">-B básica</text>
  <rect x="178" y="324" width="152" height="26" rx="3" fill="#cfe4f7"/><text x="254" y="341" text-anchor="middle" class="d18">-T + sello de tiempo</text>
  <rect x="336" y="324" width="152" height="26" rx="3" fill="#9fc9ec"/><text x="412" y="341" text-anchor="middle" class="d18">-LT + datos de validación</text>
  <rect x="494" y="324" width="166" height="26" rx="3" fill="#0055a0"/><text x="577" y="341" text-anchor="middle" class="s18">-LTA + sellos de archivo</text>
  <text x="670" y="366" text-anchor="end" class="n18">[Fuente: EIDAS, arts. 25 y 26; ENS, mp.info.3; ETSI319]</text>
</svg>
```
