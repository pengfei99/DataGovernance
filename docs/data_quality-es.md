# Calidad de los datos

En este documento, explicaré cómo definir la calidad de los datos: ¿atributos, medidas y métricas?

## 1 ¿Qué es la calidad de los datos?

La calidad de los datos es el estado de los datos, que está estrechamente relacionado con su capacidad (o incapacidad) para resolver tareas comerciales.
El estado de los datos puede ser "bueno" o "malo", dependiendo de en qué medida los datos correspondan a los siguientes atributos:

*   Exactitud

*   Auditabilidad

*   Integridad

*   Consistencia

*   Credibilidad

*   Orden

*   Puntualidad

*   Unicidad

*   Pertinencia

*   Interpretabilidad

### 1.1 Precisión

*   Definición: La exactitud se refiere a la exactitud de los datos, es decir, si el valor registrado es conforme con el
    valor real en la realidad, con respecto a su uso previsto.
*   Buen ejemplo: Tiene un usuario llamado "John Doe", y en el registro de la base de datos de CRM también está "John Doe".
*   Mal ejemplo: Tiene un usuario llamado "John Doe", y en el registro de la base de datos de CRM también está "Jane Doe".
*   Métrica de medición: La relación/porcentaje de los datos de error.

### 1.2 Auditabilidad

*   Definición: La auditabilidad indica que si el usuario puede rastrear todas las modificaciones de un conjunto de datos (desde la creación,
    a través de la modificación/transformación, hasta la eliminación).
*   Buen ejemplo: Alguien cambia la fecha de nacimiento del usuario "John Doe", sabemos quién hizo el cambio, cuándo se ha realizado el cambio y qué líneas se cambian.
*   Mal ejemplo: Alguien cambia la fecha de nacimiento del usuario "John Doe", es imposible saber quién lo cambia.
*   Métrica de medición: La relación/porcentaje de los metadatos faltantes que describe el proceso de modificación de datos (incluida la creación y eliminación).

### 1.3 Integridad

*   Definición: La completitud indica si el registro tiene todos los valores requeridos. Tenga en cuenta en algunos casos el null
    el valor tiene sentido y no debe considerarse como datos incompletos. Por ejemplo, alguna estación meteorológica no tiene nieve
    equipos de medición de profundidad, por lo que utilizan null en la columna "snow_depth" para indicar eso. Porque poner "valor 0" es perder el liderazgo.
*   Buen ejemplo: Todas las filas de la columna fecha de nacimiento de la tabla de usuario tienen valor.
*   Mal ejemplo: La fecha de nacimiento del usuario "John Doe" es desconocida, porque la celda es nula.
*   Métrica de medición: El número de datos que faltan.

### 1.4 Consistencia

*   Definición: La coherencia indica si hay contradicciones dentro de su conjunto de datos.
*   Buen ejemplo: Todos los valores de edad del usuario "John Doe" de todas las tablas son los mismos.
*   Mal ejemplo: La edad del usuario "John Doe" en la tabla de marketing es diferente de la tabla de CRM.
*   Métrica de medición: El número de inconsistencias.

### 1.5 Credibilidad

*   Definición: La credibilidad indica la confiabilidad de la fuente, así como su contenido.
*   Buen ejemplo: Sabemos quién es el proveedor de datos y cómo se construyen los datos.
*   Mal ejemplo: No tenemos idea de quién produjo los datos y cómo se construyen los datos.
*   Métrica de medición: la relación/porcentaje de los metadatos que faltan que describe el proveedor de datos y cómo se construyen los datos.

### 1.6 Orden

*   Definición: La orden indica si el conjunto de datos ingerido respeta el formato, la estructura y el esquema requeridos.
*   Buen ejemplo: El gobierno de datos define que la fecha debe respetar la norma ISO 8601. Todos los valores de fecha dentro de los datos ingeridos respetan la norma ISO 8601
*   Mal ejemplo: Los valores de fecha de la base de datos CRM no respetan la norma ISO 8601.
*   Métrica de medición: La relación/porcentaje de los datos que no respeta el formato, la estructura y el esquema definidos.

### 1.7 Puntualidad

*   Definición: La puntualidad indica que el valor registrado está actualizado para la tarea en cuestión.
*   Buen ejemplo: El equipo de marketing quiere enviar un correo a los usuarios en su dirección registrada. La dirección de todos los usuarios es
    actualizado en el momento del envío de correos electrónicos. Todos los usuarios reciben el correo.
