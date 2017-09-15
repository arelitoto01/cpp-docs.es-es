---
title: Suma (+) | Microsoft Docs
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
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
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
ms.openlocfilehash: 021f7099c6028f4f94dbb37b34ce165c0324c329
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="addition-"></a>Suma (+)
El operador de suma (**+**) hace que los dos operandos se sumen. Ambos operandos pueden ser tipos enteros o de punto flotante, o un operando puede ser un puntero y el otro un entero.  
  
 Cuando se suma un entero a un puntero, el valor entero (*i*) se convierte multiplicándolo por el tamaño del valor que direcciona el puntero. Después de la conversión, el valor entero representa las posiciones de memoria *i*, donde cada posición tiene la longitud especificada por el tipo de puntero. Cuando el valor entero convertido se suma al valor del puntero, el resultado es un nuevo valor de puntero que representa las posiciones de dirección *i* de la dirección original. El nuevo valor de puntero direcciona un valor del mismo tipo que el valor del puntero original y, por consiguiente, es igual que la indexación de matrices (vea [Matrices unidimensionales](../c-language/one-dimensional-arrays.md) y [Matrices multidimensionales](../c-language/multidimensional-arrays-c.md)). Si el puntero de la suma apunta fuera de la matriz, excepto en la primera ubicación más allá de la parte alta, el resultado es indefinido. Para más información, vea [Aritmética de punteros](../c-language/pointer-arithmetic.md).  
  
## <a name="see-also"></a>Vea también  
 [Operadores de adición de C](../c-language/c-additive-operators.md)