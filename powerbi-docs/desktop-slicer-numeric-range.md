---
title: Uso de la segmentación de intervalos numéricos en Power BI Desktop
description: Aprenda a usar la segmentación para restringir a intervalos numéricos en Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 68467894850248d6acb841dc2ed651f595f19b95
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "61364089"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Uso de la segmentación de intervalos numéricos en Power BI Desktop
Gracias a la **segmentación de intervalos numéricos**, puede aplicar todo tipo de filtros a cualquier columna numérica del modelo de datos. Puede filtrar **entre** números, o por un número **menor o igual que** o **mayor o igual que** otro número. Aunque esto puede parecer demasiado simple, es una manera muy eficaz de filtrar los datos.

![Objeto visual con segmentación de intervalos numéricos](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Uso de la segmentación de intervalos numéricos
Puede usar la segmentación de intervalos numéricos igual que cualquier otra segmentación de datos. Solo tiene que crear un objeto visual de **segmentación** para el informe y, a continuación, seleccionar un valor numérico para el valor **Campo**. En la imagen siguiente, se ha seleccionado el campo *LineTotal*.

![Crear una segmentación de intervalos numéricos](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Seleccione el vínculo de flecha abajo en la esquina superior derecha de la **segmentación de intervalos numéricos** y aparecerá un menú.

![Menú de segmentación de intervalos numéricos](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Para el intervalo numérico, puede seleccionar entre las siguientes tres opciones:

* Entre
* Menor o igual que
* Mayor o igual que

Cuando se selecciona **Entre** en el menú, aparece un control deslizante y puede filtrar por los valores numéricos que se encuentran entre los números seleccionados. Además de utilizar la propia barra deslizante, también puede hacer clic en cualquiera de los cuadros y escribir los valores. Esto resulta útil cuando quiere segmentar en números específicos, pero la precisión a la hora de mover la barra de segmentación de datos hace que sea difícil elegir exactamente el número deseado.

En la imagen siguiente, la página de informe se filtra por los valores *LineTotal* comprendidos entre 2500,00 y 6000,00.

![Segmentación de intervalos numéricos con la opción Entre](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Cuando se selecciona **Menor o igual que**, desaparece el controlador de la izquierda (el valor inferior) de la barra deslizante y podemos ajustar solo el límite superior de la barra. En la imagen siguiente, la barra deslizante se establece en un máximo de 5928,19.

![Segmentación de intervalos numéricos con la opción Menor que](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Por último, si se selecciona **Mayor o igual que**, desaparecerá el control de la barra deslizante de la derecha (el del valor más alto) y solo podremos ajustar el valor inferior, tal como se muestra en la siguiente imagen. Ahora solo aquellos elementos con un valor de *LineTotal* mayor o igual que 4902,99 aparecerán en los objetos visuales de la página de informe.

![Segmentación de intervalos numéricos con la opción Mayor que](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Ajuste a números enteros con la segmentación de intervalos numéricos

Una segmentación de rango numérico se ajustará a números enteros si el tipo de datos del campo subyacente es **número entero**. Esto permite que la segmentación se alinee limpiamente con números enteros. Los campos de tipo **número decimal** permiten especificar o seleccionar fracciones de un número. El formato aplicado en el cuadro de texto coincide con el formato establecido en el campo, aunque puede escribir o seleccionar números más precisos.

## <a name="display-formatting-with-the-date-range-slicer"></a>Mostrar formato con la segmentación de datos de intervalo de fechas

Al usar una segmentación de datos para mostrar o configurar un intervalo de fechas, el formato de la fecha siempre se muestra con el formato **Fecha corta**, de acuerdo con la configuración regional del sistema operativo o el explorador del usuario. Este es el formato de presentación, independientemente de la configuración del tipo de datos de los datos subyacentes o el modelo. 

Por ejemplo, el formato del tipo de datos subyacente podría ser fecha larga (por ejemplo, *dddd, MMMM, aaaa*, de forma que el formato de una fecha en otros objetos visuales o circunstancias sería *Miércoles, 14 de marzo de 2001*), pero en la segmentación de datos de intervalo de fechas esa fecha se mostrará como *03/14/2001*.

Mostrar el formato **Fecha corta** en la segmentación de datos garantiza que la longitud de la cadena es coherente y compacta dentro de la segmentación de datos. 


## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones
Las siguientes limitaciones y consideraciones se aplican actualmente a la **segmentación de intervalos numéricos**:

* Actualmente, la **segmentación de intervalos numéricos** filtra todas las filas subyacentes de los datos, pero no los valores agregados. Por ejemplo, si se usa un campo *Sales Amount*, se podría filtrar cada transacción basada en *Sales Amount* pero no la suma de *Sales Amount* de cada punto de datos de un objeto visual.
* Actualmente no funciona con medidas.
* Puede escribir cualquier número en los cuadros de texto en una segmentación numérica, aunque esté fuera del intervalo de valores de la columna subyacente. Esto le permite configurar filtros si sabe que los datos pueden cambiar en el futuro.
