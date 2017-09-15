---
title: Conversiones de tipos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data type conversion [C++], type-cast conversions
- conversions [C++], type-cast
- type casts
- explicit type conversions
- type casts [C++], about type-cast conversion
- type-cast conversions [C++]
ms.assetid: 57ab5902-f12f-4326-a2f6-6282f1d4025a
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b67b6beeb235585715db9c0ba9cbd589922de467
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="type-cast-conversions"></a>Conversiones de tipos
Puede utilizar conversiones de tipo para convertir tipos explícitamente.  
  
 **Sintaxis**  
  
 *cast-expression*:  
 *unary expression*  
  
 **(**  *type-name*  **)**  *cast-expression*  
  
 *type-name*:  
 *specifier-qualifier-list abstract-declarator* opt  
  
 El elemento *type-name* es un tipo y el elemento *cast-expression* es un valor que se va a convertir a ese tipo. Una expresión con una conversión de tipo no es un valor L. El elemento *cast-expression* se convierte como si se hubiera asignado a una variable de tipo *type-name*. Las reglas de conversión de las asignaciones (descritas en [Conversiones de asignación](../c-language/assignment-conversions.md)) se aplican a las conversiones de tipo. En la tabla siguiente se muestran los tipos que se pueden convertir a cualquier tipo especificado.  
  
### <a name="legal-type-casts"></a>Conversiones de tipos válidas  
  
|Tipos de destino|Posibles orígenes|  
|-----------------------|-----------------------|  
|Tipos enteros|Cualquier tipo entero o tipo de punto flotante o puntero a un objeto|  
|Punto flotante|Cualquier tipo aritmético|  
|Un puntero a un objeto o (**void \***)|Cualquier tipo entero, (**void \***), un puntero a un objeto o un puntero de función|  
|Puntero de función|Cualquier tipo entero, un puntero a un objeto o un puntero de función|  
|Una estructura, unión o matriz|Ninguna|  
|Un tipo void|Cualquier tipo|  
  
 Cualquier identificador se puede convertir al tipo `void`. Sin embargo, si el tipo especificado en una expresión de conversión de tipos no es `void`, el identificador que se va a convertir a ese tipo no puede ser una expresión `void`. Cualquier expresión se puede convertir a `void`, pero una expresión de tipo `void` no se puede convertir a ningún otro tipo. Por ejemplo, una función con el tipo de valor devuelto `void` no puede devolver un valor convertido a otro tipo.  
  
 Tenga en cuenta que una expresión **void \*** tiene un puntero de tipo a `void`, no un tipo `void`. Si un objeto se convierte al tipo `void`, la expresión resultante no se puede asignar a ningún elemento. Asimismo, un objeto de conversión de tipo no es un valor L aceptable, por lo que no se puede realizar ninguna asignación a un objeto de conversión de tipo.  
  
 **Específicos de Microsoft**  
  
 Una conversión de tipo puede ser una expresión de valor L siempre y cuando el tamaño del identificador no cambie. Para obtener información sobre las expresiones de valor L, vea [Expresiones de valor L y de valor R](../c-language/l-value-and-r-value-expressions.md).  
  
 **FIN de Específicos de Microsoft**  
  
 Puede convertir una expresión al tipo `void` con una conversión, pero la expresión resultante solo se puede utilizar donde no se requiera un valor. Un puntero de objeto convertido a **void \*** y después al tipo original volverá a su valor original.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos](../c-language/type-conversions-c.md)