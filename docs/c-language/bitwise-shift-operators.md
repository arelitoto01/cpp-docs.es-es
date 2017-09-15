---
title: Operadores de desplazamiento bit a bit | Microsoft Docs
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
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
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
ms.openlocfilehash: 54cd2dad24563082c820999ff53e17b4d04380f7
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="bitwise-shift-operators"></a>Operadores de desplazamiento bit a bit
Los operadores de desplazamiento desplazan el primer operando a la izquierda (`<<`) o a la derecha (`>>`) el número de posiciones que especifica el segundo operando.  
  
## <a name="syntax"></a>Sintaxis  
 *shift-expression*:  
 *additive-expression*  
  
 *shift-expression*  `<<`  *additive-expression shift-expression*  `>>`  *additive-expression*  
  
 Ambos operandos deben ser valores enteros. Estos operadores realizan las conversiones aritméticas habituales; el tipo del resultado es el tipo del operando izquierdo después de la conversión.  
  
 Para los desplazamientos hacia la izquierda, los bits de la derecha desocupados se establecen en 0. Para los desplazamientos hacia la derecha, los bits de la izquierda desocupados se rellenan según el tipo del primer operando después de la conversión. Si el tipo es `unsigned`, se establecen en 0. Si no, se rellenan con copias del bit de signo. Para los operadores de desplazamiento a la izquierda sin desbordamiento, la instrucción  
  
```  
expr1 << expr2   
```  
  
 es equivalente a la multiplicación por 2<sup>expr2</sup>. Para los operadores de desplazamiento a la derecha,  
  
```  
expr1 >> expr2   
```  
  
 es equivalente a la división por 2<sup>expr2</sup> si `expr1` es sin signo o tiene un valor no negativo.  
  
 El resultado de una operación de desplazamiento es indefinido si el segundo operando es negativo o si el operando derecho es mayor o igual a la anchura en bits del operando izquierdo promovido.  
  
 Como las conversiones realizadas por los operadores de desplazamiento no proporcionan condiciones de desbordamiento o subdesbordamiento, la información puede perderse si el resultado de una operación de desplazamiento no se puede representar en el tipo del primer operando después de la conversión.  
  
```  
unsigned int x, y, z;  
  
x = 0x00AA;  
y = 0x5500;  
  
z = ( x << 8 ) + ( y >> 8 );  
```  
  
 En este ejemplo, `x` se desplaza a la izquierda ocho posiciones e `y` se desplaza a la derecha ocho posiciones. Los valores desplazados se suman, dando 0xAA55 y se asignan a `z`.  
  
 Cuando se desplaza a la derecha un valor negativo se produce la mitad del valor original, redondeado a la baja. Por ejemplo, -253 (binario 11111111 00000011) desplazado a la derecha un bit produce -127 (binario 11111111 10000001). Un 253 positivo, cuando se desplaza a la derecha, produce +126.  
  
 Los desplazamientos a la derecha conservan el bit de signo. Cuando un entero con signo se desplaza a la derecha, el bit más significativo permanece establecido. Cuando un entero sin signo se desplaza a la derecha, el bit más significativo se borra.  
  
## <a name="see-also"></a>Vea también  
 [Operadores de desplazamiento a la izquierda y a la derecha (>> y <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)