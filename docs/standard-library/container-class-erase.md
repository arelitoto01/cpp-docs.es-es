---
title: Clase de contenedor::erase | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: aeb81554bdc50db44e9e8d4ee66369149eceb875
ms.contentlocale: es-es
ms.lasthandoff: 04/04/2017

---
# <a name="container-classerase"></a>Clase de contenedor::erase
> [!NOTE]
>  Este tema se incluye en la documentación de Visual C++ como un ejemplo no funcional de los contenedores usados en la biblioteca estándar de C++. Para obtener más información, vea [Contenedores de la biblioteca estándar de C++](../standard-library/stl-containers.md).  
  
 Borra un elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
 
    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,  
    iterator last);
```  
  
## <a name="remarks"></a>Comentarios  
 La primera función miembro quita el elemento de la secuencia controlada señalada por *_Where*. La segunda función miembro quita los elementos de la secuencia controlada en el intervalo [`first`, `last`). Ambas devuelven un iterador que designa el primer elemento que permanece más allá de los elementos quitados, o [end](../standard-library/container-class-end.md) si no existe ese elemento.  
  
 Las funciones miembro producen una excepción solo si una operación de copia produce una excepción.  
  
## <a name="see-also"></a>Vea también  
 [Sample Container (Clase)](../standard-library/sample-container-class.md)
