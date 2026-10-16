# Análisis de hallazgos de la entrevista (Fase 0)

## 1. Criterios de decisión

| Decisión | Cuándo se aplicó |
|---|---|
| **Aceptado** | Conocimiento de la organización ficticia, coherente con el enunciado (el experto es la fuente de verdad) |
| **Aceptado como supuesto** | Cifras marcadas *(estimación típica)*: sirven para dimensionar, no son datos reales |
| **Contrastado** | Se verificó o corrigió con una fuente externa (norma oficial, material del curso, enunciado) |
| **Descartado** | No se usa en el diseño, con razón explícita |

Principio aplicado: **lo de la organización ficticia lo define el experto; lo de la realidad colombiana (leyes, entes) se contrasta**.

---

## 2. Tabla de hallazgos

**Pregunta** = dónde está en la [conversación](conversacion.md). **Impacto** = vista o artefacto del diseño (V1 Motivación, V2 Capacidades, V3 E2E, V4 Servicios, V5 Dominios, V6 Agregados, V7 Lenguaje ubicuo, V8 Mapa de contextos, V9 Interoperabilidad, V11 Canvas).

### 2.1 Contexto de la organización

| ID | Pregunta | Hallazgo | Decision | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H01 | P1, P2, P6 | Metro Andino es el ente gestor (100 % público): planea, regula y controla. Los buses los operan 3 concesionarios; el metro, la OMVA (contrato de operación); el recaudo, la URA (concesión **hasta el 31-12-2027**); el dinero lo administra la Fiduciaria Cordillera | Aceptado | Hechos de la organización ficticia | V3 actores; V4/V8/V9 externos (operadores, URA, fiducia) | |
| H02 | P3, P5 | 9 áreas con clasificación estratégica / misional / apoyo; **liquidación y distribución es misional** | Aceptado | Clasificación argumentada por el experto | **V2** grupos de nivel 1 | |
| H03 | P4 | Financiación: tarifa ≈70 %, Fondo de Estabilización Tarifaria (FET) ≈27 %; los descuentos de perfiles los pagan la Alcaldía y las universidades **según las validaciones subsidiadas certificadas** | Contrastado | Los fondos de estabilización tienen base en el **art. 33 de la Ley 1753 de 2015**, modificado por la Ley 1955 de 2019 y la Ley 2294 de 2023. Los porcentajes quedan como supuesto | V1 impulsor; V4 servicio "Certificación de validaciones subsidiadas" | |
| H04 | P6, P11 | El dinero siempre está en el patrimonio autónomo: Metro Andino **ordena** pagos, nunca recibe dinero | Aceptado | Principio explícito del negocio | V1 principio; la solución no "mueve dinero" | |

### 2.2 Motivación (V1)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H05 | P7 | **Impulsores**: fin de la concesión URA y decisión de ser dueños del sistema y los datos; acuerdo municipal 2025 (tarifa universitaria); visitantes y meta de pago sin contacto; presión financiera del FET; hallazgo de la Contraloría sobre subsidios | Aceptado | Coherentes con la solicitud del tema | **V1** impulsores |
| H06 | P8 | **Evaluaciones**: 12 % de pagos con tiquete desechable y sin pago bancario; filas de 12–20 min; ~4 % de errores de tarifa en perfiles; perfiles hasta 6 semanas; 1.300 PQRS/mes; conciliación de 12 días; bloqueo hasta 24 h | Aceptado como supuesto | Cifras *(estimación típica)* | **V1** evaluaciones; línea base de indicadores |
| H07 | P9 | **Metas   resultados**: sistema propio el 01-01-2028; 8 % de pagos bancarios; <0,5 % de errores de tarifa; perfiles en 3 días; conciliación en 3 días; −40 % PQRS; 45 % de recarga digital | Aceptado | Medibles y con plazo (distinción meta/resultado del curso) | **V1** metas y resultados; V11 métricas |
| H08 | P10 | 15 grupos de **interesados** (Alcaldía, Secretaría de Movilidad, Junta, operadores, URA, fiducia, usuarios, visitantes, beneficiarios, certificadores, adquirente, entes de control…) | Aceptado | Completo | **V1** interesados |
| H09 | P11 | 9 **principios**: tarifa justa; nunca cobrar dos veces; el saldo es del usuario; trazabilidad total; dinero solo en el patrimonio autónomo; inclusión; la operación no se detiene; neutralidad entre operadores; mínimo dato personal | Aceptado | Varios se vuelven invariantes (H20) | **V1** principios; Fase 4 |
| H10 | P12 | **Requerimientos**: 100 % de transacciones sin pérdida ni duplicados; reglas parametrizables; ciclo completo de VAMOS; pago sin contacto; perfiles con vigencias; consolidado; historial para PQRS; reportes; bloqueo ≤1 h; 24/7; 40.000 validaciones en hora pico | Aceptado | Cada uno debe quedar realizado por un servicio o componente | **V1**; **V10** trazabilidad |
| H11 | P13, P14 | **Restricciones**. El experto **corrigió nuestra hipótesis**: la más dura es el **plazo del 01-01-2028**, no los dispositivos. Además, aunque los validadores están fuera de alcance, **deben recibir** listas de bloqueo, tarifas y perfiles. Otras: 2.600 validadores existentes con protocolo del fabricante; contratos que definen "pasajero pago"; tarifas por decreto | Contrastado | Contra el enunciado ("el software recibe las transacciones… pero no los gestiona"): la solución no **gestiona** dispositivos, pero sí les **publica** listas y parámetros. Es coherente | **V1** restricciones; **V4/V9** integración con validadores en ambas direcciones | |

