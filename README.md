# Seguridad en Medellín

Taller de datos de Tópicos de Sistemas de Información. Modalidad: **trabajo individual**. Responsable del repositorio: [cameloxd](https://github.com/cameloxd).

El proyecto reúne fuentes oficiales sobre homicidios, hurtos a personas y población de Medellín para estudiar diferencias entre comunas y corregimientos. El periodo de análisis es **enero a noviembre de 2022 y el mismo periodo de 2023**.

## Entrega

- [Respuestas del taller en Word](Respuestas_seguridad_Medellin_individual.docx): seis respuestas justificadas, con referencias a los identificadores de las fuentes.
- [Diccionario de datos en Excel](Diccionario_seguridad_Medellin_individual.xlsx): cuatro fuentes registradas, tres integradas, una descartada, doce campos y la bitácora de búsqueda con IA.
- [Lago de datos en ZIP](Lago_seguridad_Medellin.zip): tres CSV agregados y un README con transformación, procedencia, licencias y huellas SHA-256 de las descargas originales.

Para usar los datos, descarga y extrae el ZIP. Dentro encontrarás la carpeta `lago` con `homicidios_mensuales.csv`, `hurtos_personas_mensuales.csv` y `poblacion_anual.csv`.

## Preguntas del sistema

1. ¿En qué comunas y corregimientos se concentran los homicidios y hurtos a personas registrados?
2. ¿Cómo cambian los registros mensuales entre enero y noviembre de 2022 y el mismo periodo de 2023?
3. ¿Cómo cambia la comparación territorial al expresar los registros por cada 100.000 habitantes?

## Fuentes y periodo

- **F01 Homicidio**, Alcaldía de Medellín y SISC. [Ficha oficial](https://medata.app.medellin.gov.co/node/16761).
- **F02 Hurto a persona**, Alcaldía de Medellín y SISC, con registros de Policía Nacional. [Ficha oficial](https://medata.app.medellin.gov.co/node/16764).
- **F03 Proyecciones de población**, DANE y Departamento Administrativo de Planeación de Medellín. [Página oficial](https://www.medellin.gov.co/es/centro-documental/proyecciones-poblacion-viviendas-y-hogares/). Se usa la versión actualizada el 30 de julio de 2025 y los valores correspondientes a 2022 y 2023.
- **F04 Proyecciones de población Medellín 2020** se registra como descartada porque no coincide con los años de comparación.

Los CSV de delitos descargados llegan hasta noviembre de 2023, aunque sus fichas se modificaron en marzo de 2025. Este proyecto describe un periodo histórico y no presenta cifras de seguridad actuales de 2026. Las descargas se comprobaron el 3 de noviembre de 2026.

## Interpretación de los datos

Los archivos de delitos suman el campo original `cantidad` por año, mes y comuna. Se excluyen coordenadas, fecha y hora exactas y características individuales. Los registros sin comuna se conservan como `SIN_DATO` y no se distribuyen entre territorios. Una combinación sin fila no se rellena automáticamente con cero.

Para comparar tasas, se suman los meses de enero a noviembre por año y territorio y se divide por la población del mismo año, multiplicando por 100.000. Es una tasa acumulada de once meses, no anualizada. Los registros administrativos no estiman los hechos no denunciados ni la percepción de inseguridad. La población residente tampoco mide la población flotante de visitantes.

## Licencias

F01 y F02 declaran [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode). Sus dos CSV agregados se atribuyen a las entidades publicadoras y se comparten bajo esa misma licencia. En la ficha y libro de F03 revisados no se encontró una licencia específica y se registró **no declara**. No se aplica una licencia única a todo el repositorio por analogía.

## Acceso a la entrega

El repositorio es público. El docente y cualquier otra persona pueden consultar y descargar la entrega desde https://github.com/cameloxd/seguridad-medellin sin solicitar acceso.
