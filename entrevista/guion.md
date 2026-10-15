# Guion de la entrevista - Tema 4: Recaudo del SIT (Fase 0)

- Uso: se pega **después** de la [instrucción de rol](instruccion-rol.md), cuando el experto se haya presentado.
- Tipos de pregunta: **[A]** abierta · **[P]** profundización · **[V]** validación. Las preguntas [V] contienen las hipótesis iniciales del equipo para que el experto las confirme, corrija o descarte.
- La columna "Alimenta" del encabezado de cada bloque indica qué vista o artefacto se construye con las respuestas.
- Hay 4 pausas: tras los bloques 3, 6 y 9 el experto se detiene; escribir `continúa` para seguir.

| Bloque | Tema exigido por el enunciado | Alimenta |
|---|---|---|
| 1 | Contexto de la organización | V2, V1 |
| 2 | Motivación estratégica | V1 |
| 3 | Capacidades del negocio | V2 |
| 4 | Proceso E2E (y cadena de valor) | V3, V4 |
| 5 | Actores | V3, V4 |
| 6 | Reglas de negocio | Fase 4, V11 |
| 7 | Excepciones | Fase 4 (eventos de rechazo, compensaciones) |
| 8 | Indicadores | V1 (resultados), V11 (métricas) |
| 9 | Normatividad | V1, capa ACL |
| 10 | Sistemas y procesos con los que interactúa (interoperabilidad) | Capa ACL de V4, V8, V9, V11 |
| 11 | Vocabulario (lenguaje ubicuo) | V7 |
| 12 | Cierre y resumen estructurado | Todas |

