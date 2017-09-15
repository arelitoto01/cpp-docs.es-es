---
title: Declarar una Variable basada en la nueva clase de Control | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables, control classes
- control classes, variables
- classes [C++], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: a5777019ca87616fbb7c6a0d27140b3fabbf7fde
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Declarar una variable basada en una clase de control nueva
Una vez haya creado una clase de control MFC, puede declarar una variable basada en él. Para proporcionar un contexto para la nueva variable, debe abrir el editor de cuadro de diálogo y editar el cuadro de diálogo en el que desea utilizar el control reutilizable. Además, el cuadro de diálogo ya debe tener una clase asociada a él. Para obtener información acerca de cómo utilizar el editor de cuadro de diálogo, vea [Editor de cuadro de diálogo](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Para declarar una variable basada en una clase reutilizable  
  
1.  Mientras el cuadro de diálogo, arrastre un control del mismo tipo que la clase base del nuevo control desde la barra de herramientas de controles en el cuadro de diálogo.  
  
2.  Coloque el puntero del mouse sobre el control arrastrado.  
  
3.  Mantenga presionada la tecla CTRL y haga doble clic en el control.  
  
     El [agregar variables miembro](../../ide/add-member-variable-wizard.md) aparece el cuadro de diálogo.  
  
4.  En el **acceso** , seleccione el acceso correcto para el control.  
  
5.  Haga clic en el **variable de Control** casilla de verificación.  
  
6.  En el **nombre de Variable** , escriba un nombre.  
  
7.  En **categoría**, haga clic en **Control**.  
  
8.  En el **Id. de Control** lista, elija el control que agregó. El **tipo de Variable** lista debe mostrar el tipo de variable correcto y el **tipo de Control** cuadro debe mostrar el tipo de control correcto.  
  
9. En el **comentario** , agregue cualquier comentario que desee que aparezca en el código.  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Asignar mensajes a funciones](../../mfc/reference/mapping-messages-to-functions.md)   
 [Agregar funcionalidad con los asistentes para código](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Agregar una clase](../../ide/adding-a-class-visual-cpp.md)   
 [Agregar una función miembro](../../ide/adding-a-member-function-visual-cpp.md)   
 [Agregar una Variable miembro](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Reemplazar una función Virtual](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Controlador de mensajes MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navegar por la estructura de clases](../../ide/navigating-the-class-structure-visual-cpp.md)
