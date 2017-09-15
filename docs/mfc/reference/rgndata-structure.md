---
title: RGNDATA (estructura) | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
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
ms.openlocfilehash: 93a7c79f175e22dcb0b40cb39b157cfe21a98e93
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="rgndata-structure"></a>RGNDATA (Estructura)
El `RGNDATA` estructura contiene un encabezado y una matriz de rectángulos que componen una región. Estos rectángulos, ordenados de arriba abajo de izquierda a derecha, no se superponen.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Parámetros  
 *rdh*  
 Especifica un [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) estructura. (Para obtener más información sobre esta estructura, vea la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) Los miembros de esta estructura de especifican el tipo de región (ya sea rectangular o trapezoidal), el número de rectángulos que componen la región, el tamaño del búfer que contiene las estructuras del rectángulo, y así sucesivamente.  
  
 `Buffer`  
 Especifica un búfer de tamaño arbitrario que contiene el [RECT](../../mfc/reference/rect-structure1.md) estructuras que constituyen la región.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** wingdi.h  
  
## <a name="see-also"></a>Vea también  
 [Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