```text
GUION DE LA ENTREVISTA — RECAUDO DEL SISTEMA INTEGRADO DE TRANSPORTE

Somos el equipo de arquitectura. Responde cada pregunta numerada como "P<n>." siguiendo tu rol.
Etiquetas: [A] abierta, [P] profundización, [V] validación (en las [V] te presentamos lo que creemos entender:
confírmalo, corrígelo o descártalo explicando por qué).
Responde los bloques 1 a 3 y DETENTE. Cuando escribamos "continúa", responde los bloques 4 a 6 y detente;
luego 7 a 9 y detente; luego 10 a 12.

══════════ BLOQUE 1. CONTEXTO DE LA ORGANIZACIÓN ══════════
P1 [A] Preséntenos Metro Andino: naturaleza jurídica, misión, y el SIT en cifras (rutas y flota por modo,
       estaciones, pasajeros/día, recaudo diario aproximado).
P2 [A] ¿Cómo está estructurado el SIT? ¿Quién opera cada modo (alimentadores, articulados, metro), quién opera
       el recaudo, quién administra y distribuye los recursos (p. ej. una fiducia)? ¿Qué relación contractual
       existe entre ellos?
P3 [A] Describa las áreas o gerencias de Metro Andino y qué hace cada una.
P4 [P] ¿Cómo se financia el sistema? ¿Qué parte proviene de la tarifa al usuario y qué parte de subsidios,
       fondos de estabilización u otras fuentes? ¿Quién paga la diferencia de las tarifas especiales?
P5 [P] De esas áreas y actividades, ¿cuáles considera estratégicas, cuáles misionales y cuáles de apoyo? ¿Por qué?
P6 [V] Entendemos que el ente gestor planifica, regula y controla; que operadores privados prestan el transporte
       por concesión; y que el recaudo y el manejo del dinero pueden estar concesionados o fiduciados.
       ¿Es así en Metro Andino?

══════════ BLOQUE 2. MOTIVACIÓN ESTRATÉGICA ══════════
P7  [A] ¿Por qué necesitan un nuevo software de recaudo AHORA? ¿Qué cambió dentro y fuera de la organización?
        (impulsores)
P8  [P] ¿Cómo está el recaudo hoy? Denos evidencia: problemas, cifras, quejas, errores en tarifas especiales,
        filas en taquillas, % de pasajeros con tarjeta, evasión, demoras en conciliación. (evaluaciones)
P9  [A] ¿Qué metas tiene la organización para el recaudo en los próximos 1 a 3 años? Para cada meta, ¿qué
        resultado medible indicaría que se logró y en qué plazo? (metas y resultados)
P10 [A] ¿Quiénes son los interesados y qué le importa a cada uno? (alcaldía, autoridad de transporte, junta
        directiva, operadores de transporte, operador de recaudo, fiducia, usuarios residentes, visitantes,
        beneficiarios de tarifas especiales, entidades financieras, órganos de control, otros)
P11 [P] ¿Qué principios guían el recaudo y que la organización nunca negociaría? (p. ej. tarifa justa,
        inclusión, transparencia en el manejo del dinero, no cobrar dos veces) (principios)
P12 [P] ¿Qué debe cumplir sí o sí la solución para que el negocio la acepte? (requerimientos)
P13 [P] ¿Qué limita la solución: normas, presupuesto, contratos de concesión vigentes, equipos validadores
        existentes, plazos políticos? (restricciones)
P14 [V] ¿Es correcto que lo prioritario es cobrar a cada usuario la tarifa que le corresponde (incluidos
        transbordos y perfiles) y habilitar el pago con tarjetas bancarias para visitantes, y que la restricción
        más dura es que la solución no gestiona validadores ni dispositivos, solo recibe sus transacciones?

══════════ BLOQUE 3. CAPACIDADES DEL NEGOCIO ══════════
P15 [A] Más allá del recaudo, ¿qué sabe hacer la organización? Enumere las capacidades por área (por ejemplo:
        planeación de rutas, programación de flota, control de la operación, gestión de contratos con operadores,
        atención al usuario, comunicaciones, gestión financiera, jurídica, TI, talento humano, infraestructura).
P16 [P] ¿En cuáles de esas capacidades impacta directamente el recaudo y cuáles dependen de su información?
P17 [P] ¿Qué recursos clave sostienen el recaudo? (personas, conocimiento, red de recarga, contratos,
        infraestructura, datos)
P18 [V] ¿Valida que las capacidades impactadas por la solución son: gestión de medios de pago, gestión tarifaria
        y de perfiles, validación y cobro de viajes, consolidación y distribución de ingresos, conciliación
        financiera y atención al usuario? ¿Falta o sobra alguna?

── PAUSA: detente aquí y espera "continúa" ──

══════════ BLOQUE 4. CADENA DE VALOR Y PROCESO E2E ══════════
P19 [A] Describa la cadena de valor desde que una persona decide viajar hasta que el operador de transporte
        recibe el dinero que le corresponde.
P20 [A] Describa el proceso de recaudo de punta a punta: qué evento lo inicia, cada paso, quién lo ejecuta, qué
        información usa y produce, y qué evento lo cierra.
P21 [P] ¿Cómo cambia el proceso según el medio de pago: tarjeta VAMOS frente a débito/crédito sin contacto?
P22 [P] ¿Cómo funciona la integración entre modos? Ventana de tiempo del transbordo, combinaciones permitidas,
        cuánto se cobra en el segundo y tercer tramo, si aplica igual a tarjetas bancarias y a perfiles especiales.
P23 [P] ¿Qué pasos ocurren en línea y cuáles por lotes? (p. ej. validadores sin conectividad, cierre diario,
        liquidación, distribución a operadores)
P24 [V] Resumimos el proceso así: Adquirir o recargar el medio de pago → Validar el viaje → Determinar perfil y
        tarifa (incluido transbordo) → Debitar el saldo o autorizar el pago bancario → Registrar la transacción
        → Consolidar por modo, ruta y operador → Conciliar y distribuir ingresos. ¿Es correcto? ¿Qué falta,
        sobra o cambia de orden?

══════════ BLOQUE 5. ACTORES Y ROLES ══════════
P25 [A] ¿Qué personas, áreas, empresas y entidades participan en el proceso y qué rol cumple cada una?
P26 [P] ¿Quién es dueño (responsable) de los datos de: tarjetas y saldos, perfiles de usuario, tarifas,
        transacciones de validación y consolidados de recaudo? ¿Quién define e implementa las reglas tarifarias?
P27 [P] ¿Qué área o paso del proceso tiene el conocimiento para certificar que un usuario cumple su perfil
        especial? ¿Quién lo verifica y quién lo aprueba?

══════════ BLOQUE 6. REGLAS DE NEGOCIO ══════════
P28 [A] ¿Qué reglas se deben cumplir siempre al validar y cobrar un viaje?
P29 [P] Tarifas: ¿cómo se fijan, quién las aprueba, cada cuánto cambian, varían por modo, horario o distancia?
P30 [P] Perfiles especiales (escolar, universitario, adulto mayor, movilidad reducida): requisitos, documentos,
        vigencia, renovación, límite de viajes o de subsidio, y qué pasa cuando el perfil vence.
P31 [P] Tarjeta VAMOS: emisión (personalizada o anónima) y costo, saldo mínimo y máximo, viaje a crédito o saldo
        negativo, canales y límites de recarga, consulta de saldo, bloqueo por pérdida y traslado del saldo.
P32 [P] Tarjetas bancarias: ¿qué tarifa pagan los visitantes?, ¿tienen transbordo?, ¿la autorización es en
        línea o diferida?, ¿qué pasa si el banco rechaza el cobro después de que la persona ya viajó?
P33 [V] ¿Es correcto que: no se puede validar con saldo insuficiente (salvo un viaje de emergencia, si existe);
        un perfil vencido paga tarifa plena; una tarjeta bloqueada no puede validar; y un transbordo solo aplica
        dentro de la ventana de tiempo y entre combinaciones de modos permitidas?

── PAUSA: detente aquí y espera "continúa" ──

══════════ BLOQUE 7. EXCEPCIONES ══════════
P34 [A] ¿Cuáles son las situaciones excepcionales más frecuentes en el recaudo? Cuéntenos casos reales.
P35 [P] ¿Qué pasa en cada caso: doble cobro, validación fallida, validador sin conexión, tarjeta perdida con saldo,
        cobro bancario rechazado, fraude o suplantación en perfiles especiales, solicitud de devolución?
P36 [P] ¿Cómo se corrige o se revierte cada uno (ajuste de saldo, reembolso, contracargo), quién lo autoriza y en
        cuánto tiempo?

══════════ BLOQUE 8. INDICADORES ══════════
P37 [A] ¿Qué indicadores miden hoy el recaudo y la operación asociada? ¿Cuáles quisieran medir y no pueden?
P38 [P] Para cada indicador: valor actual aproximado, meta, frecuencia y quién lo revisa (p. ej. recaudo diario,
        participación de tarjetas bancarias, tiempo de conciliación, PQRS de recaudo, evasión, errores de tarifa,
        tiempo promedio de recarga).

══════════ BLOQUE 9. NORMATIVIDAD ══════════
P39 [A] ¿Qué normas aplican al recaudo de un sistema integrado de transporte en Colombia? (transporte masivo,
        tarifas y subsidios, beneficios para adultos mayores, estudiantes y personas con discapacidad, protección
        de datos personales, PQRS, protección al consumidor, pagos con tarjeta). Indique (seguro) o (verificar).
P40 [P] ¿Qué entes vigilan o controlan (autoridad de transporte local, Superintendencia de Transporte, SIC,
        contraloría u otros)? ¿Qué se les reporta, cada cuánto y en qué formato?
P41 [P] ¿Qué exigencias imponen las redes de pago y las entidades financieras (seguridad de datos de tarjeta,
        certificaciones, adquirencia)?
P42 [V] ¿Qué consecuencias tiene incumplir cada una? Confirme cuáles de las normas mencionadas está seguro y
        cuáles debemos verificar en fuente oficial.

── PAUSA: detente aquí y espera "continúa" ──

══════════ BLOQUE 10. INTEROPERABILIDAD (SISTEMAS, PROCESOS Y ENTIDADES CON LOS QUE INTERACTÚA) ══════════
P43 [A] ¿Con qué procesos y áreas internas intercambia información el recaudo?
P44 [A] ¿Con qué sistemas (propios, legados, de terceros) y entidades externas se comunica?
P45 [P] Para cada uno de los siguientes, indique: qué información se intercambia, dirección (hacia el recaudo, desde
        el recaudo o ambas), frecuencia (tiempo real, diaria, mensual), mecanismo actual (manual, archivo, API,
        correo) y quién define el formato:
        (a) validadores y equipos a bordo y en estaciones (transacciones de validación)
        (b) experiencia y servicio al cliente: peticiones, quejas, reclamos y devoluciones
        (c) financiero: registro contable de recaudos e ingresos
        (d) planeación de rutas y de la operación (rutas, modos, operadores, horarios)
        (e) redes de pago y entidades financieras (adquirente, franquicias, bancos)
        (f) entidades que certifican los perfiles especiales (colegios, universidades, registros de adultos
            mayores, certificación de discapacidad)
        (g) autoridad de transporte de la ciudad (tarifas, reportes)
        (h) fiducia y operadores de transporte (distribución de ingresos)
        (i) red de puntos de recarga y canales digitales
        (j) cualquier otro que identifique
P46 [P] ¿Qué problemas tiene hoy cada integración (procesos manuales, retrasos, inconsistencias, duplicidades)?
P47 [P] ¿En cuáles de esas relaciones Metro Andino puede imponer el formato y en cuáles le toca adaptarse al del
        otro? ¿Alguno de esos sistemas es antiguo o difícil de cambiar?
P48 [V] Entréguenos una tabla resumen de todas las interoperabilidades con columnas: externo, tipo (proceso
        interno / sistema legado / proveedor / entidad regulatoria / dispositivo), información, dirección,
        frecuencia, mecanismo, quién define el formato. ¿Falta alguna?

══════════ BLOQUE 11. VOCABULARIO DEL NEGOCIO ══════════
P49 [A] ¿Cuáles son los términos clave del recaudo y cómo los define su organización?
P50 [P] ¿Significan lo mismo para todas las áreas (recaudo, operación, finanzas, atención al usuario) los términos:
        viaje, validación, transbordo, tarjeta, usuario, operador, tarifa, recaudo, liquidación, saldo, perfil?
        Explique cada diferencia con un ejemplo.
P51 [P] ¿Qué palabras se usan como sinónimos pero no lo son, o qué dos palabras se usan para lo mismo?

══════════ BLOQUE 12. CIERRE Y RESUMEN ESTRUCTURADO ══════════
P52 [A] ¿Qué no le preguntamos y deberíamos saber?
P53 [V] Para validar lo conversado, entregue un resumen en tablas, coherente con todas sus respuestas anteriores:
        1. Elementos de motivación: interesados, impulsores, evaluaciones, metas, resultados, principios,
           requerimientos y restricciones (con la pregunta donde surgieron).
        2. Mapa de capacidades por área, clasificando cada capacidad como estratégica, misional o de apoyo, y
           marcando las que impacta la solución.
        3. Cadena de valor y proceso E2E: pasos, actor responsable, evento inicial y final.
        4. Reglas de negocio (las que siempre se cumplen) y políticas que cambian con frecuencia.
        5. Excepciones y cómo se compensan.
        6. Interoperabilidades (tabla de P48, actualizada).
        7. Glosario: término, definición, área o contexto, ejemplo; con los términos homónimos en filas separadas.
        8. Indicadores: nombre, valor actual, meta.
        9. Normas: nombre, qué exige, ente que vigila, certeza (seguro/verificar).
```
