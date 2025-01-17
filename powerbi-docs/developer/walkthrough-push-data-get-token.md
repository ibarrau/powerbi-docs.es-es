---
title: Obtener un token de acceso de autenticación
description: Tutorial para insertar datos - Obtener un token de acceso de autenticación
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 4a0b0f5e7d697c137da343576d05fbcc91b4a4f7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710351"
---
# <a name="step-2-get-an-authentication-access-token"></a>Paso 2: Obtener un token de acceso de autenticación

Este artículo forma parte de un tutorial paso a paso para [insertar datos en un conjunto de datos](walkthrough-push-data.md).

En el **paso 1** de Insertar datos en un conjunto de datos, [Registrar la aplicación con Azure AD](walkthrough-push-data-register-app-with-azure-ad.md), registró una aplicación de cliente en Azure AD. En este paso, obtendrá un token de acceso de autenticación. Las aplicaciones de Power BI se integran con **Azure AD** para proporcionar un inicio de sesión seguro y una autorización para la aplicación. Un token se usa para autenticarse en **Azure AD** y obtener acceso a los recursos de Power BI.

Aquí se indica cómo obtener un token de acceso de autenticación.

## <a name="get-an-authentication-access-token"></a>Obtener un token de acceso de autenticación

> **NOTA**: Antes de comenzar, asegúrese de que ha seguido los pasos anteriores del tutorial [Insertar datos en un conjunto de datos](walkthrough-push-data.md).

1. En Visual Studio (2015 o posterior), cree un **aplicación de consola** proyecto.
2. Instale la [Biblioteca de autenticación de Azure AD para el paquete NuGet de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727). Para obtener un token de seguridad de autenticación en una aplicación de .NET, use este paquete. Aquí se muestra cómo instalar el paquete:

     a. En Visual Studio (2015 o posterior), elija **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.

     b. En **Consola del Administrador de paquetes**, escriba Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Agregue el código siguiente a la clase Program {...}.
4. Reemplace "{ClientID}" por el valor de **Client ID** que obtuvo al registrar la aplicación. Consulte [Registrar una aplicación con Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. Después de instalar el paquete de Microsoft.IdentityModel.Clients.ActiveDirectory, agregue **using Microsoft.IdentityModel.Clients.ActiveDirectory;** a Program.cs.
6. Ejecute la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver una cadena de token en la ventana de consola.

**Ejemplo de código para obtener un token de seguridad de autenticación**

Agregue este código a Program {...}.

* Una variable de token para llamar a las operaciones:
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* En static void Main(string[] args):
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Agregue un método GetToken():

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Después de obtener un token de autenticación, puede llamar a cualquier operación de Power BI. En el siguiente paso se muestra cómo llamar a la operación [PostDataSet](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) para crear un conjunto de datos para insertar datos en un panel.

El siguiente paso muestra cómo [crear un conjunto de datos en Power BI](walkthrough-push-data-create-dataset.md).

A continuación se muestra la [lista de código completa](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Lista de código completa

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```

[Paso siguiente >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Pasos siguientes

[Creación de un conjunto de datos en Power BI](walkthrough-push-data-create-dataset.md)  
[Registrar una aplicación con Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Biblioteca de autenticación de Azure AD para el paquete .NET de NuGet](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Inserción de datos en un conjunto de datos de Power BI](walkthrough-push-data.md)  
[Información general sobre la API de REST de Power BI](overview-of-power-bi-rest-api.md)  
[Referencia de la API de REST de Power BI](https://docs.microsoft.com/rest/api/power-bi/)  
¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)