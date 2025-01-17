---
title: Sugerencias para diseñar un panel de Power BI fantástico
description: Sugerencias para diseñar un panel de Power BI fantástico
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 0e523707caa38c808c777eb29bb8dcbdc6af5ebf
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721216"
---
# <a name="tips-for-designing-a-great-power-bi-dashboard"></a>Sugerencias para diseñar un panel de Power BI fantástico
Ahora que ya creó un panel y agregó algunos iconos, piense en cómo conseguir un panel atractivo, a la par que funcional. En general, esto se consigue destacando la información más importante y manteniéndolo limpio y despejado.

Aquí encontrará algunas sugerencias.

> [!TIP]
> Muchos de los principios de diseño de los informes se aplican también a los paneles.  Lea las notas del producto sobre los [principios para el mejor diseño de los informes y las visualizaciones](visuals/power-bi-visualization-best-practices.md).
>
>

## <a name="watch-the-dashboard-makeover-webinarhttpsinfomicrosoftcomco-powerbi-wbnr-fy16-05may-12-dashboard-makeover-registrationhtml"></a>Ver el [seminario web Dashboard Makeover (Transformación del panel)](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-05May-12-Dashboard-Makeover-Registration.html)
Vea cómo Marc Reguera, jefe principal de programas de Microsoft y experto en paneles de Power BI, [transforma los informes](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-05May-12-Dashboard-Makeover-Registration.html).

## <a name="consider-your-audience"></a>Tenga en cuenta al público
¿Cuáles son las métricas claves que le ayudarán a tomar decisiones? ¿Cómo se usará el panel? ¿Qué suposiciones adquiridas o culturales pueden afectar a las opciones de diseño? ¿Qué información necesita su público para conseguir buenos resultados?

Tenga en cuenta que el panel es un recurso de información general, un lugar único para supervisar el estado actual de los datos. El panel se basa en informes y conjuntos de datos subyacentes, que a su vez pueden contener numerosos detalles. Los lectores pueden profundizar en los informes desde el panel. Por eso, no incluya detalles en el panel además de la información que deben supervisar los lectores.

¿Dónde se mostrará el panel? Si el panel se va a mostrar en un monitor grande, puede incluir más contenido. Si los lectores lo consultarán en tabletas, cuantos menos iconos tenga, más legible será.

## <a name="tell-a-story-and-keep-it-to-one-screen"></a>Cuente una historia y muéstrela en una pantalla
Los paneles están diseñados para mostrar la información importante de un vistazo, por lo que se recomienda incluir todos los iconos en una pantalla. ¿Puede evitar las barras de desplazamiento en el panel?

¿Está el panel demasiado abarrotado?  Quítelo todo, excepto la información esencial que se pueda leer e interpretar fácilmente.

## <a name="make-use-of-full-screen-mode"></a>Use el modo de pantalla completa
Muestre su panel en [pantalla completa](consumer/end-user-focus.md) sin distracciones.

## <a name="make-the-most-important-information-biggest"></a>Muestre la información más importante a mayor tamaño
Si el texto y las visualizaciones son del mismo tamaño en el panel, a los lectores les costará centrarse en lo más importante. Por ejemplo, las visualizaciones de tarjeta son una buena forma de mostrar un número importante de forma destacada:  
![Visualización de tarjeta](media/service-dashboards-design-tips/pbi_card.png)

Pero no olvide proporcionar un contexto.  

Más información sobre cómo [crear un icono con un solo número](visuals/power-bi-visualization-card.md).

## <a name="put-the-most-important-information-in-the-upper-corner"></a>Coloque la información más importante en la parte superior
La mayoría de las personas leen de arriba abajo, por lo que se recomienda colocar la información con mayor nivel de detalle en la parte superior e ir mostrando más detalles a medida que avanza en la dirección en que lee el público (de izquierda a derecha, o de derecha a izquierda).

