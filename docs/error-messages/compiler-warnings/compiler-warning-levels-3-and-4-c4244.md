---
title: Compilador (niveles 3 y 4) de la advertencia C4244 | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: 16
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ffc1f0012d7b65ab959503c3845b1f7a04268676
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Advertencia del compilador (niveles 3 y 4) C4244
'conversion': conversión de 'type1' a 'type2', posible pérdida de datos  
  
 Un tipo de entero se convierte en un tipo de entero más pequeño. Esta es una advertencia de nivel&4; si *type1* es `int` y *type2* es menor que `int`. De lo contrario, es de nivel 3 (asigna un valor de tipo [__int64](../../cpp/int8-int16-int32-int64.md) a una variable de tipo `unsigned int`). Se ha producido una posible pérdida de datos.  
  
 Si recibe el error C4244, debe cambiar el programa para que use tipos compatibles o agregar lógica al código, para asegurarse de que el intervalo de valores posibles sea siempre compatible con los tipos que usa.  
  
 C4244 también puede producirse en el nivel 2; consulte [advertencia del compilador (nivel 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) para obtener más información.  
  
 Puede que la conversión tenga problemas debido a conversiones implícitas.  
  
 El siguiente ejemplo genera C4244:  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 Para obtener más información, consulte [conversiones aritméticas usuales](../../c-language/usual-arithmetic-conversions.md).  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 La advertencia C4244 puede producirse al generar código para destinos de 64 bits que no genera la advertencia al compilar destinos de 32 bits. Por ejemplo, una diferencia entre punteros es una cantidad de 32 bits en plataformas de 32 bits, pero una cantidad de 64 bits en plataformas de 64 bits.  
  
 En el ejemplo siguiente se genera C4244 cuando se compila para destinos de 64 bits:  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```