*   Mal ejemplo: Algunas direcciones de los usuarios están desactualizadas en el momento de enviar correos electrónicos. Algunos usuarios no recibieron el correo.
*   Métrica de medición: Número de registros que están desactualizados.

### 1.8 Singularidad

*   Definición: La unicidad indica que un registro con detalles específicos sólo aparece una vez en la base de datos.
*   Buen ejemplo: Solo tenemos un registro para el nombre, la dirección y la fecha de nacimiento del usuario.
*   Mal ejemplo: Tenemos varios registros duplicados para el nombre, la dirección y la fecha de nacimiento del usuario.
*   Métrica de medición: número de datos duplicados y cuántas veces se han duplicado los datos.

### 1.9 Relevancia

*   Definición: Medidas de relevancia si los datos satisfacen el propósito de la recopilación de datos que puede ayudar al científico de datos a resolver el problema.
*   Buen ejemplo: Los datos pueden responder a todos los requisitos del científico de datos
*   Mal ejemplo: Los datos no pueden responder al requisito del científico de datos
*   Métrica de medición: El número de la queja del usuario divise a todos los usuarios. Esto puede ser objetivo, pero sigue siendo un buen indicador.

### 1.10 Interpretabilidad

*   Definición: La interpretabilidad refleja la facilidad con la que los usuarios pueden entender, utilizar y analizar adecuadamente.
    los datos. La adecuación de las definiciones de conceptos, poblaciones objetivo, variables y terminología
    la base de los datos, y la información que describe las limitaciones de los datos, si las hay, determina en gran medida
    el grado de interpretabilidad
*   Buen ejemplo: nombre de columna autoexplicativo, valores categóricos, descripción detallada de cada columna (por ejemplo, valor nulo, terminología de valores distintos)
*   Mal ejemplo: nombre de columna incomprensible, valor categórico, sin descripción en las columnas.
*   Métrica de medición: El número de la queja del usuario divise a todos los usuarios. Esto puede ser objetivo, pero sigue siendo un buen indicador.

## 2 Métrica común de calidad de datos

*   La relación entre datos y errores: supervisa el número de errores de datos conocidos en comparación con todo el conjunto de datos.

*   El número de valores vacíos: cuenta las veces que tiene un campo vacío dentro de un conjunto de datos.

*   Tiempo de obtención de valor de los datos: evalúa cuánto tiempo le lleva obtener información de un conjunto de datos. Hay otros factores
    influyendo en él, sin embargo, la calidad es una de las principales razones por las que esta vez puede aumentar.

*   Tasa de error de transformación de datos: esta métrica realiza un seguimiento de la frecuencia con la que falla una operación de transformación de datos.

*   Costos de almacenamiento de datos: cuando sus costos de almacenamiento aumentan mientras que la cantidad de datos que utiliza sigue siendo la misma, o peor,
    podría significar que una parte significativa de los datos almacenados tiene una calidad a baja para ser utilizados.

## 3. Gestión de la calidad de los datos: etapas del proceso descritas

### 3.1 Definir umbrales de calidad de datos

El objetivo de garantizar la calidad de los datos para una empresa es utilizar estos datos para tomar buenas decisiones. Y estas decisiones
ayudará a la empresa a reducir la expansión o ganar más dinero en ciertos productos o servicios. Así que podemos considerar los datos
controles de calidad como inversión, y el dinero que ganamos a través de estos datos como ingreso. Si los ingresos son mayores que
inversión entonces es un buen negocio.

Más a menudo, una empresa no necesita una calidad de datos 100% perfecta (por ejemplo, 100% consistente, 100 completa, etc.), porque
costará demasiado lograrlo, y la ganancia no es tan significativa. Como resultado, el trabajo de una calidad de datos
El administrador es identificar los umbrales de calidad de datos perfectos que hacen que los datos sean lo suficientemente buenos como para tomar decisiones y costar menos.
Y los umbrales de calidad pueden ser diferentes para diferentes apartamentos debido al diferente uso de los datos.

Por ejemplo, tiene una tabla de clientes que contiene columnas como:

*   full_name
*   date_of_birth
*   sexo
*   dirección
*   phone_num
*   Correo electrónico

