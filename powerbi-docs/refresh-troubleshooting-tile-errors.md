---
title: Solución de problemas de errores de icono
description: Errores comunes que pueden producirse cuando un icono intenta actualizarse en Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c1df7e6293db703922f37c3f28546bb296d1a46a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66050993"
---
# <a name="troubleshooting-tile-errors"></a>Solución de problemas de errores de icono
A continuación se muestran los errores comunes que pueden producirse con los iconos y una explicación.

> [!NOTE]
> Si se encuentra con algún error que no se enumera a continuación y que le causa problemas, puede pedir más ayuda en el [sitio de la comunidad](http://community.powerbi.com/), o bien puede crear una [incidencia de soporte técnico](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Errores
**Power BI encontró un error inesperado al cargar el modelo. Inténtelo de nuevo más tarde.**
o **No se puede recuperar el modelo de datos. Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existen y están accesibles.**

No se pudo acceder a los datos porque el origen de datos no estaba accesible. Este problema puede suceder si se quita, mueve o desconecta el origen de datos, o bien si se cambian el nombre o los permisos. Compruebe que el origen aún está en la ubicación que estamos señalando y que todavía tiene permiso para acceder a ella. Si no es este el problema, es posible que el origen sea lento. Inténtelo de nuevo más tarde durante un tiempo cuando la carga en el origen sea menor. Si es un origen local, es posible que el propietario del origen de datos pueda proporcionar más información.

**No tiene permiso para ver este icono ni para abrir el libro.**

Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existan y sean accesibles para su cuenta.

**El administrador ha deshabilitado los objetos visuales personalizados.**

Su administrador de Power BI ha deshabilitado el uso de objetos visuales personalizados para su organización o grupo de seguridad. No podrá usar objetos visuales personalizados desde [Microsoft Marketplace](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) ni importar objetos visuales privados desde un archivo. Solo podrá usar el conjunto de objetos visuales empaquetado previamente.


**Las formas de datos deben contener al menos un grupo o cálculo con salida de datos. Póngase en contacto con el propietario del panel.**

No tenemos ningún dato que mostrar porque la consulta está vacía. Intente agregar algunos campos de la lista de campos al objeto visual y vuelva a anclarlo.

**No se pueden mostrar los datos porque Power BI no puede determinar la relación entre dos o más campos.**

Está intentando usar dos o más campos de tablas que no están relacionadas. Debe quitar los campos no relacionados del objeto visual y, después, crear una relación entre las tablas. Después de hacerlo, podrá volver a agregar los campos al objeto visual. Esto puede hacerse en Power BI Desktop o PowerPivot para Excel. [Más información](desktop-create-and-manage-relationships.md)

**Los grupos del eje principal y del eje secundario se solapan. Los grupos del eje principal no pueden tener las mismas claves que los grupos del eje secundario.**

Esto suele ser un problema temporal. Esto ocurre normalmente cuando se mueven los grupos de las filas a las columnas. En este caso, el error debería desaparecer al terminar de mover todos los grupos. Si continúa recibiendo el mensaje, intente cambiar los campos entre las filas y las columnas o la leyenda del eje, o bien quite los campos del objeto visual.  

**El objeto visual superó los recursos disponibles. Intente filtrar para disminuir la cantidad de datos que se muestran.**

El objeto visual intentó consultar demasiados datos para poder completar el resultado con los recursos disponibles. Intente filtrar el objeto visual para reducir la cantidad de datos en el resultado.

**No podemos identificar los campos siguientes: {0}. Actualice el objeto visual con campos que existan en el conjunto de datos.**

Probablemente, se eliminó el campo o se le cambió el nombre. Puede quitar el campo dañado del objeto visual, agregar un campo diferente y volver a anclarlo.

**No se pueden recuperar los datos para este objeto visual. Inténtelo de nuevo más tarde.**

Este suele ser un problema transitorio. Si vuelve a intentarlo más tarde y se sigue mostrando este mensaje, póngase en contacto con el soporte técnico.

**Los iconos siguen mostrando datos sin filtrar después de habilitar el inicio de sesión único (SSO).**

Esto puede ocurrir si el conjunto de datos subyacente está configurado para usar el modo DirectQuery o una conexión dinámica a Analysis Services a través de una puerta de enlace de datos en el entorno local. En este caso, los iconos con mostrar los datos sin filtrar después de habilitar el inicio de sesión único para el origen de datos hasta que vence la próxima actualización de icono. En la siguiente actualización de icono, Power BI usa el inicio de sesión único como se ha configurado y los iconos se muestran los datos filtrados según la identidad del usuario. 

Si desea ver los datos filtrados de forma inmediata, puede forzar una actualización de icono, seleccione el botón de puntos suspensivos (...) en la esquina superior derecha de un panel y seleccione **Actualizar iconos del panel**.

Como propietario de un conjunto de datos, también puede cambiar la frecuencia de actualización de icono y establézcalo en 15 minutos para acelerar la actualización del icono. Seleccione el icono de engranaje en la esquina superior derecha del servicio Power BI y luego seleccione **configuración**. En el **configuración** página, seleccione el **conjuntos de datos** ficha. Expanda **actualización de caché programada** y cambiar **frecuencia de actualización**. Asegúrese de que restablecer la configuración original de la frecuencia de actualización después de que Power BI realiza la siguiente actualización de icono.

> [!NOTE]
> El **actualización de caché programada** sección solo está disponible para conjuntos de datos en modo de DirectQuery/LiveConnection. Conjuntos de datos en modo de importación no requieren una actualización de los iconos independientes porque los iconos se actualizan automáticamente durante la siguiente actualización de datos programada.

## <a name="contact-support"></a>Ponerse en contacto con soporte técnico
Si sigue teniendo problemas, [póngase en contacto con el soporte técnico](https://support.powerbi.com) para que lo investiguen con más detalle.

## <a name="next-steps"></a>Pasos siguientes
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Solución de problemas de Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