### 2.3 Capacidades (  V2)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H12 | P15, P18, P53.2 | Mapa completo: 9 áreas, 29 capacidades E/M/A, **9 impactadas** por la solución (medios de pago, tarifas, beneficiarios, recargas, consolidación, certificación de subsidios, control de fraude, reportes, conciliación) | Aceptado | Sigue el formato del curso : todo el negocio, no solo la app | **V2** completo | |
| H13 | P18 | **Separar gestión tarifaria de gestión de beneficiarios y perfiles** ("la tarifa cambia una vez al año, el perfil todos los días") | Contrastado | Es el criterio del curso para separar servicios | **V2** dos capacidades; **V5** dos subdominios | |
| H14 | P18 | Límites: la solución entrega la **base** de liquidación (liquidar y ordenar a la fiducia lo hace Financiera); las PQRS se gestionan en Servicio al Usuario | Aceptado | Define lo que la solución "no debe administrar" (P2 de SOA) | **V4** exclusiones; V8 relaciones con Financiera y PQRS | |

### 2.4 Proceso E2E (  V3, V4)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H15 | P19, P20, P24 | **Cadena de valor** (5 etapas: acceder al medio de pago   cargar valor   viajar   consolidar y conciliar   liquidar y distribuir) y **E2E corregido** de 11 pasos: gestionar medio y perfil   recargar   validar   recibir y verificar   debitar o cobrar   depurar y cerrar el día   consolidar   conciliar   liquidar   distribuir   certificar subsidios | Contrastado | Reemplaza nuestra hipótesis de 7 pasos: tarifa y perfil se determinan **al validar**; faltaban recepción diferida, depuración, cierre y certificación | **V3**; capa 1 de **V4** | |
| H16 | P21 | VAMOS = **prepago**, descuento al validar. Bancaria = **pospago**, cobro diferido y agregado por día, siempre tarifa plena. Hoy el saldo vive **en el chip** y el negocio quiere usar las recargas de inmediato | Aceptado | Dos flujos distintos; abre la decisión DP1 (dónde vive el saldo) | V3 rama alternativa; Fase 4 agregados de cuenta | |
| H17 | P23 | Transacciones en línea (metro, BRT, ~70 % de alimentadores, recargas, bloqueos) y por lotes (resto de alimentadores, equipos sin conexión hasta 7 días). **Cierre provisional en D+1, definitivo en D+3**; lo tardío se imputa al día en que ocurrió | Aceptado | Define estilo síncrono/asíncrono (P4 de SOA) | **V9** estilos; Fase 4 "Día operativo" | |
| H18 | P52 | En BRT y metro se valida en la estación, no en el bus: se consolida por **estación y troncal**; "ruta" aplica solo a alimentadores | Aceptado | Precisa el enunciado ("modo, ruta y operador") | **V7** "Ruta" vs. "Troncal"; requisito del consolidado | |
| H19 | P26 | **Dueños de datos**: tarjetas, saldos y perfiles = Gerencia de Recaudo; valor de la tarifa = alcalde; reglas de aplicación = Metro Andino con **doble control** (analista registra, Gerente aprueba); liquidación = Financiera | Aceptado | Responde las preguntas SOA de responsabilidad de datos y reglas, que marcan los límites de los contextos | **V4/V5/V8** límites; Fase 4 invariante de doble control | |