Para el equipo de marketing el **Precisión, integridad, puntualidad** de full_name, dirección, teléfono, correo electrónico debe ser de hasta el 95%,
porque esta información era esencial para llegar al cliente. El **Orden, Singularidad** de dirección, teléfono, correo electrónico
debe ser de hasta el 75%. Debido a que incluso el formato de dirección no es estándar o único, el cliente aún puede recibir los correos.

Para el `date_of_birth` columna, que es menos importante, podemos ignorar el **Precisión, integridad, puntualidad**. Todo
necesitamos asegurarnos de que el formato de fecha es válido (cumplir con el atributo orderliness)

Para que pueda notar, la granularidad de un control de calidad de datos puede bajar a las columnas de una tabla, para cada columna.
puede tener umbrales específicos. Puede configurar el coeficiente para cada columna para calcular los umbrales generales
de la tabla, luego de todo el conjunto de datos.

### 3.2 Definir reglas de medición de la calidad de los datos

Ahora, hablemos de cómo medir si los datos cumplen con estos umbrales o no. Para eso, debe establecer la calidad de los datos
reglas de medición. Nota `data quality measurement rules is very similar to data validation rules, because data 
validation is a sub domain of data quality measurement`.

Con los umbrales definidos anteriormente, podemos declarar las siguientes reglas:

*   La dirección del cliente no debe ser N/A (para comprobar la integridad).
*   La dirección del cliente debe incluir un código postal y el nombre del país / estado (para verificar la orden).
*   Las cartas del cliente han sido devueltas (para comprobar la exactitud)
*   El correo electrónico del cliente debe consistir en @ (para verificar el orden).
*   Solo las primeras letras en el nombre del cliente, el segundo nombre (si los hay) y el apellido deben estar en mayúsculas (para verificar el orden).
*   La fecha de nacimiento debe ser una fecha válida que caiga en el intervalo del 01/01/1900 al 01/01/2010.

Umbrales de precisión = confirmación/cliente \* 100%

### 3.3 Evaluar la calidad de los datos

En este paso, probamos los datos utilizando las reglas de medición de calidad de datos que definimos en el paso anterior.

Por ejemplo, supongamos que tenemos 100 filas en el conjunto de datos.

*   Para la regla 1, detectamos que no hay filas que contengan valor nulo en la columna `address`. Tenga en cuenta casi toda la manipulación de datos
    framework puede detectar valores nulos. por ejemplo, en spark podemos crear una nueva columna para indicar que es null o
    not (df.withColumn("type_is_null", df.type.isNull())), luego contamos el número de filas nulas. Esto significa columna **la dirección tiene 100 como puntuación de integridad**
*   para la regla 2, detectamos que hay 26 filas que no tienen código postal, país o nombre de estado. Esto significa columna **la dirección tiene 74 como puntuación de orden**
*   para la regla 3, detectamos que 16 cartas que la empresa envía al cliente han sido devueltas, lo que significa que 16 filas tienen una dirección incorrecta.
    Esto significa **la dirección tiene 84 como puntuación de precisión**. Tenga en cuenta que esto también puede decirnos el **Puntualidad** de los datos si comparamos
    el resultado con el estado de devolución de la carta anterior. Por ejemplo, si el número de letra de devolución anterior es 10. Significa el 6
    la nueva carta de devolución se debe a la actualización de la dirección del cliente.

Puede notar, para probar las reglas anteriores, para algunas de ellas podemos usar análisis de datos para lograrlas (por ejemplo, verifique si
la dirección de correo electrónico se ajusta a ciertos formatos, tiene valor nulo o no). Pero para algunos de ellos, necesitamos contactar con el cliente para lograr
(como enviar una carta para verificar la dirección). Es por eso que la validación de datos es un subdominio del control de calidad de datos.
Porque no puede responder a todas las preguntas.

Después de aplicar todas las reglas, tendrá puntajes para todas las propiedades que queremos garantizar. Por ejemplo, para la columna

dirección:

*   Precisión: 84 (por debajo de los umbrales)
*   Integridad: 100 (arriba)
*   Orden: 74 (abajo). La orden es peor que la precisión, porque el formato de dirección incorrecto aún puede ser leído por un
    humano, luego derivado con éxito al cliente.
*   Puntualidad: 94 (Arriba)
*   Etc.

Ahora que tenemos la métrica de calidad de los datos, necesitamos manejar los problemas de calidad de los datos

### 3.4 Resolver problemas de calidad de datos

