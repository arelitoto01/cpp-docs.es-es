---
title: "__sptr, __uptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__uptr_cpp"
  - "__sptr"
  - "__uptr"
  - "__sptr_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__sptr (modificador)"
  - "__uptr (modificador)"
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# __sptr, __uptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Específicos de Microsoft  
 Use el modificador `__sptr` o `__uptr` en una declaración de puntero de 32 bits para especificar cómo convierte el compilador un puntero de 32 bits en un puntero de 64 bits.  Un puntero de 32 bits se convierte, por ejemplo, cuando se asigna a una variable de puntero de 64 bits o se deshace la referencia en una plataforma de 64 bits.  
  
 La documentación de Microsoft para la compatibilidad con plataformas de 64 bits hace referencia a veces al bit más significativo de un puntero de 32 bits como el bit de signo.  De forma predeterminada, el compilador utiliza la extensión de signo para convertir un puntero de 32 bits en un puntero de 64 bits.  Es decir, los 32 bits menos significativos del puntero de 64 bits se establecen en el valor del puntero de 32 bits y los 32 bits más significativos se establecen en el valor del bit de signo del puntero de 32 bits.  Esta conversión produce resultados correctos si el bit de signo es 0, pero no si el bit de signo es 1.  Por ejemplo, la dirección de 32 bits 0x7FFFFFFF produce la dirección de 64 bits equivalente 0x000000007FFFFFFF, pero la dirección de 32 bits 0x80000000 cambia incorrectamente a 0xFFFFFFFF80000000.  
  
 El modificador `__sptr` o de puntero con signo especifica que una conversión de puntero establezca los bits más significativos de un puntero de 64 bits en el bit de signo del puntero de 32 bits.  El modificador `__uptr` o de puntero sin signo especifica que una conversión establezca los bits más significativos en cero.  Las declaraciones siguientes muestran los modificadores `__sptr` y `__uptr` utilizados con dos punteros incompletos, dos punteros completos con el tipo [\_\_ptr32](../cpp/ptr32-ptr64.md), y un parámetro de función.  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Use los modificadores `__sptr` y `__uptr` con declaraciones de puntero.  Use los modificadores en la posición de un [calificador de tipo de puntero](../c-language/pointer-declarations.md), lo que significa que el modificador debe seguir el asterisco.  No se puede usar los modificadores con [punteros a miembros](../cpp/pointers-to-members.md).  Los modificadores no afectan a las declaraciones que no son de puntero.  
  
 Si no usa el modificador `__sptr` o `__uptr` y habilita [Advertencia del compilador \(nivel 2\) C4826](../error-messages/compiler-warnings/compiler-warning-level-2-c4826.md), el compilador emite una advertencia cuando un puntero de 32 bits se convierte a 64 bits.  
  
## Ejemplo  
 El ejemplo siguiente declara punteros de 32 bits que usan los modificadores `__sptr` y `__uptr`, asigna cada puntero de 32 bits a una variable de puntero de 64 bits y muestra el valor hexadecimal de cada puntero de 64 bits.  El ejemplo se compila con el compilador de 64 bits nativo y se ejecuta en una plataforma de 64 bits.  
  
```  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
// Warning C4826 is off by default.  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
  **Mostrar cada puntero de 32 bits \(como un puntero de 64 bits sin signo\):**  
**p32d:       0000000087654321**  
**p32s:       0000000087654321**  
**p32u:       0000000087654321**  
**Mostrar el puntero 64 bits creado a partir de cada puntero de 32 bits:**  
**p32d: p64 \= FFFFFFFF87654321**  
**p32s: p64 \= FFFFFFFF87654321**  
**p32u: p64 \= 0000000087654321**   
## FIN de Específicos de Microsoft  
  
## Vea también  
 [Modificadores específicos de Microsoft](../cpp/microsoft-specific-modifiers.md)