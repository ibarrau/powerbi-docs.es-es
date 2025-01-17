---
title: Exportar los informes a formato PDF desde Power BI Desktop
description: Exporte fácilmente a PDF desde Power BI Desktop e imprima con facilidad esos informes en PDF
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/28/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 2f64973650edd951a9a780090426afba3e8471f5
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "61303188"
---
# <a name="export-reports-to-pdf-from-power-bi-desktop"></a>Exportar informes a PDF desde Power BI Desktop
En **Power BI Desktop** o en el servicio Power BI, puede exportar informes a un archivo PDF y, por tanto, compartirlos o imprimirlos fácilmente desde ese PDF.

![Exportar a PDF](media/desktop-export-to-pdf/export-to-pdf_01.png)

El proceso de exportación del informe de **Power BI Desktop** a un PDF para que pueda imprimir o compartir el PDF con otros usuarios es sencillo. Solo tiene que seleccionar **Archivo > Exportar a PDF** desde Power BI Desktop.

El proceso de **Exportar a PDF** exportará todas las páginas *visibles* del informe, y cada una de ellas se exportará a una sola página en el PDF. Las páginas del informe que no estén visibles, como cualquier información sobre herramientas o páginas ocultas, no se exportan al archivo PDF. 

![Exportación a PDF en curso](media/desktop-export-to-pdf/export-to-pdf_02.png)

Al seleccionar **Archivo > Exportar a PDF**, se inicia la exportación y aparece un cuadro de diálogo que muestra que el proceso de exportación está en curso. El cuadro de diálogo permanece en la pantalla hasta que se complete el proceso de exportación. Durante el proceso de exportación, se deshabilita toda la interacción con el informe que se está exportando. La única forma de interactuar con el informe es esperar a que se complete el proceso de exportación, o bien cancelar la exportación. 

Cuando finalice la exportación, el PDF se carga en el visor de PDF predeterminado del equipo. 

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Hay algunas consideraciones que se deben tener en cuenta con la característica **Exportar a PDF**.

* La característica exporta objetos visuales personalizados, pero *no* exporta ningún papel tapiz que haya aplicado al informe.

Puesto que no se exporta el papel tapiz al PDF, debe prestar especial atención a los informes que usen un papel tapiz oscuro. Si el texto del informe es blanco o claro, para que destaque en el papel tapiz oscuro, será difícil de leer o no se podrá leer en el proceso de exportación a PDF puesto que no se exportará el papel tapiz con el resto del informe. 



## <a name="next-steps"></a>Pasos siguientes
Hay muchos elementos visuales y características interesantes de **Power BI Desktop**. Para más información, consulte los recursos siguientes:

* [Uso de elementos visuales para mejorar los informes de Power BI](desktop-visual-elements-for-reports.md)
* [¿Qué es Power BI Desktop?](desktop-what-is-desktop.md)


