---
title: Constantes de tipo entero de C | Microsoft Docs
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
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: dab1cb72b5914901808dc51f3a173a62a8924cfb
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="c-integer-constants"></a>Constantes de tipo entero de C
Una "constante de tipo entero" es un número decimal (base 10), octal (base 8) o hexadecimal (base 16) que representa un valor de tipo entero. Utilice las constantes de tipo entero para representar valores de tipo entero que no se pueden modificar.  
  
## <a name="syntax"></a>Sintaxis  
 *integer-constant*:  
 *decimal-constant integer-suffix* opt  
  
 *octal-constant integer-suffix* opt  
  
 *hexadecimal-constant integer-suffix* opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x**  *hexadecimal-digit*  
  
 **0X**  *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: uno de  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: uno de  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: uno de  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix* opt  
  
 *long-suffix unsigned-suffix* opt  
  
 *unsigned-suffix*: uno de  
 **u U**  
  
 *long-suffix*: uno de  
 **l L**  
  
 *64-bit integer-suffix*:  
 **i64**  
  
 Las constantes de tipo entero son positivas a menos que vayan precedidas de un signo menos (**-**). El signo menos se interpreta como el operador aritmético unario de negación. (Vea [Operadores aritméticos unarios](../c-language/unary-arithmetic-operators.md) para obtener información sobre este operador).  
  
 Si una constante entera comienza con **0x** o **0X**, es hexadecimal. Si empieza con el dígito **0**, es octal. En los demás casos, se supone que es decimal.  
  
 Las líneas siguientes son equivalentes:  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Los dígitos de una constante de tipo entero no se pueden separar con ningún carácter de espacio en blanco. En estos ejemplos se muestran constantes decimales, octales y hexadecimales válidas.  
  
```  
/* Decimal Constants */  
10  
132  
32179  
  
/* Octal Constants */  
012  
0204  
076663  
  
/* Hexadecimal Constants */  
0xa or 0xA  
0x84  
0x7dB3 or 0X7DB3  
```  
  
## <a name="see-also"></a>Vea también  
 [Constantes de C](../c-language/c-constants.md)