---
title: Uso de parámetros What if para visualizar variables
description: Creación de una variable What if propia para imaginar y visualizar variables en informes de Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 2451620c6d4092e5da4605f8e76b0a70e2eecf2b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513479"
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Creación y uso de un parámetro What if para visualizar variables en Power BI Desktop
A partir de la versión de agosto de 2018 de **Power BI Desktop**, puede crear variables **What if** para los informes, interactuar con la variable como una segmentación y visualizar y cuantificar diferentes valores clave de los informes.

![](media/desktop-what-if/what-if_01.png)

El parámetro **What if** se encuentra en la pestaña **Modelado** de **Power BI Desktop**. Cuando lo selecciona, aparece un cuadro de diálogo donde puede configurarlo.

## <a name="creating-a-what-if-parameter"></a>Creación de un parámetro What if
Para crear un parámetro **What if**, seleccione el botón **What if** en la pestaña **Modelado** de **Power BI Desktop**. En la imagen siguiente, se ha creado un parámetro llamado *Discount percentage* y se ha establecido su tipo de dato en *Número decimal*. El valor *Mínimo* es cero y el valor *Máximo* es 0,50 (cincuenta por ciento). También se *Incremento* en 0,05, o cinco por ciento. Esto indica cuánto se ajustará el parámetro cuando se interactúe con él en un informe.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Para números decimales, asegúrese de que vayan precedidos por un cero, como en 0,50 frente a simplemente ,50. En caso contrario, no se validará el número y no se podrá seleccionar el botón **Aceptar**.
> 
> 

Para su comodidad, la casilla **Agregar segmentación en esta página** coloca automáticamente una segmentación de datos con el parámetro **What if** en la página actual del informe.

![](media/desktop-what-if/what-if_03.png)

Al crear el parámetro **What if**, también se crea una medida, que puede usar para visualizar el valor actual de dicho parámetro.

![](media/desktop-what-if/what-if_04.png)

Es importante y resulta útil advertir que una vez creado un parámetro **What if**, el parámetro y la medida se convierten en parte del modelo. Por tanto, están disponibles en todo el informe y se pueden usar en otras de sus páginas. Y como son parte del modelo, puede eliminar la segmentación de datos de la página del informe y recuperarla con solo obtener el parámetro **What if** de la lista **Campos** y arrastrarlo al lienzo (el objeto visual cambia a una segmentación de datos) para devolverlo fácilmente a su informe.

## <a name="using-a-what-if-parameter"></a>Uso de un parámetro What if
Vamos a crear un ejemplo sencillo de uso de un parámetro **What if**. En la sección anterior se ha creado el parámetro **What if**; ahora crearemos una nueva medida cuyo valor se ajusta con la segmentación para ponerlo en funcionamiento. Para ello, se crea una nueva medida.

![](media/desktop-what-if/what-if_05.png)

La nueva medida será algo sencillo, como el importe de ventas total, con la tarifa de descuento aplicada. Por supuesto, puede crear medidas complejas e interesantes, que permitan a los clientes de los informes visualizar la variable del parámetro **What if?** . Por ejemplo, podría crear un informe que permita el personal de ventas ver que sus compensaciones si cumplen ciertos objetivos de ventas o porcentajes o ver el efecto de aumentado ventas en unos mayores descuentos.

Después de escribir la fórmula de medida en la barra de fórmulas y asignarle el nombre **Sales after Discount**, se puede ver el resultado:

![](media/desktop-what-if/what-if_06.png)

A continuación, se creará un objeto visual de columna con *OrderDate* en el eje, y los valores *SalesAmount* y la medida que se acaba de crear *Sales after Discount*.

![](media/desktop-what-if/what-if_07.png)

Seguidamente, conforme se mueve la segmentación, se puede ver que la columna *Sales after Discount* refleja el importe de ventas descontado.

![](media/desktop-what-if/what-if_08.png)

Y eso es todo. Puede usar parámetros **What if** en todo tipo de situaciones para permitir que los clientes de informes interactúen con diferentes escenarios que se creen en los informes.

