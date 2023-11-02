#Geocodificación y Limpieza de Datos de Accidentes en Barranquilla

Este proyecto tiene como objetivo geocodificar direcciones de accidentes en Barranquilla, Colombia, y realizar una limpieza de datos para su análisis posterior. A continuación, se presenta un resumen de las etapas clave del proceso:

## Paso 1: Geocodificación de Direcciones

Para geocodificar las direcciones de accidentes en Barranquilla, seguimos los siguientes pasos:

1. **Inicialización del Cliente de Google Maps**: Se inicializó el cliente de Google Maps para utilizar su API de geocodificación.

2. **Obtención de Latitud y Longitud**: Creamos una función personalizada que utiliza la API de Google Maps para obtener la latitud y longitud de una dirección. Esto se aplicó a las direcciones únicas del conjunto de datos para evitar costos innecesarios.

3. **Exportación de Resultados**: Los resultados de la geocodificación se exportaron a un archivo CSV, que contiene las direcciones geocodificadas con sus respectivas latitudes y longitudes.

## Paso 2: Limpieza de Datos

En esta etapa, realizamos una limpieza de datos para preparar el conjunto de datos para su análisis. Los principales pasos incluyen:

1. **Manejo de Datos Duplicados**: Identificamos las direcciones duplicadas y las unimos con las únicas. Para las filas duplicadas, se observó que las columnas 'latitud' y 'longitud' eran nulas. Utilizamos una función de agrupación para asignar valores de latitud y longitud a la mayoría de los registros duplicados.

2. **Manejo de Valores Nulos**: Eliminamos las filas con valores nulos en las columnas 'latitud' y 'longitud', y luego aplicamos una función para obtener latitud y longitud en las filas restantes.

3. **Uniformización de Fechas y Horas**: Convertimos las fechas en un formato uniforme utilizando una función personalizada y cambiamos el formato de las horas para que sea reconocido por Pandas.

4. **Unión de Fecha y Hora**: Unimos las columnas 'FECHA_ACCIDENTE' y 'HORA_ACCIDENTE' para obtener la fecha y hora exacta del accidente.

5. **Eliminación de Columnas Innecesarias**: Eliminamos las columnas innecesarias, como 'AÑO_ACCIDENTE', 'MES_ACCIDENTE', 'DIA_ACCIDENTE' y 'HORA_ACCIDENTE', para simplificar el conjunto de datos.

6. **Tratamiento de Valores Faltantes en Heridos y Muertos**: Las columnas 'CANT_HERIDOS_EN_SITIO_ACCIDENTE' y 'CANT_MUERTOS_EN_SITIO_ACCIDENTE' se trataron para convertir los valores en enteros y rellenar los valores nulos con ceros.

7. **Exportación de Datos Limpios**: Finalmente, exportamos el conjunto de datos limpio a un archivo CSV listo para el análisis.

## Paso 3: Creación de Dashboard con Tableau

Utilizamos los datos limpios y geocodificados para crear un dashboard interactivo con Tableau. El dashboard permite visualizar y explorar los accidentes en Barranquilla de manera efectiva, proporcionando información valiosa a los usuarios.

Este conjunto de datos limpio y geocodificado, junto con el dashboard de Tableau, se encuentran disponibles en este repositorio para su análisis y visualización.

---