## <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>Use el formato y la visualización correcta para los datos para facilitar la lectura
Evite utilizar distintos tipos de visualizaciones simplemente para aportar variedad.  Las visualizaciones deben transmitir una imagen, y ser fáciles de "leer" e interpretar.  En el caso de algunos datos y visualizaciones, basta con una sencilla visualización gráfica. Sin embargo, otros datos pueden requerir una visualización más compleja. Por ello, asegúrese de usar títulos, etiquetas y las personalizaciones necesarias para ayudar al lector.  

* [Elija visualizaciones de datos adecuadas](https://www.youtube.com/watch?v=-tdkUYrzrio). Tenga cuidado al usar gráficos que distorsionen la realidad, como los tridimensionales. Tenga en cuenta que al cerebro humano le cuesta interpretar las formas circulares. Los gráficos circulares, de anillos, de medidores y otros tipos de gráficos circulares pueden parecer atractivos, pero no son un procedimiento recomendado para la visualización de datos.
* Sea coherente con las escalas del gráfico en los ejes, el orden de las dimensiones del gráfico y los colores que use para los valores de las dimensiones de los gráficos.
* Asegúrese de codificar correctamente los datos cuantitativos. No use más de tres o cuatro dígitos al mostrar números. Muestre las medidas con uno o dos números a la izquierda de la coma decimal y reduzca los millares o millones, es decir, escriba "3,4 millones" en lugar de "3.400.000".
* No mezcle los niveles de precisión y tiempo. Asegúrese de que los intervalos de tiempo se comprenden perfectamente.  No coloque un gráfico del mes pasado junto a gráficos filtrados de un mes concreto del año.
* No mezcle medidas grandes y pequeñas en la misma escala, por ejemplo, en un gráfico de barras o líneas.  Por ejemplo, una medida puede estar en millones y otra en millares.  Con una escala tan grande, sería difícil comprender las diferencias de la medida en millares.  Si tiene que combinarlas, elija una visualización que permita usar un segundo eje.
* No abarrote los gráficos con etiquetas de datos innecesarias. Normalmente, los valores de los gráficos de barras se entienden bien sin necesidad de mostrar el número real.
* Preste atención a la manera de [ordenar los gráficos](consumer/end-user-change-sort.md).  Si desea llamar la atención sobre el número más alto o más bajo, ordene por medida.  Si desea que los usuarios puedan encontrar rápidamente una categoría determinada entre muchas otras categorías, ordene por eje.  
* Los gráficos circulares funcionan mejor si no superan las ocho categorías. Los valores no se pueden comparar en paralelo, y es más difícil hacerlo en un gráfico circular que en los gráficos de barras y columnas. Los gráficos circulares resultan útiles para ver las relaciones de una parte con respecto a un todo, no para comparar los elementos. Por último, los gráficos de medidor son ideales para mostrar el estado actual en el contexto de un objetivo.

Para más instrucciones específicas sobre la visualización, consulte [Tipos de visualización en Power BI](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).  

## <a name="learning-more-about-best-practice-dashboard-design"></a>Obtener más información sobre el diseño de paneles según los procedimientos recomendados
Si desea aprender a diseñar paneles fantásticos, considere la posibilidad de aprender los principios básicos de Gestalt sobre la percepción visual y la manera de comunicar claramente información accionable en contexto. Afortunadamente, existen numerosos recursos disponibles en nuestros blogs. Estos son algunos de nuestros libros favoritos:

* *Information dashboard design* , de Stephen Few  
* *Show me the numbers* , de Stephen Few  
* *Now you see it* , de Stephen Few  
* *Envisioning information* , de Edward Tufte  
* *Advanced presentations by design* , de Andrew Abela   

## <a name="next-steps"></a>Pasos siguientes
[Creación de un panel desde un informe](service-dashboard-create.md)  
[Conceptos básicos para los diseñadores en el servicio Power BI](service-basic-concepts.md)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