En esta etapa, necesitamos identificar la causa raíz de los problemas de calidad de los datos y encontrar la forma más eficiente de eliminarlos.

Por ejemplo, para el orden de la dirección del cliente, porque la dirección es ingresada manualmente por diferentes empleados,
y cada uno tiene su propia manera de escribir una dirección.

Solución a corto plazo: necesitamos pedirle al ingeniero de datos que limpie la columna convirtiendo todas las direcciones a un solo formato estándar.
Solución a largo plazo: necesitamos introducir estándares claros para las entradas de datos manuales de direcciones de clientes, así como para los datos
indicadores clave de rendimiento relacionados con la calidad para los empleados responsables de introducir datos en la base de datos. También podemos
establecer una regla de validación en el sistema que no aceptará una dirección a menos que cumpla con el formato o el rango.

### 3.5 Supervisar y controlar la calidad de los datos de forma continua

Los requisitos de datos y negocio evolucionan cada día, por lo que el sistema de gestión de calidad de datos debe evolucionar para adaptarse
nuevos cambios. Por ejemplo, un día su empresa puede querer hacer perfiles de usuario, por lo que su tabla personalizada tendrá nueva
columnas que describen el grupo demográfico y los pasatiempos personalizados. Debe agregar nuevos umbrales y reglas de calidad de datos a
asegúrese de que las nuevas columnas también satisfacen los requisitos de calidad de los datos.

Como resultado, el control de calidad de los datos no es un esfuerzo de una sola vez, sino un proceso ininterrumpido. **Necesita revisar regularmente
políticas y reglas de calidad de datos con la intención de mejorarlas continuamente**.

## 4. Mejores prácticas de gestión de la calidad de los datos

A continuación se presentan algunas prácticas recomendadas que pueden ayudarlo a mejorar la calidad de sus datos.

### 4.1 Integrar la gestión de la calidad de los datos

Integrar la gestión de la calidad de los datos en la canalización del procesamiento de datos es difícil y requiere mucho tiempo. Requiere múltiples pasos serios:

*   Sobre la base de la estrategia de gobierno de datos empresariales y los requisitos comerciales, diseñe una estrategia de calidad de datos adecuada (qué se debe hacer, quién lo hará, etc.).
*   Defina roles (por ejemplo, derechos, responsabilidad, kpi, recompensas, etc.) para todos los que trabajan con datos.
*   Establecimiento de un procedimiento de gestión de la calidad de los datos Procedimiento de funcionamiento estándar (consulte la sección 3).
*   Hacer visible la calidad de los datos (por ejemplo, informe, panel de control, etc.)

### 4.2 Automatizar tanto como sea posible

La mala calidad de los datos a menudo se introduce por error humano. Por ejemplo, entradas manuales de datos (por empleados, por clientes o
incluso por múltiples usuarios) es una de las principales razones.
Administrar miles de reglas de control de calidad de datos (validación) también es bastante difícil. Si un proceso puede automatizarse, impleméntelo.

### 4.3 Prevenir problemas, no solo solucionarlos

A menudo decimos "Basura adentro, basura afuera". Por lo tanto, en lugar de tomarse el tiempo para limpiar los datos, puede configurar reglas para evitar
los datos de baja calidad entran en su plataforma de datos. Por ejemplo, puede crear detección de valores nulos o detección de duplicados
reglas. Esta regla puede ayudarle a detectar anomalías dentro de un conjunto de datos antes de que entre en su plataforma de datos.

### 4.4 Cuidar tanto el maestro como los metadatos

Los datos maestros pueden ayudarlo a construir una referencia común (por ejemplo, código de moneda estándar, catálogo de productos, etc.) que cada
puede confiar en. Esto puede reducir la falta de coincidencia de términos o formatos, lo que mejora el orden de los datos.

Los metadatos pueden ayudarle a identificar y encontrar datos y sus propiedades fácilmente. Por ejemplo, la marca de tiempo de datos puede ayudarle
establecer versiones de datos, mejorando así la puntualidad de los datos. El linaje de datos puede ayudarle a identificar el upstream y
aguas abajo de un conjunto de datos. Puede ayudarle a mejorar la integridad y la consistencia.

Nota:
Un esquema de datos es simplemente un tipo de estructura de datos. Una estructura de datos es una representación del arreglo,
relaciones y contenido de los datos en el recurso de datos de una organización
