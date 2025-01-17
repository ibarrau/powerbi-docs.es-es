---
title: 'Project Online: conexión a los datos a través de Power BI Desktop'
description: 'Project Online: conexión a los datos a través de Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b0dc84d7b2d8da0df8a9e61a43f35898d197c188
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513741"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: conexión a los datos a través de Power BI Desktop
Puede conectarse a los datos en Project Online a través de Power BI Desktop.

## <a name="step-1-download-power-bi-desktop"></a>Paso 1: Descargar Power BI Desktop
1. [Descargue Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662) y, después, ejecute el instalador para obtener **Power BI Desktop** en el equipo.

## <a name="step-2-connect-to-project-online-with-odata"></a>Paso 2: Conexión a Project Online con OData
1. Abra **Power BI Desktop**.
2. En la pantalla de *bienvenida*, seleccione **Obtener datos**.
3. Elija **Fuente de OData** y seleccione **Conectar**.
4. Escriba la dirección de su fuente de OData en el cuadro de la dirección URL y, a continuación, haga clic en Aceptar.
   
   Si la dirección de su sitio de Project Web App se parece a *https://\<tenantname\>.sharepoint.com/sites/pwa*, entonces la dirección que especifique para la fuente de OData es *https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata*.
   
   En nuestro ejemplo, estamos usando https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop le solicitará que realice la autenticación con su cuenta de Office 365. Seleccione la cuenta de la organización y, a continuación, escriba sus credenciales.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

La cuenta que use para conectarse a la fuente debe tener al menos de OData de tener acceso un visor de carteras al sitio de Project Web App. 

Desde aquí, puede elegir a qué tablas le gustaría conectarse y crear una consulta.  ¿Desea una idea de cómo comenzar?  Entrada de blog siguiente muestra cómo crear una grabación de gráfico de los datos de Project Online.  La entrada de blog se refiere al uso de Power Query para conectarse a Project Online, pero esto se aplica también a Power BI Desktop.

[Crear grabación de gráficos para Project con PowerPivot y Power Query](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

