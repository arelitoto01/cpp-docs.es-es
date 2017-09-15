---
title: Clase CPtrList | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8158e0acce04ee78ea07da26332f53613489653f
ms.contentlocale: es-es
ms.lasthandoff: 03/17/2017

---
# <a name="cptrlist-class"></a>Clase CPtrList
Admite listas de punteros void.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Miembros  
 Las funciones miembro de `CPtrList` son similares a las funciones miembro de clase [CObList](../../mfc/reference/coblist-class.md). Debido a esta similitud, puede utilizar la documentación de referencia de `CObList` para obtener información específica de la función miembro. Siempre que vea un puntero `CObject` como un parámetro o un valor devuelto de función, utilice un puntero a `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 por ejemplo, se traduce en  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Comentarios  
 `CPtrList` incorpora la macro `IMPLEMENT_DYNAMIC` para admitir el acceso a tipos en tiempo de ejecución y el volcado en un objeto `CDumpContext`. Si se necesita un volcado de elementos de lista de punteros individuales, se debe establecer la profundidad del contexto de volcado en 1 o un valor superior.  
  
 Las listas de punteros no se pueden serializar.  
  
 Cuando se elimina un objeto `CPtrList`, o cuando se quitan sus elementos, solo se quitan los punteros, no las entidades a las que hacen referencia.  
  
 Para obtener más información sobre el uso de `CPtrList`, vea el artículo [colecciones](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxcoll.h  
  
## <a name="see-also"></a>Vea también  
 [CObject (clase)](../../mfc/reference/cobject-class.md)   
 [Gráfico de jerarquía](../../mfc/hierarchy-chart.md)   
 [CObList (clase)](../../mfc/reference/coblist-class.md)
