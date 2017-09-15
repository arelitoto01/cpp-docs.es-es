---
title: Interfaz ICommandUI | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>Interfaz ICommandUI
Administra los comandos de la interfaz de usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[icommandui__Check](#check)|Establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Indica al mecanismo de enrutamiento de comandos para continuar el enrutamiento del mensaje actual por la cadena de controladores.|  
|[ICommandUI::Enabled](#enabled)|Habilita o deshabilita el elemento de la interfaz de usuario para este comando.|  
|[ICommandUI::ID](#id)|Obtiene el identificador del objeto de interfaz de usuario representado por la `ICommandUI` objeto.|  
|[ICommandUI::Index](#index)|Obtiene el índice del objeto de interfaz de usuario representado por la `ICommandUI` objeto.|  
|[ICommandUI::Radio](#radio)|Establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada.|  
|[ICommandUI::Text](#text)|Establece el texto del elemento de interfaz de usuario para este comando.|  
  
## <a name="remarks"></a>Comentarios  
 Esta interfaz proporciona métodos y propiedades que administran los comandos de la interfaz de usuario. `ICommandUI`es similar a [CCmdUI (clase)](../../mfc/reference/ccmdui-class.md), salvo que `ICommandUI` se utiliza para aplicaciones de MFC que interoperan con los componentes. NET.  
  
 `ICommandUI`se utiliza dentro de un `ON_UPDATE_COMMAND_UI` controlador en un [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-clase derivada. Cuando un usuario de una aplicación activa (activa o clics) se muestra un menú, cada elemento de menú como habilitado o deshabilitado. El destino de cada comando de menú proporciona esta información mediante la implementación de un `ON_UPDATE_COMMAND_UI` controlador. Para cada uno de los objetos de interfaz de usuario de comandos en la aplicación, utilice la ventana Propiedades para crear una entrada de mapa de mensajes y el prototipo de función para cada controlador.  
  
 Para obtener más información sobre cómo las `ICommandUI` interfaz se utiliza en el enrutamiento de comandos, consulte [Cómo: agregar el enrutamiento de comandos para el Control Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Para obtener más información sobre el uso de formularios Windows Forms, vea [mediante un Control de usuario de Windows Forms en MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Para obtener más información sobre cómo se administran los comandos de la interfaz de usuario en MFC, vea [CCmdUI (clase)](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada.
```
property UICheckState Check;
```
## <a name="remarks"></a>Comentarios  
Esta propiedad establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada. Establecer comprobación en los siguientes valores:  
- Desactive la casilla&0;  
- 1 Compruebe  
- 2 establecer indeterminado  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Indica al mecanismo de enrutamiento de comandos para continuar el enrutamiento del mensaje actual por la cadena de controladores.
```
void ContinueRouting();
```
## <a name="remarks"></a>Comentarios
Se trata de una función miembro avanzado que debe utilizarse junto con un controlador ON_COMMAND_EX que devuelve FALSE. Para obtener más información, consulte TN006 de nota técnica: mapas de mensajes.

## <a name="enabled"></a>ICommandUI::Enabled 
Habilita o deshabilita el elemento de la interfaz de usuario para este comando.
```
property bool Enabled;
```
## <a name="remarks"></a>Comentarios
Esta propiedad habilita o deshabilita el elemento de la interfaz de usuario para este comando. Establezca Enabled en True para habilitar el elemento, FALSE para deshabilitarla.

## <a name="id"></a>ICommandUI::ID  
Obtiene el identificador del objeto de interfaz de usuario representado por el objeto ICommandUI.
```
property unsigned int ID;
```
## <a name="remarks"></a>Comentarios
Esta propiedad obtiene el identificador (un identificador) de otro objeto de interfaz de usuario representado por el objeto ICommandUI, botón de barra de herramientas o el elemento de menú.

## <a name="index"></a>ICommandUI::Index   
Obtiene el índice del objeto de interfaz de usuario representado por el objeto ICommandUI.
```
property unsigned int Index;
```
## <a name="remarks"></a>Comentarios
Esta propiedad obtiene el índice (un identificador) de otro objeto de interfaz de usuario representado por el objeto ICommandUI, botón de barra de herramientas o el elemento de menú.

## <a name="radio"></a>ICommandUI::Radio 
Establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada.
```
property bool Radio;
```
## <a name="remarks"></a>Comentarios
Esta propiedad establece el elemento de la interfaz de usuario para este comando en el estado de verificación adecuada. Establecer Radio en True para habilitar el elemento; de lo contrario, FALSE.

## <a name="text"></a>ICommandUI::Text 
Establece el texto del elemento de interfaz de usuario para este comando.
```
property String^ Text;
```
## <a name="remarks"></a>Comentarios
Esta propiedad establece el texto del elemento de interfaz de usuario para este comando. Establecer texto a un identificador de cadena de texto.

## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxwinforms.h (definido en el ensamblado atlmfc\lib\mfcmifc80.dll)  
  
## <a name="see-also"></a>Vea también  
 [CCmdUI (clase)](../../mfc/reference/ccmdui-class.md)
