---
title: Sugerencias y trucos para crear informes en Power BI
description: Conozca los procedimientos recomendados para la creación de informes en el servicio Power BI y Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: willthom
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
ms.openlocfilehash: 41e5ff75e9b6fd48e3101d30999e8d570f34a270
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514068"
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop"></a>Sugerencias y trucos para crear informes en Power BI Desktop
Para sacar el máximo provecho a los datos, a veces es necesario un poco de ayuda adicional. Hemos recopilado algunos consejos y trucos que puede usar al crear informes con Microsoft Power BI Desktop *y* con las ediciones de Microsoft Excel 2016 o Excel 2013 Pro-Plus con el complemento Power Pivot habilitado y Power Query instalado y habilitado. 

## <a name="learning-to-use-the-query-editor"></a>Aprender a usar el Editor de consultas
El Editor de consultas de Power BI Desktop es similar al complemento Power Query de Excel 2013. Aunque el soporte de Power BI ofrece varios artículos útiles, también puede revisar la documentación de Power Query en support.office.com para comenzar.

Puede obtener información adicional en el [Centro de recursos de Power Query](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94).

También puede consultar la [referencia de las fórmulas](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

## <a name="data-types-in-query-editor"></a>Tipos de datos del Editor de consultas
Al usar el Editor de consultas en Power BI Desktop para cargar los datos, hacemos una detección del tipo de datos. Al usar las fórmulas, a veces no se conserva la configuración de tipos de datos en las columnas. Asegúrese de que el tipo de datos de columnas es correcto tras realizar las siguientes operaciones:  Cargar datos inicialmente en la pestaña de consulta, Primera fila como encabezado, Agregar columna, Agrupar por, Combinar y antes de presionar cargar los datos por primera vez.

Un elemento clave que hay que recordar: la cursiva en la cuadrícula de datos no significa que el tipo de datos se haya configurado correctamente, solo indica que los datos no se consideran como texto.

## <a name="reference-queries-in-the-query-editor"></a>Consultas de referencia en el Editor de consultas
En el navegador del Editor de consultas en Power BI Desktop, cuando hace clic en una de las consultas, está disponible una opción "Referencia". Esto resulta útil por el siguiente motivo:

* Cuando se usan archivos como orígenes de datos para una consulta, la ruta de acceso absoluta al archivo se almacena en la consulta. Al compartir o mover el archivo de Power BI Desktop o Excel Workbook, ahorrará tiempo al actualizar las rutas de acceso, ya que solo necesitará actualizar los datos una vez.

De forma predeterminada todas las consultas se cargan en una hoja de cálculo de Excel o en el modelo de datos (o ambos). Algunas consultas son pasos intermedios y no destinada a los usuarios finales. como, por ejemplo, al hacer referencia a las consultas tal como se ha mencionado anteriormente. Puede controlar el comportamiento de carga haciendo clic en la consulta en el navegador y si activa o desactiva la opción "Habilitar carga" de la consulta. Cuando *habilitar la carga* no tiene una marca de verificación junto a él, la consulta sigue estando disponible en la pestaña de consulta y usarla con otras consultas. Esto resulta especialmente útil en combinación con las operaciones de combinación, anexado y transformaciones de referencia. Sin embargo, puesto que los resultados de la consulta no se cargan en el modelo de datos, la consulta no recargará la lista de campos de informes o el modelo de datos. 

## <a name="scatter-charts-need-a-point-identifier"></a>Necesidad del identificador de puntos en los gráficos de dispersión
Tomemos como ejemplo una sencilla tabla de temperaturas con la hora a la que se realizó la lectura. Si trazamos directamente un gráfico de dispersión, Power BI agrega todos los valores en un único punto. Para mostrar puntos de datos individuales, debe agregar también un campo a los detalles en el campo. Una manera sencilla de hacerlo esto en Power BI Desktop es mediante la opción "Agregar columna de índice" de la pestaña de consultas, en la cinta de opciones "Agregar columna". 

## <a name="reference-lines-in-your-report"></a>Líneas de referencia del informe
Puede usar una columna calculada en Power BI Desktop para definir una línea de referencia. Identifique la tabla y la columna en las que desea crear una línea de referencia. Seleccione "Nueva columna" en la cinta de opciones y, en la barra de fórmulas, escriba la fórmula siguiente:

    Target Value = 100

Esta columna calculada devolverá el valor 100 independientemente de dónde se use. La nueva columna aparecerá en la lista de campos. Agregue la columna calculada del valor de destino a un gráfico de líneas para mostrar cómo se relacionan las series a dicha línea de referencia específica. 

## <a name="sort-by-another-column"></a>Ordenación por otra columna
Cuando se usa un valor de categoría (cadena) en Power BI para los ejes de gráficos o en segmentaciones o filtros, el orden predeterminado es alfabético. Si necesita cambiar este orden, por ejemplo para cosas como los días de la semana o meses, a continuación, puede indicar Power BI Desktop que ordene por una columna diferente. Para obtener más información, consulte [ordenar por columnas en Power BI Desktop](desktop-sort-by-column.md).

## <a name="building-maps-more-easily-with-hints-to-bing"></a>Creación de mapas simplificada con las sugerencias de Bing
Power BI se integra con Bing para proporcionar las coordenadas de mapas predeterminadas (es decir, un proceso denominado codificación geográfica) y facilitar la creación de mapas. Bing usa algunos algoritmos y sugerencias para intentar obtener la ubicación correcta, aunque es un cálculo aproximado. Para aumentar la probabilidad de realizar la codificación geográfica de manera correcta, use las sugerencias siguientes:

Cuando se crea un mapa, a menudo se busca trazar países, estados y ciudades. En Power BI Desktop, el uso de columnas de nombres después de la designación geográfica ayudará a Bing a adivinar lo que desea mostrar. Por ejemplo, si tiene un campo de nombres de estado de Estados Unidos como, por ejemplo, "California" y "Washington", Bing podría devolver la ubicación de Washington, DC, en lugar de la del estado de Washington debido a la palabra "Washington". Asignar a la columna el nombre "Estado" mejorará la codificación geográfica. Lo mismo ocurre para las columnas denominadas "País" y "Ciudad". 

Algunas designaciones son ambiguas cuando se consideran en el contexto de varios países/regiones. En determinados países o regiones, los "Estados" se consideran como una "provincia" o un "condado" u otras designaciones. Puede aumentar la precisión de la codificación geográfica con la creación de columnas con varios campos juntos que permitan trazar las ubicaciones de los datos. Un ejemplo de ello sería, en lugar de pasar solo "Wiltshire", pasar "Wiltshire, Inglaterra" para obtener un resultado más preciso de codificación geográfica. 

Siempre es posible proporcionar ubicaciones específicas de latitud y longitud en el servicio Power BI o Power BI Desktop. Al hacerlo, también debe pasar un campo de ubicación, de lo contrario, los datos se agregan de forma predeterminada, por lo que es posible que la ubicación de latitud y longitud no coincida con lo que esperaba.

## <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>Categorización de campos geográficos de sugerencias de codificación geográfica de Bing
Otra forma de asegurarse de que los campos estén correctamente codificados geográficamente al establecer la categoría de datos en los campos de datos. En Power BI Desktop, seleccione la tabla deseada, vaya a la cinta de opciones avanzada y, a continuación, Establece la categoría de datos en la dirección, ciudad, continente, país o región, país, código Postal, estado o provincia. Estas categorías de datos ayudan a Bing a codificar correctamente los datos. Para más información, consulte [Categorización de datos en Power BI Desktop](desktop-data-categorization.md).

## <a name="better-geocoding-with-more-specific-locations"></a>Mejora de la codificación geográfica con ubicaciones más específicas
A veces, incluso el establecimiento de las categorías de datos de mapas no es suficiente. Con el Editor de consultas de Power BI Desktop, cree una ubicación más específica como, por ejemplo, una dirección postal. Use la característica Agregar columnas para crear una columna personalizada. A continuación, cree la ubicación deseada como se muestra a continuación: 

    = [Field1] & " " & [Field2]

A continuación, use este campo resultante en las visualizaciones de mapa. Esto resulta muy útil para crear direcciones postales a partir de los campos de dirección de envío que son comunes en los conjuntos de datos. Hay que tener en cuenta que la concatenación solo funciona con campos de texto. Si es necesario, convierta el número de la calle a un tipo de datos de texto antes de usarlo para crear una dirección.

## <a name="histograms-in-the-query-stage"></a>Histogramas en la fase de consulta
Hay varias formas de crear histogramas en Power BI Desktop. Comenzaremos con la más sencilla e iremos avanzando a partir de ahí:

Histogramas más sencillos: determine qué consulta tiene el campo a partir del cual desea generar un histograma. Use la opción "Referencia" para que la consulta cree una nueva consulta y asígnele el nombre "FieldName Histogram". Use la opción "Agrupar por" de la cinta de opciones "Transformar" y seleccione el agregado "recuento de filas". Asegúrese de que el tipo de datos es un número para la columna agregada resultante. A continuación, visualice estos datos en la página de informes. La creación de este histograma resultará rápida y sencilla, aunque no es la opción recomendada si tiene muchos puntos de datos; además, no permite resaltar diferentes objetos visuales.

Definición de cubos para crear histogramas: determine qué consulta tiene el campo a partir del cual desea generar un histograma. Use la opción "Referencia" para que la consulta cree una nueva consulta y asígnele el nombre "FieldName". Defina los cubos con una regla. Use la opción Agregar columnas personalizadas de la cinta de opciones Agregar columna y cree una regla personalizada. Esta podría ser una regla de creación de cubos sencilla:

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

Asegúrese de que el tipo de datos es un número para la columna agregada resultante. Ahora puede usar el grupo mediante la técnica descrita en la sección Histogramas más sencillos obtener el histograma. Esta opción controla más puntos de datos, pero todavía no ayuda con los gráficos.

Definición de histogramas que permitan el resaltado: el resaltado es cuando los objetos visuales están vinculados entre sí para que cuando un usuario selecciona un punto de datos de un objeto visual, otros objetos visuales en la página del informe resaltarán o filtran los puntos de datos relacionados con el punto de datos seleccionado. Puesto que vamos a manipular los datos en tiempo de consulta, necesitamos crear una relación entre las tablas y asegurarse de que sabemos qué elemento de detalle está relacionado con el cubo del histograma y viceversa.

Inicie el proceso con la opción "Referencia" de la consulta que tiene el campo a partir del cual desea generar un histograma. Asigne a la nueva consulta el nombre "Cubos". En este ejemplo, llamaremos a la consulta original "Detalles". A continuación, quite todas las columnas excepto la columna que se va a usar como cubo del histograma. Ahora use la característica "Quitar duplicados" en la consulta que se encuentra en el menú contextual que aparece al seleccionar la columna. De este modo, los demás valores serán los únicos valores de la columna. Si tiene números decimales, puede usar la primera sugerencia para definir cubos para crear un histograma que permita obtener un conjunto de cubos fáciles de administrar. Ahora, compruebe los datos que se muestran en la vista previa de la consulta. Si ve valores en blanco o nulos deberá corregirlos antes de crear una relación. Consulte "Creación de una relación si mis datos tienen valores nulos o en blanco". El uso de este enfoque puede ser problemático debido a la necesidad de ordenar. Para obtener los cubos ordenados correctamente, vea "Ordenación: conseguir que las categorías aparezcan en el orden deseado". 

>[!NOTE]
>Conviene pensar en el criterio de ordenación antes de crear los objetos visuales. 

El siguiente paso del proceso es definir una relación entre las consultas de "Cubos" y "Detalles" en la columna de cubos. En Power BI Desktop, haga clic en **Administrar relaciones** en la cinta de opciones. Cree una relación según la cual los cubos se situarán en la tabla izquierda y los detalles en la tabla derecha. A continuación, seleccione el campo que va a usar para el histograma. 

El último paso es crear el histograma. Arrastre el campo Cubo desde la tabla "Cubos". Quite el campo predeterminado del gráfico de columnas resultante. Ahora, desde la tabla "Detalles", arrastre el campo de histograma al mismo objeto visual. En el conjunto de campos, cambie el agregado predeterminado a Recuento. Obtendrá como resultado un histograma. Si crea otro objeto visual como, por ejemplo, un gráfico de rectángulos de la tabla Detalles, seleccione un punto de datos en el gráfico de rectángulos para ver el histograma resaltado y mostrar el histograma del punto de datos seleccionado en relación con la tendencia de todo el conjunto de datos.

## <a name="histograms"></a>Histogramas
En Power BI Desktop, puede usar un campo calculado para definir un histograma. Identifique la tabla y la columna en las que desea crear un histograma. En el área de cálculo, escriba la fórmula siguiente:

> Frequency:=COUNTROWS(\<Nombre de columna\>)
> 
> 

Guarde los cambios y vuelva al informe. Agregue el \<Nombre de columna\> y la frecuencia a una tabla para, a continuación, convertirlos en un gráfico de barras. Asegúrese de que el \<Nombre de columna\> se encuentra en el eje x y de que el campo calculado Frecuencia se encuentra en el eje y.

## <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Sugerencias y trucos para crear relaciones en Power BI Desktop
A menudo al cargar conjuntos de datos detallados de varios orígenes, problemas como los valores nulos, los valores en blanco o los valores duplicados impiden crear las relaciones. 

Veamos un ejemplo: 

Supongamos que cargamos conjuntos de datos de solicitudes de soporte de clientes activos y otro conjunto de datos de elementos de trabajo que tienen esquemas como el siguiente:

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Si queremos realizar un seguimiento de todos los incidentes y elementos de trabajo relacionados con un determinado un CustomerName, no podemos crear simplemente una relación entre estos dos conjuntos de datos. Algunos WorkItems pueden no estar relacionados con un CustomerName, por lo que dicho campo estaría en blanco o con un valor NULL. Puede haber varios registros de en WorkItems y CustomerIncidents para cualquier CustomerName determinado. 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>Creación de relaciones en Power BI Desktop si mis datos tienen valores nulos o en blanco
A menudo los conjuntos de datos contienen columnas con valores nulos o en blanco. Esto puede producir problemas al intentar usar las relaciones. Básicamente hay dos opciones para resolver los problemas. Podemos quitar las filas que tengan valores nulos o en blanco. Para ello, se puede usar una característica de filtro en la pestaña de consulta o si se van a combinar las consultas, seleccionar la opción "Mantener solo las filas coincidentes". De manera alternativa, se pueden reemplazar los valores en blanco o nulos con valores que funcionan normalmente en las relaciones como, por ejemplo, las cadenas "NULL" y ("Blank"). No hay ningún enfoque correcto aquí: el filtrado de filas en la fase de consulta quita filas y puede afectar a los cálculos y las estadísticas de resumen. El último enfoque conserva dichas filas de datos, pero puede hacer que en el modelo aparezcan filas no relacionadas como relacionadas, lo que daría lugar a cálculos erróneos. Si adoptamos la última solución, debemos asegurarnos de usar filtros en la visa/gráfico donde corresponda para asegurarse de que se obtienen resultados precisos. Lo más importante es evaluar las filas que se mantendrán/eliminarán y comprender el impacto global en el análisis. 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>Creación de relaciones en Power BI Desktop si los datos tienen valores duplicados
A menudo, cuando se cargan conjuntos de datos detallados de varios orígenes, los valores de datos duplicados impiden crear las relaciones. Este problema se puede solucionar creando una tabla de dimensiones con los valores únicos de ambos conjuntos de datos. 

Veamos un ejemplo: 

Supongamos que cargamos conjuntos de datos de solicitudes de soporte de clientes activos y otro conjunto de datos de elementos de trabajo que tienen esquemas como el siguiente:

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Si queremos realizar un seguimiento de todos los incidentes y elementos de trabajo relacionados con un determinado un CustomerName, no podemos crear simplemente una relación entre estos dos conjuntos de datos. Algunos WorkItems pueden no estar relacionados con un CustomerName, por lo que dicho campo estaría en blanco o con un valor NULL. Si hay valores en blanco o nulos en la tabla CustomerNames, es posible que aún no se pueda crear ninguna relación. Vea Creación de relaciones si mis datos tienen valores nulos o en blanco. Puede haber varios WorkItems y CustomerIncidents para un único CustomerName. 

Para crear una relación en este caso, tenemos que crear un conjunto de datos lógico de todos los CustomerNames de los dos conjuntos de datos. En la pestaña consulta, puede usar la siguiente secuencia para crear el conjunto de datos lógico:

1. Duplique ambas consultas, asignando a la primera el nombre **Temp** y el nombre **CustomerNames**a la segunda.
2. En cada consulta, quite todas las columnas *excepto* la columna CustomerName
3. En cada consulta, use  **Quitar duplicados**.
4. En la consulta **CustomerNames** , seleccione la opción **Anexar** de la cinta de opciones, seleccione la consulta **Temp**.
5. En la consulta **CustomerNames** , seleccione **Quitar duplicados**.

Ahora tiene una tabla de dimensiones que puede usar para crear una relación entre CustomerIncidents y WorkItems en la que se incluyen todos los valores de cada uno. 

## <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>Patrones para comenzar a usar el Editor de consultas
El Editor de consultas es muy eficaz a la hora de manipular los datos para darles forma y limpiarlos para que estén listos para la visualización o el modelado. Existen determinados patrones que debe tener en cuenta.

### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>Las columnas temporales se pueden eliminar después de calcular un resultado
A menudo es necesario crear un cálculo en Power BI Desktop capaz de transformar los datos de varias columnas en una única nueva columna. Esto puede resultar complejo. Una forma sencilla de solucionar el problema es dividir la operación en pasos. Comience por duplicar las columnas iniciales. A continuación, cree los pasos en una columna temporal. Luego cree una columna para el resultado final. En este punto, podrá eliminar las columnas temporales para que el conjunto de datos final no esté lleno. Esto es posible porque la pestaña de consulta ejecuta los pasos en orden. 

### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>Consultas duplicadas o de referencia seguidas por la combinación en la consulta original
A veces es útil calcular las estadísticas de resumen para un conjunto de datos. Una manera fácil de hacerlo es duplicar o hacer referencia a la consulta en la pestaña de la consulta. A continuación, use la opción **Agrupar por** para calcular las estadísticas de resumen. Las estadísticas de resumen le ayudarán a normalizar los datos en los datos originales para que sean más comparables como en . Esto resulta especialmente útil para comparar valores individuales con el conjunto completo. Para ello, vaya a la consulta original y seleccione la opción de combinación. A continuación, combine los datos de la consulta de estadísticas de resumen que coincida con los identificadores adecuados. Ahora está listo para normalizar los datos según sea necesario para su análisis.

## <a name="using-dax-for-the-first-time"></a>Uso de DAX por primera vez
DAX es el lenguaje de fórmulas de cálculos de Power BI Desktop. Está optimizado para el análisis de BI. Es un poco distinto de los lenguajes con los que es posible que ya esté familiarizado si solo ha usado SQL como lenguaje de consulta. Existen numerosos recursos disponibles en línea, así como documentación de aprendizaje de DAX. 

[Aspectos básicos de DAX en Power BI Desktop](desktop-quickstart-learn-dax-basics.md)

[Referencia de expresiones de análisis de datos (DAX)](https://msdn.microsoft.com/library/gg413422.aspx)

[Centro de recursos de DAX](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)