### 2.5 Reglas y excepciones (  Fase 4, V11)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H20 | P28, P53.4 | **Reglas que siempre se cumplen**: un solo cobro por validación; tarjeta bloqueada no valida; sin saldo no valida (salvo un viaje a crédito); tarifa del perfil vigente; transbordo con condiciones; nada se borra, se ajusta; imputación al día operativo | Aceptado | Son **invariantes** del curso  | **Fase 4** invariantes; V11 decisiones de negocio | |
| H21 | P22, P29, P53.4 | **Políticas parametrizables**: valor de la tarifa (decreto anual), descuentos por perfil, cupos mensuales, transbordo (90 min, máximo 3 tramos, cargo en el tercero, regla antirretorno), montos de recarga, viaje a crédito | Aceptado | Son **políticas** del curso; sustentan el requerimiento "cambiar reglas sin desarrollos" | **Fase 4** agregado "Esquema tarifario" con vigencias | |
| H22 | P27, P30 | **Perfiles**: escolar (Secretaría de Educación, SIMAT), universitario (listado de cada universidad), adulto mayor (documento), movilidad reducida (certificado); vigencias y cupos; perfil vencido o cupo agotado   tarifa plena | Aceptado | Hechos de la organización ficticia; normas en H29 | **Fase 4** agregado "Beneficio"; **V9** integración con certificadores | |
| H23 | P32 | **Pago bancario**: lista de denegación, cobro agregado por día, rechazo   **deuda de viaje**, 3 reintentos en 10 días, riesgo máximo de 1 día por tarjeta | Contrastado | El experto lo presenta como práctica común del pago abierto y "por negociar con el adquirente": se acepta el modelo; los valores quedan como supuesto | **Fase 4** agregado de cuenta bancaria; **V9** adquirente | |
| H24 | P34–P36 | **Excepciones con compensación**: ajuste por cobro sin paso, reimputación de un bus asignado a ruta errónea, estimación de transacciones perdidas, contingencia sin cobro, traslado de saldo, deuda de viaje, suspensión por fraude, devolución en 15 días hábiles | Aceptado | Cumplen la recomendación del curso de diseñar **compensaciones**  | **Fase 4** comandos de compensación y eventos de rechazo | |

### 2.6 Indicadores (V1, V11)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H25 | P37, P38 | 17 indicadores con valor actual y meta; varios **no se pueden medir hoy** (errores de tarifa, uso del cupo, saldo flotante, propagación de bloqueos) | Aceptado como supuesto | Valores estimados; los "no medibles" son requisitos implícitos de datos | **V1** resultados; **V11** métricas |
| H26 | P38 | Evasión (9 / 5 / 2 %) medida por Operaciones con conteos manuales | **Descartado** (del alcance) | Controlar la evasión es capacidad de Operaciones; la solución solo entrega datos de validaciones | V2 marca "depende"; no es servicio en V4 |

### 2.7 Normatividad ( V1, integraciones con reguladores)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H27 | P26, P39 | Datos personales: Ley 1581 de 2012; datos **sensibles** (discapacidad) y de **menores** (escolares). El experto duda si deben registrar sus bases | Contrastado | Confirmado. El **Decreto 090 de 2018** obliga a inscribir las bases en el Registro Nacional de Bases de Datos de la SIC a las **personas jurídicas públicas**  Metro Andino **sí está obligada** | **V1** restricción; **V4** integración "Reporte a la SIC" | |
| H28 | P41 | **PCI DSS** ("verificar la versión") y decisión de **no almacenar el número completo** de la tarjeta | Contrastado | **PCI DSS v4.0.1** es la única versión activa desde el **31-12-2024**. La tokenización por el adquirente reduce el alcance de la certificación | **V1** restricción; Fase 4: la tarjeta bancaria se identifica por **token** | |
| H29 | P30, P39 | Adulto mayor desde **62 años** "por decisión local" y certificación de discapacidad "según resolución del Ministerio de Salud (verificar)" | Contrastado | La **Ley 1276 de 2009 (art. 7)** define adulto mayor desde los **60 años**: la edad se modela como **parámetro** del perfil y se registra el riesgo de tutela. La resolución de discapacidad vigente es la **Resolución 1197 de 2024**, que derogó la 1239 de 2022 | Fase 4 parámetro "Edad mínima"; **V1** restricción; **V9** integración con el registro de discapacidad | |
| H30 | P39, P44 | Integración con la DIAN por el **documento equivalente electrónico** de tiquetes | Contrastado **Descartado** | Según doctrina DIAN sobre la **Resolución 000165 de 2023**, las empresas de transporte urbano están **exceptuadas** de expedir factura. Se retira la integración del diseño y queda como supuesto | Se **retira** el externo DIAN de V4/V9 | |

### 2.8 Interoperabilidad y vocabulario (V4, V7, V8, V9)

