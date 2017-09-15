---
title: goto e instrucciones con etiquetas (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 2e42906c932375ec62597868f7c106712bd25cbc
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="goto-and-labeled-statements-c"></a>goto e instrucciones con etiquetas (C)
La instrucción `goto` transfiere el control a una etiqueta. La etiqueta especificada debe estar en la misma función y puede aparecer delante de una sola instrucción en la misma función.  
  
## <a name="syntax"></a>Sintaxis  
 *statement*:  
 *labeled-statement*  
  
 *jump-statement*  
  
 *jump-statement*:  
 **goto**  *identifier*  **;**  
  
 *labeled-statement*:  
 *identifier*  **:**  *statement*  
  
 Una etiqueta de instrucción solo tiene sentido en una instrucción `goto`; en cualquier otro contexto, una instrucción con etiqueta se ejecuta sin tener en cuenta la etiqueta.  
  
 Un elemento *jump-statement* debe estar en la misma función y puede aparecer delante de una sola instrucción en la misma función. El conjunto de nombres de *identifier* que siguen a `goto` tiene su propio espacio de nombres, por lo que los nombres no interfieren con otros identificadores. Las etiquetas no se pueden volver a declarar. Para más información, vea [Espacios de nombres](../c-language/name-spaces.md).  
  
 Una práctica de programación recomendada es usar la instrucción **break**, **continue** y `return` en lugar de `goto` siempre que sea posible. Como la instrucción **break** solo sale de un nivel del bucle, puede ser necesario usar `goto` para salir de un bucle profundamente anidado.  
  
 En este ejemplo se muestra la instrucción `goto`:  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 En este ejemplo, una instrucción `goto` transfiere el control al punto con la etiqueta `stop` cuando `i` es igual a 5.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones](../c-language/statements-c.md)