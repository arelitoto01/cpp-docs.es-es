---
title: "Funciones intr&#237;nsecas _InterlockedXor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedXor_nf"
  - "_InterlockedXor_np"
  - "_InterlockedXor64_HLERelease"
  - "_InterlockedXor8_acq"
  - "_InterlockedXor64_acq"
  - "_InterlockedXor64_rel"
  - "_InterlockedXor64_nf"
  - "_InterlockedXor_acq"
  - "_InterlockedXor16"
  - "_InterlockedXor64_np"
  - "_InterlockedXor64"
  - "_InterlockedXor_HLEAcquire"
  - "_InterlockedXor_HLERelease"
  - "_InterlockedXor_cpp"
  - "_InterlockedXor16_rel"
  - "_InterlockedXor8_rel"
  - "_InterlockedXor8"
  - "_InterlockedXor64_HLEAcquire"
  - "_InterlockedXor16_nf"
  - "_InterlockedXor16_acq"
  - "_InterlockedXor16_np"
  - "_InterlockedXor8_fn"
  - "_InterlockedXor8_np"
  - "_InterlockedXor64_cpp"
  - "_InterlockedXor_rel"
  - "_InterlockedXor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Intrínseco _InterlockedXor"
  - "Intrínseco _InterlockedXor64"
  - "Intrínseco InterlockedXor"
  - "Intrínseco InterlockedXor64"
ms.assetid: faef1796-cb5a-4430-b1e2-9d5eaf9b4a91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Funciones intr&#237;nsecas _InterlockedXor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de Microsoft**  
  
 Realiza una operación OR exclusiva \(XOR\) bit a bit atómica en una variable compartida por varios subprocesos.  
  
## Sintaxis  
  
```  
long _InterlockedXor(    long volatile * Value,    long Mask ); long _InterlockedXor_acq(    long volatile * Value,    long Mask ); long _InterlockedXor_HLEAcquire(    long volatile * Value,    long Mask ); long _InterlockedXor_HLERelease(    long volatile * Value,    long Mask ); long _InterlockedXor_nf(    long volatile * Value,    long Mask ); long _InterlockedXor_np(    long volatile * Value,    long Mask ); long _InterlockedXor_rel(    long volatile * Value,    long Mask ); char _InterlockedXor8(    char volatile * Value,    char Mask ); char _InterlockedXor8_acq(    char volatile * Value,    char Mask ); char _InterlockedXor8_nf(    char volatile * Value,    char Mask ); char _InterlockedXor8_np(    char volatile * Value,    char Mask ); char _InterlockedXor8_rel(    char volatile * Value,    char Mask ); short _InterlockedXor16(    short volatile * Value,    short Mask ); short _InterlockedXor16_acq(    short volatile * Value,    short Mask ); short _InterlockedXor16_nf (    short volatile * Value,    short Mask ); short _InterlockedXor16_np (    short volatile * Value,    short Mask ); short _InterlockedXor16_rel(    short volatile * Value,    short Mask ); __int64 _InterlockedXor64(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_acq(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_HLEAcquire(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_HLERelease(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_nf(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_np(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_rel(    __int64 volatile * Value,    __int64 Mask );  
```  
  
#### Parámetros  
 \[in, out\] `Value`  
 Un puntero al primer operando, que será sustituido por el resultado.  
  
 \[in\] `Mask`  
 Segundo operando.  
  
## Valor devuelto  
 El valor original del primer operando.  
  
## Requisitos  
  
|Función intrínseca|Arquitectura|Header|  
|------------------------|------------------|------------|  
|`_InterlockedXor`, `_InterlockedXor8`, `_InterlockedXor16`, `_InterlockedXor64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_acq`, `_InterlockedXor_nf`, `_InterlockedXor_rel`, `_InterlockedXor8_acq`, `_InterlockedXor8_nf`, `_InterlockedXor8_rel`, `_InterlockedXor16_acq`, `_InterlockedXor16_nf`, `_InterlockedXor16_rel`, `_InterlockedXor64_acq`, `_InterlockedXor64_nf`, `_InterlockedXor64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedXor_np`, `_InterlockedXor8_np`, `_InterlockedXor16_np`, `_InterlockedXor64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_HLEAcquire`, `_InterlockedXor_HLERelease`, `_InterlockedXor64_HLEAcquire`, `_InterlockedXor64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Comentarios  
 El número en el nombre de cada función especifica el tamaño en bits de los argumentos.  
  
 En plataformas ARM, utilice los intrínsecos con sufijos `_acq` y `_rel` si necesita adquirir y liberar semántica, como al principio y al final de una sección crítica.  Los intrínsecos ARM con un sufijo `_nf` \("sin límite"\) no actúan como una barrera de memoria.  
  
 Los intrínsecos con un sufijo `_np` \("sin captura previa"\) impiden que el compilador inserte una posible operación de captura previa.  
  
 En las plataformas de Intel que admiten instrucciones de Elisión de bloqueo de Hardware \(HLE\), los intrínsecos con sufijos `_HLEAcquire` y `_HLERelease` incluyen una sugerencia para el procesador que puede acelerar el rendimiento mediante la eliminación de un paso de escritura de bloqueo en el hardware.  Si se llama a estos intrínsecos en plataformas que no son compatibles con HLE, se omite la sugerencia.  
  
## Ejemplo  
  
```  
// _InterLockedXor.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedXor)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedXor(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xffff0000 0xffff00 0xff00ff00**   
## FIN de Específicos de Microsoft  
  
## Vea también  
 [Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)   
 [Conflictos con el compilador de x86](../build/conflicts-with-the-x86-compiler.md)