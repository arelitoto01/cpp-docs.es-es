---
title: Puntos de secuencia de C | Microsoft Docs
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
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
caps.latest.revision: 6
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
ms.openlocfilehash: 85e9d8c04280b6f40081b1362a46bf27b62bcc28
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="c-sequence-points"></a>Puntos de secuencia de C
Entre "puntos de secuencia" consecutivos, una expresión solo puede modificar una vez el valor de un objeto. El lenguaje C define los puntos de secuencia siguientes:  
  
-   Operando izquierdo del operador AND lógico (**&&**). El operando izquierdo del operador AND lógico se evalúa totalmente y todos los efectos secundarios se completan antes de continuar. Si el operando izquierdo se evalúa como false (0), el otro operando no se evalúa.  
  
-   Operando izquierdo del operador OR lógico (`||`). El operando izquierdo del operador OR lógico se evalúa totalmente y todos los efectos secundarios se completan antes de continuar. Si el operando izquierdo se evalúa como true (distinto de cero), el otro operando no se evalúa.  
  
-   Operando izquierdo del operador de coma. El operando izquierdo del operador de coma se evalúa totalmente y todos los efectos secundarios se completan antes de continuar. Los dos operandos del operador de coma se evalúan siempre. Observe que el operador de coma en una llamada de función no garantiza un orden de evaluación.  
  
-   Operador de llamada de función. Todos los argumentos de una función se evalúan y todos los efectos secundarios se completan antes de la entrada a la función. No se especifica ningún orden de evaluación entre los argumentos.  
  
-   Primer operando del operador condicional. El primer operando del operador condicional se evalúa totalmente y todos los efectos secundarios se completan antes de continuar.  
  
-   El final de una expresión completa de inicialización (es decir, una expresión que no forma parte de otra expresión tal como el final de una inicialización en una instrucción de declaración).  
  
-   La expresión de una instrucción de expresión. Las instrucciones de expresión constan de una expresión opcional seguida de un punto y coma (**;**). La expresión se evalúa para sus efectos secundarios y hay un punto de secuencia después de esta evaluación.  
  
-   La expresión de control de una instrucción de selección (**if** o `switch`). La expresión se evalúa completamente y todos los efectos secundarios se completan antes de que se ejecute el código dependiente de la selección.  
  
-   La expresión de control de una instrucción `while` o **do**. La expresión se evalúa completamente y todos los efectos secundarios se completan antes de que se ejecute ninguna instrucción de la siguiente iteración del bucle `while` o **do**.  
  
-   Cada una de las tres expresiones de una instrucción **for**. Las expresiones se evalúan completamente y todos los efectos secundarios se completan antes de que se ejecute ninguna instrucción de la siguiente iteración del bucle **for**.  
  
-   La expresión en una instrucción `return`. La expresión se evalúa completamente y todos los efectos secundarios se completan antes de devolver el control a la función de llamada.  
  
## <a name="see-also"></a>Vea también  
 [Evaluación de expresiones](../c-language/expression-evaluation-c.md)