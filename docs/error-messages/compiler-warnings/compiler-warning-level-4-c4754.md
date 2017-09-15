---
title: "Advertencia del compilador (nivel 4) C4754 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4754"
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Advertencia del compilador (nivel 4) C4754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Las reglas de conversión para las operaciones aritméticas de una comparación significan que una bifurcación no puede ejecutarse.  
  
 Se emite la advertencia C4754 porque el resultado de la comparación es siempre el mismo.  Esto indica que una de las bifurcaciones de la condición nunca se ejecuta, probablemente porque la expresión de entero asociada es incorrecta.  Este defecto de código aparece en las comprobaciones incorrectas de desbordamiento con enteros en la arquitectura de 64 bits.  
  
 Las reglas de conversión de enteros son complejas y hay muchos problemas sutiles.  Como alternativa a corregir cada advertencia C4754, puede actualizar el código para utilizar la [Biblioteca SafeInt](../../windows/safeint-library.md).  
  
## Ejemplo  
 Este ejemplo genera el error C4754:  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 La suma `a + b` podría producir un desbordamiento aritmético antes de que el resultado se convierta hacia arriba a un valor de 64 bits y se asigne a la variable `x` de 64 bits.  Esto significa que la comprobación en `x` es redundante y nunca detectará un desbordamiento.  En este caso, el compilador emite esta advertencia:  
  
  **Advertencia C4754: Las reglas de conversión para las operaciones aritméticas de la comparación en C4754a.cpp \(7\) significan que una bifurcación no puede ejecutarse.  Convierta "\(a \+ ...\)" en "ULONG64" \(o un tipo similar de 8 bytes\).**  Para eliminar la advertencia, puede cambiar la instrucción de asignación para convertir los operandos en valores de 8 bytes:  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## Ejemplo  
 El ejemplo siguiente también genera el error C4754.  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 El operador `sizeof()` devuelve un valor `size_t` cuyo tamaño depende de la arquitectura.  El código de ejemplo funciona en arquitecturas de 32 bits cuyo valor `size_t` es un tipo de 32 bits.  Sin embargo, en las arquitecturas de 64 bits, `size_t` es un tipo de 64 bits.  Las reglas de conversión para los enteros significan que `a` se convierte hacia arriba a un valor de 64 bits en la expresión `a + b < a` como si se hubiera escrito `(size_t)a + (size_t)b < (size_t)a`.  Cuando `a` y `b` son enteros de 32 bits, la operación de suma de 64 bits nunca puede desbordarse y la restricción no se mantiene.  Como resultado, el código nunca detecta una condición de desbordamiento de enteros en la arquitectura de 64 bits.  Este ejemplo hace que el compilador emita esta advertencia:  
  
  **Advertencia C4754: Las reglas de conversión para las operaciones aritméticas de la comparación en C4754b.cpp \(7\) significan que una bifurcación no puede ejecutarse.  Convierta "4" a "ULONG" \(o un tipo similar de 4 bytes\).**  Observe que el mensaje de advertencia muestra explícitamente el valor constante 4 en lugar de la cadena original. En el momento en que el análisis de la advertencia encuentra código incorrecto, `sizeof(unsigned long)` ya se ha convertido en una constante.  Por lo tanto, puede que tenga que rastrear qué expresión del código fuente está asociada al valor constante en el mensaje de advertencia.  Los orígenes de código más comunes que se resuelven como constantes en los mensajes de advertencia C4754 son expresiones como `sizeof(TYPE)` y `strlen(szConstantString)`.  
  
 En este caso, el código corregido se parecería al siguiente:  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **Nota** El número de línea al que se hace referencia en las advertencias del compilador es la última línea de una instrucción.  En un mensaje de advertencia sobre una instrucción condicional compleja que ocupa varias líneas, la línea que tiene el defecto de código puede estar varias líneas antes de la línea que se notifica.  Por ejemplo:  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
  
```