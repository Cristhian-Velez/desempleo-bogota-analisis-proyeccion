# Investigación con datos públicos de Colombia
Fecha: 15 de octubre de 2026.

## 1. Protestas
Pregunta: ¿qué protestas se documentaron durante los mandatos de Álvaro Uribe y Gustavo Petro, por qué motivos y qué afectaciones a personas se documentaron?
Ampliar el alcance histórico hasta 2002 para incluir a Uribe. Comparar periodos de igual duración además de totales; conservar fuente y metodología. No interpretar manifestaciones durante un gobierno como manifestaciones contra ese gobierno.

Fuentes:
- CINEP, consulta pública 1975–2019: https://cinep.org.co/base-de-datos-de-luchas-sociales/
- CINEP 2001–2005: https://cinep.org.co/luchas/2001-2005/index.html
- CINEP 2006–2010: https://cinep.org.co/base-de-datos-movimientos-sociales-2006-2010/
- Defensoría: https://www.defensoria.gov.co/conflictividad-social
- Informe enero–marzo 2025: https://www.defensoria.gov.co/documents/20123/3146242/Informe%2BPrimer%2BTrimestre%2B%2B2025%2BConflictos%2BSociales%2BManifiestos%2B.pdf/b7408817-c666-ad2b-6fd6-efa261fb7662?t=1745604008832
- ONU-DH 2021: https://www.hchr.org.co/documentos/el-paro-nacional-2021-lecciones-aprendidas-para-el-ejercicio-del-derecho-de-reunion-pacifica-en-colombia/
- CIDH: https://www.oas.org/es/cidh/informes/pdfs/ObservacionesVisita_cidh_Colombia_spA.pdf
- Indepaz: https://indepaz.org.co/victimas-de-violencia-homicida-en-el-marco-del-paro-nacional/
- Temblores: https://www.temblores.org/grita

Estado: fuentes localizadas. No hay aún una base integrada ni un conteo validado. CINEP expone vistas históricas; descarga de registros y cobertura posterior por confirmar. Defensoría registra eventos desde enero de 2022 según su informe: no cubre Uribe. No unir sus totales como una serie homogénea.
Unidad propuesta: evento por municipio y fecha, conservando identificador de jornada nacional. Separar marcha, plantón, bloqueo, huelga y otras modalidades. Registrar motivos múltiples. Distinguir fallecidos, heridos, detenidos y otras afectaciones; no sumar categorías como personas únicas sin deduplicación. Ausencia de registro no equivale a cero. Atribución de responsabilidad solo según la fuente y su estado de verificación.

## 2. Datos Abiertos Colombia
- Catálogo: https://www.datos.gov.co/
- Manual oficial de desarrollador: https://herramientas.datos.gov.co/node/304
- Candidato inicial para practicar API: TRM, identificador 32sa-8pi3.
- Página candidata: https://www.datos.gov.co/d/32sa-8pi3
- Endpoint candidato, pendiente de respuesta validada: https://www.datos.gov.co/resource/32sa-8pi3.json?$limit=5
Usar el botón API del conjunto para confirmar identificador, columnas, límites y paginación. Una muestra de cinco filas no es la descarga completa. TRM permite estudiar tasa de cambio, no concluir por sí sola cómo va toda la economía.

## 3. Datos Abiertos Bogotá
- Catálogo: https://datosabiertos.bogota.gov.co/
- Conjunto candidato: https://datosabiertos.bogota.gov.co/en/dataset/mercado-laboral-bogota
- Consulta CKAN candidata, pendiente de validación: https://datosabiertos.bogota.gov.co/api/3/action/package_search?q=mercado%20laboral&rows=5
Una API de catálogo devuelve metadatos y enlaces: no necesariamente filas del conjunto. Inspeccionar los recursos, formato, fecha, cobertura y disponibilidad de DataStore antes de descargar.

## Fuentes económicas adicionales
- Empleo DANE: https://www.dane.gov.co/index.php/estadisticas-por-tema/mercado-laboral/empleo-y-desempleo
- IPC histórico DANE: https://www.dane.gov.co/index.php/estadisticas-por-tema/precios-y-costos/indice-de-precios-al-consumidor-ipc/ipc-historico
- Pobreza DANE: https://www.dane.gov.co/index.php/estadisticas-por-tema/pobreza-y-condiciones-de-vida/pobreza-monetaria
- Banco de la República: https://suameca.banrep.gov.co/estadisticas-economicas/

## Primera sesión
1. Crear un notebook independiente y carpetas datos_originales, datos_limpios y fuentes.
2. Descargar un informe de Defensoría y revisar definición de evento, periodo, territorio, motivos y metodología. Guardarlo sin cambios.
3. Examinar vistas de CINEP; confirmar si permiten exportar filas o solo muestran agregados. Si no hay exportación, documentar la limitación y preparar solicitud de datos, sin enviarla automáticamente.
4. Probar una muestra de la API nacional y consultar los recursos del conjunto de Bogotá.
5. Registrar URL, entidad, fecha de descarga, periodo, formato y limitaciones.
Entrega de hoy: inventario verificable y primeras muestras/documentos reales. No publicar todavía una clasificación de gobiernos.

## Prueba técnica realizada
El 15/10/2026 respondieron HTTP 200 el endpoint JSON de TRM y la búsqueda del catálogo CKAN de Bogotá. La búsqueda devolvió 9 coincidencias para mercado laboral. Esto confirma acceso, no valida todavía calidad ni cobertura de las filas.

Descarga del PDF de Defensoría T1 2025: falló con HTTP 500. No se incluye como documento descargado. Los JSON son muestras/metadatos, no la base completa de protestas.
