---
title: Conexión a Azure Audit Logs con Power BI
description: Azure Audit Logs para Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 005913bc6af73f9b20db3cff7d12733f721eef3a
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720589"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Conexión a Azure Audit Logs con Power BI
Con el paquete de contenido de Registros de auditoría de Azure puede analizar y visualizar la información almacenada en los registros de auditoría. Power BI recupera los datos, crea un panel integrado y crea informes basados en esos datos.

[Conéctese al paquete de contenido de Registros de auditoría de Azure](https://app.powerbi.com/getdata/services/azure-audit-logs) u obtenga más información sobre la [integración de Registros de auditoría de Azure](https://powerbi.microsoft.com/integrations/azure-audit-logs) con Power BI.

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Seleccione **Registros de auditoría de Azure** > **Obtener**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Cuando se le solicite, escriba su **identificador de suscripción de Azure**. Vea los detalles acerca de cómo buscar el [identificador de suscripción](#FindingParams) a continuación.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. En **Método de autenticación**, seleccione **oAuth2** \> **Iniciar sesión**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Escriba sus credenciales de cuenta para finalizar el proceso de inicio de sesión.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI recuperará los datos de Registros de auditoría de Azure y creará un panel y un informe listos para usar. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](consumer/end-user-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](consumer/end-user-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o intentar actualizar a petición mediante **Actualizar ahora**

## <a name="system-requirements"></a>Requisitos del sistema
El paquete de contenido de registros de auditoría de Azure requiere acceso a los registros de auditoría en Azure Portal. Consulte más detalles [aquí](/azure/azure-resource-manager/resource-group-audit/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
Existen dos métodos sencillos de buscar el identificador de suscripción.

1. Desde https://portal.azure.com -&gt; Examinar -&gt; Suscripciones -&gt; Id. de suscripción
2. Desde https://manage.windowsazure.com -&gt; Configuración -&gt; Id. de suscripción

El identificador de suscripción será un conjunto largo de números y caracteres, similar al ejemplo del paso \#4 anterior. 

## <a name="troubleshooting"></a>Solución de problemas
Si ve un error en las credenciales o un error al intentar actualizar debido a credenciales no válidas, vuelva a intentar eliminar todas las instancias del paquete de contenido de Registros de auditoría de Azure y conéctese de nuevo.

## <a name="next-steps"></a>Pasos siguientes
[¿Qué es Power BI?](power-bi-overview.md)  
[Conceptos básicos para los diseñadores en el servicio Power BI](service-basic-concepts.md)  

