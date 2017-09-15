---
title: "Implementaci&#243;n de barra de herramientas de MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mapas de bits [C++], barra de herramientas"
  - "botones [C++], barras de herramientas de MFC"
  - "CToolBar (clase), crear barras de herramientas"
  - "CToolBarCtrl (clase), implementar barras de herramientas"
  - "acoplamiento de barras de herramientas"
  - "barras de herramientas flotantes"
  - "barras de herramientas de MFC"
  - "información sobre herramientas [C++], habilitar"
  - "controles de barra de herramientas [MFC]"
  - "barras de herramientas [C++]"
  - "barras de herramientas [C++], crear"
  - "barras de herramientas [C++], acoplar"
  - "barras de herramientas [C++], flotante"
  - "barras de herramientas [C++], implementar barras de herramientas de MFC"
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Implementaci&#243;n de barra de herramientas de MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Una barra de herramientas es una [barra de control](../mfc/control-bars.md) que contiene imágenes de mapa de bits de controles.  Estas imágenes se comportan como botones de comando, casillas o botones de radio.  MFC suministra la clase [CToolbar](../mfc/reference/ctoolbar-class.md) para administrar las barras de herramientas.  
  
 Si se habilita, los usuarios de las barras de herramientas de MFC pueden acoplarlas al borde de una ventana o hacerlas "flotar" en cualquier parte dentro de la ventana de la aplicación.  MFC no admite barras de herramientas personalizables como las del entorno de desarrollo.  
  
 MFC admite también información sobre herramientas: pequeñas ventanas emergentes que describen el propósito de un botón de la barra de herramientas cuando se coloca el mouse sobre el botón.  De forma predeterminada, cuando el usuario presiona un botón de la barra de herramientas, aparece una cadena de estado en la barra de estado \(si hay una\).  Se puede activar la actualización de la barra de estado al "sobrevolar" para mostrar la cadena de estado cuando el mouse se coloca sobre el botón sin presionarlo.  
  
> [!NOTE]
>  A partir de la versión 4.0 de MFC, las barras de herramientas y la información sobre herramientas se implementan con la funcionalidad de Windows 95 y versiones posteriores, en lugar de usar la implementación anterior específica de MFC.  
  
 Por compatibilidad con versiones anteriores, MFC conserva la implementación más antigua de la barra de herramientas en la clase **COldToolBar**.  En la documentación de versiones anteriores de MFC se describe **COldToolBar** en `CToolBar`.  
  
 Puede crear la primera barra de herramientas de un programa si selecciona la opción Barra de herramientas en el Asistente para aplicaciones.  También puede crear barras de herramientas adicionales.  
  
 En este artículo se presenta lo siguiente:  
  
-   [Botones de barra de herramientas](#_core_toolbar_buttons)  
  
-   [Barras de herramientas de acoplamiento y flotantes](#_core_docking_and_floating_toolbars)  
  
-   [Barras de herramientas e información sobre herramientas](#_core_toolbars_and_tool_tips)  
  
-   [Clases CToolBar y CToolBarCtrl](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [Mapa de bits de la barra de herramientas](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> Botones de barra de herramientas  
 Los botones de una barra de herramientas son análogos a los elementos de un menú.  Ambos tipos de objetos de la interfaz de usuario generan comandos, que se pueden administrar mediante las funciones de controlador que el programa proporciona.  Los botones de la barra de herramientas duplican a menudo la funcionalidad de los comandos de menú y proporcionan una interfaz de usuario alternativa para la misma funcionalidad.  Para organizar esta duplicación de forma sencilla, asigne el mismo id. al botón y al elemento de menú.  
  
 Puede hacer que los botones de una barra de herramientas aparezcan y se comporten como botones de comando, las casillas o los botones de radio.  Para obtener más información, vea la clase [CToolBar](../mfc/reference/ctoolbar-class.md).  
  
##  <a name="_core_docking_and_floating_toolbars"></a> Barras de herramientas de acoplamiento y flotantes  
 Una barra de herramientas de MFC puede:  
  
-   Mantenerse estática a lo largo de un lado de la ventana primaria.  
  
-   Arrastrarse y "acoplarse", o asociarse, a cualquier lado o lados de la ventana primaria que el usuario especifique.  
  
-   "Flotar", o desasociarse de la ventana marco, en su propia ventana minimarco para que el usuario pueda moverla a cualquier posición adecuada.  
  
-   Cambiar de tamaño mientras flota.  
  
 Para obtener más información, vea el artículo [Barras de herramientas de acoplamiento y flotantes](../mfc/docking-and-floating-toolbars.md).  
  
##  <a name="_core_toolbars_and_tool_tips"></a> Barras de herramientas e información sobre herramientas  
 También se puede hacer que las barras de herramientas de MFC muestren "información sobre herramientas", que son ventanas emergentes minúsculas que contienen una breve descripción de texto del propósito de un botón de la barra de herramientas.  Cuando el usuario mueve el mouse sobre un botón de la barra de herramientas, la ventana de información sobre herramientas emerge para proporcionar una sugerencia.  Para obtener más información, vea el artículo [Información sobre herramientas de la barra de herramientas](../mfc/toolbar-tool-tips.md).  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> Clases CToolBar y CToolBarCtrl  
 Las barras de herramientas de la aplicación se administran mediante la clase [CToolBar](../mfc/reference/ctoolbar-class.md).  A partir de la versión 4.0 de MFC, `CToolBar` se ha implementado de nuevo para utilizar el control común de barra de herramientas que está disponible en Windows 95 o versiones posteriores y en Windows NT versión 3.51 o versiones posteriores.  
  
 Esta nueva implementación da lugar a menos código MFC para las barras de herramientas, porque MFC utiliza la compatibilidad con el sistema operativo.  La nueva implementación también mejora la capacidad.  Puede utilizar las funciones miembro de `CToolBar` para manipular las barras de herramientas o puede obtener una referencia al objeto subyacente [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) y llamar a sus funciones miembro para la personalización y funcionalidad adicionales de la barra de herramientas.  
  
> [!TIP]
>  Si ha invertido mucho en la implementación MFC anterior de `CToolBar`, esa compatibilidad sigue estando disponible.  Vea el artículo [Usar las barras de herramientas anteriores](../mfc/using-your-old-toolbars.md).  
  
 Vea también el ejemplo general de MFC [DOCKTOOL](../top/visual-cpp-samples.md).  
  
##  <a name="_core_the_toolbar_bitmap"></a> Mapa de bits de la barra de herramientas  
 Una vez construido, un objeto `CToolBar` carga un solo mapa de bits que contiene una imagen de cada botón para crear la imagen de la barra de herramientas.  El Asistente para aplicaciones crea un mapa de bits de barra de herramientas estándar que se puede personalizar con el [editor de barras de herramientas](../mfc/toolbar-editor.md) de Visual C\+\+.  
  
### ¿Sobre qué desea obtener más información?  
  
-   [Fundamentos de la barra de herramientas](../mfc/toolbar-fundamentals.md)  
  
-   [Barras de herramientas de acoplamiento y flotantes](../mfc/docking-and-floating-toolbars.md)  
  
-   [Información sobre herramientas de la barra de herramientas](../mfc/toolbar-tool-tips.md)  
  
-   [Trabajar con el control ToolBar](../mfc/working-with-the-toolbar-control.md)  
  
-   [Usar las barras de herramientas anteriores](../mfc/using-your-old-toolbars.md)  
  
-   Clases [CToolBar](../mfc/reference/ctoolbar-class.md) y [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
## Vea también  
 [Barras de herramientas](../mfc/toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)