| ID | Pregunta | Hallazgo | Decisión | Contraste / razón | Impacto |
|---|---|---|---|---|---|
| H31 | P45–P48 | **Tabla de 24 interoperabilidades** (se usan 23: se retira la DIAN, H30) con información, dirección, frecuencia y **quién define el formato**: Metro Andino impone a operadores, red de venta y universidades; se **adapta** al adquirente, la fiducia, el ERP, el SIMAT y los entes de control. Mayor riesgo: validadores, adquirente, fiducia y migración de la URA | Aceptado | Cubre los 5 tipos que pide el enunciado (procesos internos, legados, proveedores, reguladores, dispositivos). "Quién impone el formato" es la heurística del curso para elegir patrón: si nos adaptamos  **ACL o conformista**; si imponemos  **servicio abierto + lenguaje publicado** | **Tabla de externos** para V4, V8, V9 y V11 |
| H32 | P50, P51 | **11 términos homónimos** (viaje, validación, transbordo, tarjeta, usuario, operador, tarifa, recaudo, liquidación, saldo, perfil). El experto **corrigió** su propia cifra: los 850 millones diarios son **ingreso tarifario por consumo**, no dinero recibido ("recaudo de caja") | Aceptado | Es justo lo que exige el enunciado: "un mismo término con significados distintos en dos contextos debe quedar explícito" | **V7** una fila por significado; nombres de todas las vistas |

---

## 3. Hipótesis iniciales frente a la entrevista

| Hipótesis del equipo | Resultado | Hallazgo |
|---|---|---|
| Restricción más dura: no gestionar dispositivos | **Corregida**: es el plazo de 2028; los validadores sí reciben listas | H11 |
| 6 capacidades impactadas | **Ampliada a 9**, con tarifa y perfiles separados | H12, H13 |
| E2E de 7 pasos | **Corregida**: 11 pasos | H15 |
| Consolidar por modo, ruta y operador | **Precisada**: estación y troncal en BRT y metro | H18 |
| Reglas de saldo, perfil, bloqueo y transbordo | Confirmada con precisiones | H20, H21 |

## 4. Decisiones de diseño que abre la entrevista

| ID | Decisión | Origen | Propuesta |
|---|---|---|---|
| DP1 | ¿Dónde vive el saldo? | H16 | En una **cuenta del sistema central** (la tarjeta solo identifica): permite recarga inmediata, bloqueo en ≤1 h y traslado de saldo |
| DP2 | ¿Quién envía listas y parámetros a los validadores? | H11 | **La solución**, con formato propio hacia el nuevo proveedor y una capa anticorrupción para los 2.600 equipos existentes |
| DP3 | ¿La liquidación va dentro de la solución? | H14 | **No**: la solución entrega la base y Financiera liquida |
| DP4 | ¿Cómo se identifica una tarjeta bancaria? | H28 | Por **token** del adquirente, nunca por su número |

## 5. Supuestos abiertos

| ID | Supuesto | Cómo se validaría |
|---|---|---|
| S01 | Las cifras *(estimación típica)* son representativas (organización ficticia) | Se declaran como supuestos; no cambian la estructura |
| S02 | Reglas exactas del adquirente (riesgo de 1 día, reintentos) | Contrato con el adquirente |
| S03 | No hay obligación de documento equivalente ante la DIAN | Concepto de la DIAN para el SIT |
| S04 | Edad mínima de adulto mayor 62 (local) frente a 60 (ley) | Jurídica / Concejo |
| S05 | Alcance de la cláusula de reversión de datos de la URA | Jurídica |

## 6. Fuentes de contraste

- Ley 1276 de 2009, art. 7: [Función Pública](https://www.funcionpublica.gov.co/eva/gestornormativo/norma_pdf.php?i=34495)
- Resolución 1239 de 2022 derogada por la Resolución 1197 de 2024: [Normograma Supersalud](https://normograma.supersalud.gov.co/compilacion/docs/resolucion_minsaludps_1239_2022.htm)
- Decreto 090 de 2018 (Registro Nacional de Bases de Datos): [Función Pública](https://www.funcionpublica.gov.co/eva/gestornormativo/norma_pdf.php?i=85039)
- Ley 1753 de 2015, art. 33 (modificado): [Decreto de Cali 0074 de 2024 que lo transcribe](https://normagrama.cali.gov.co/compilacion/docs/pdf/d_alcacali_0074_2024.pdf)
- Resolución DIAN 000165 de 2023 y excepción del transporte urbano: [Concepto DIAN 000426 de 2024 (PwC)](https://legalytributarioenlinea.co.pwc.com/Repositorio%20PwC/PDF/Doctrina/DIAN/Conceptos/2024/CON-000426-24.pdf)
- PCI DSS v4.0.1: [Cloud Security Alliance](https://cloudsecurityalliance.org/articles/preparing-for-the-end-pci-4-0-retirement-in-december-2024)


