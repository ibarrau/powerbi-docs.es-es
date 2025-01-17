---
title: Tipos de información compatibles con Power BI
description: Información rápida y Ver información con Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 216c58644ee13cc6015878fc31d83e47e5673398
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "61064383"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Tipos de información compatibles con Power BI
## <a name="how-does-insights-work"></a>¿Cómo funciona la búsqueda de información?
Power BI busca rápidamente en distintos subconjuntos del conjunto de datos al tiempo que aplica un conjunto de algoritmos sofisticados para detectar información de posible interés. Power BI examina tanto como puede un conjunto de datos en el tiempo asignado.

Puede ejecutar la información en un conjunto de datos o en un icono de panel.   

## <a name="what-types-of-insights-can-we-find"></a>¿Qué tipos de información se puede buscar?
Estos son algunos de los algoritmos que se usan:

## <a name="category-outliers-topbottom"></a>Valores atípicos de categoría (superior o inferior)
Resalta los casos en los que, en relación con una medida del modelo, uno o dos miembros de una dimensión tienen valores mucho más altos que otros miembros de la dimensión.  

![Ejemplo de valores atípicos de categoría](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Cambiar los puntos de una serie temporal
Resalta cuando hay cambios significativos en las tendencias de datos de una serie temporal.

![Ejemplo de cambio de puntos de una serie temporal](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Correlación
Detecta los casos en los que varias medidas muestran una correlación entre sí al trazarse en una dimensión del conjunto de datos.

![Ejemplo de correlación](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Baja varianza
Detecta aquellos casos en los que los puntos de datos no están lejos de la media.

![Ejemplo de baja varianza](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Mayoría (factores principales)
Busca los casos en los que una mayoría de un valor total puede atribuirse a un único factor cuando se desglosa con otra dimensión.  

![Ejemplo de factores principales](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Tendencias generales de la serie temporal
Detecta las tendencias hacia arriba o hacia abajo de los datos de la serie temporal.

![Ejemplo de tendencias generales de serie temporal](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Estacionalidad de la serie temporal
Busca patrones periódicos en los datos de series temporales, por ejemplo, semanales, mensuales o de estacionalidad anual.

![Ejemplo de estacionalidad](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Recurso compartido constante
Resalta los casos en los que hay una correlación de elementos primarios y secundarios entre el recurso compartido de un valor de secundario en relación con el valor global del elemento primario a través de una variable continua.

![Ejemplo de recurso compartido constante](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Valores atípicos de la serie temporal
En el caso de los datos de una serie temporal, detecta si hay determinadas fechas u horas con valores significativamente diferentes de los demás valores de fecha y hora.

![Ejemplo de valores atípicos de serie temporal](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Pasos siguientes
[Información de Power BI](end-user-insights.md)

Si es propietario de un conjunto de datos, [optimícelo para información](../service-insights-optimize.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

