---
title: "Configuraci&#243;n de la aplicaci&#243;n, Asistente para controles ActiveX MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Asistente para controles ActiveX MFC, configuración de la aplicación"
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Configuraci&#243;n de la aplicaci&#243;n, Asistente para controles ActiveX MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Use esta página del Asistente para controles ActiveX MFC para diseñar y agregar características básicas a un nuevo proyecto de control ActiveX MFC. Esta configuración se aplica a la aplicación en sí, pero no a las características o los elementos específicos del control.  
  
 **Licencia en tiempo de ejecución**  
 Seleccione esta opción para generar un archivo de licencia de usuario para distribuir con el control. La licencia es un archivo de texto *nombre\_proyecto*.lic. Este archivo debe estar en el mismo directorio que el archivo DLL del control para permitir la creación de una instancia del control en un entorno en tiempo de diseño. Normalmente distribuirá este archivo con el control, pero los clientes no lo distribuirán.  
  
 **Generar archivos de ayuda**  
 Seleccione esta opción para generar archivos de ayuda auxiliares y configurar el proyecto para incluir ayuda del control. Un proyecto predeterminado, creado sin esta opción, solo genera un cuadro **Acerca de** que se muestra cuando el usuario hace clic con el botón derecho en el control, presiona F1 o hace clic en **Ayuda** en el contenedor del control.  
  
> [!NOTE]
>  La forma de presentar la ayuda depende de cómo interactúa el control con su contenedor. Si quiere incluir la ayuda con el contenedor, debe controlar los mensajes emitidos entre el control y el contenedor para mostrar la ayuda de forma adecuada.  
  
 Al generar archivos de ayuda a través del asistente, el proyecto incluye lo siguiente:  
  
-   El archivo .vcxproj contiene código para compilar y configurar el archivo de ayuda cuando se compile el proyecto.  
  
-   El archivo *nombre\_proyecto\_pág\_prop*.cpp incluye una función [SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md) en el constructor.  
  
-   El archivo nombre\_proyecto.hpj, es el archivo de proyecto de ayuda que el compilador de ayuda usa para crear el archivo de ayuda del control ActiveX. El archivo .hpj es un archivo de texto que contiene la información sobre cómo compilar el archivo de ayuda y las rutas de acceso a los archivos adicionales \(por ejemplo, mapas de bits\) que incluye el archivo de ayuda.  
  
-   El proyecto incluye el directorio HLP, que contendrá los archivos de mapa de bits de ayuda del proyecto y el archivo de temas de ayuda \(*nombre\_proyecto*.rtf\). Este archivo de temas de ayuda contiene los temas de ayuda estándar para las propiedades, los eventos y los métodos admitidos por muchos controles ActiveX comunes. Puede editar el archivo .rtf para agregar o quitar temas de ayuda específicos.  
  
## Vea también  
 [Asistente para controles ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Nombres del control, Asistente para controles ActiveX MFC](../../mfc/reference/control-names-mfc-activex-control-wizard.md)   
 [Configuración del control, Asistente para controles ActiveX MFC](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)