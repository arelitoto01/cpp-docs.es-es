---
title: Agregar una nueva interfaz en un proyecto ATL | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 10b252047a7bae1bbd54e854445dcd90db06a341
ms.contentlocale: es-es
ms.lasthandoff: 03/31/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Agregar una nueva interfaz en un proyecto ATL
Cuando se agrega una interfaz para el objeto o un control, cree funciones auxiliares para cada método en esa interfaz. En el objeto o el control, puede agregar únicamente las interfaces que se encuentra actualmente en una biblioteca de tipos existente. Además, la clase en la que agregar la interfaz debe implementar la [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) macro o, si el proyecto tiene como atributo, debe tener la `coclass` atributo.  
  
 Puede agregar una nueva interfaz para el control de una de dos maneras: manualmente o mediante los asistentes de código de la vista de clases.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Para utilizar los asistentes para código en la vista de clases para agregar una interfaz a un objeto existente o control  
  
1.  En [vista de clases](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), haga clic en el nombre de clase de un control. Por ejemplo, un control total o control compuesto o cualquier otra clase de control que implemente una macro BEGIN_COM_MAP en su archivo de encabezado.  
  
2.  En el menú contextual, haga clic en **agregar**y, a continuación, haga clic en **Implementar interfaz**.  
  
3.  Seleccione las interfaces que se va a implementar en el [Asistente para implementar interfaces](../../ide/implement-interface-wizard.md). Si la interfaz no existe en cualquier biblioteca de tipos disponible, a continuación, que debe agregarla manualmente al archivo .idl.  
  
### <a name="to-add-a-new-interface-manually"></a>Para agregar una nueva interfaz manualmente  
  
1.  Agregue la definición de la nueva interfaz al archivo .idl.  
  
2.  Derive el objeto o el control de la interfaz.  
  
3.  Crear un nuevo [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) para la interfaz o, si el proyecto tiene como atributos, agregue el `coclass` atributo.  
  
4.  Implementar los métodos en la interfaz.  
  
## <a name="see-also"></a>Vea también  
 [Asistente para proyectos ATL](../../atl/reference/atl-project-wizard.md)   
 [Tipos de proyecto de Visual C++](../../ide/visual-cpp-project-types.md)   
 [Crear proyectos de escritorio con asistentes para aplicaciones](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programar con ATL y el código de tiempo de ejecución de C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Aspectos básicos de los objetos ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Configuraciones de proyecto ATL predeterminadas](../../atl/reference/default-atl-project-configurations.md)

