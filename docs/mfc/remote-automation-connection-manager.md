---
title: "Administrador de conexiones de automatización remota | Documentos de Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation clients [MFC], configuring for Remote Automation
- registry [MFC], remote Automation
- Automation servers [MFC], configuring for Remote Automation
- Remote Automation Connection Manager [MFC]
- Remote Automation [MFC], configuring client and server machines
- RAC Manager tool [MFC]
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf316653b2f968fd5373c6265bb4f3f3ef3b0ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="remote-automation-connection-manager"></a>Administrador de conexiones de automatización remota
Para configurar equipos cliente y servidor, debe realizar cambios en el registro. En lugar de hacerlo manualmente, es mucho más fácil de usar la herramienta Administrador de conexiones de automatización remota (RAC). Esta herramienta, RACMGR32. EXE, junto con el archivo RACREG32. DLL, debe copiarse en cualquier directorio que elija. Si lo pone en la ruta de acceso, se puede ejecutar desde la barra de tareas mediante la ejecución. Como alternativa, puede crear un acceso directo o colocar una referencia a él en el menú Inicio.  
  
 RACMGR32 está escrita en Visual Basic y, por tanto, necesita algunos Visual Basic admite archivos DLL. Estos archivos se colocan en el mismo directorio que RACMGR32. Archivo EXE en el CD-ROM. Las versiones de estos archivos que se instalan con el programa de instalación de Visual C++ Enterprise Edition son equivalentes o más recientes que las que se incluye con Visual Basic Enterprise Edition 5.0. La instalación de Visual C++ copia las nuevas versiones de los archivos de Visual Basic en el directorio del sistema. Para Windows 9 x este directorio suele ser C:\Windows\System. Para Windows NT y Windows 2000, suele ser C:\WINNT\system32. El programa de instalación también registra estos archivos con el sistema operativo. Puede quitarlos de la instalación de Visual Basic.  
  
## <a name="see-also"></a>Vea también  
 [Administrador de automatización (MFC)](../mfc/automation-manager-mfc.md)   
 [Componentes de usuario de automatización remota](../mfc/remote-automation-user-components.md)   
 [Instalación de automatización remota](../mfc/remote-automation-installation.md)
