---
title: _heapset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
dev_langs:
- C++
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 0bcd8094d0b07927c8f85baf81d6ae834d283d9d
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="heapset"></a>_heapset
Comprueba que los montones mantienen una coherencia mínima y establece las entradas libres a un valor especificado.  
  
> [!IMPORTANT]
>  Esta función está obsoleta. A partir de Visual Studio 2015, no está disponible en CRT.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `fill`  
 Carácter de relleno.  
  
## <a name="return-value"></a>Valor devuelto  
 `_heapset` devuelve una de las siguientes constantes de manifiesto enteras, definidas en Malloc.h.  
  
 `_HEAPBADBEGIN`  
 La información de encabezado inicial no es válida o no se encuentra.  
  
 `_HEAPBADNODE`  
 Se ha encontrado un montón dañado o un nodo incorrecto.  
  
 `_HEAPEMPTY`  
 El montón no está inicializado.  
  
 `_HEAPOK`  
 El montón parece ser coherente.  
  
 Además, si se produce un error, `_heapset` establece `errno` en `ENOSYS`.  
  
## <a name="remarks"></a>Comentarios  
 La función `_heapset` muestra las ubicaciones de memoria libre o los nodos que se han sobrescrito accidentalmente.  
  
 `_heapset` comprueba la coherencia mínima en el montón y establece cada byte de las entradas libres del montón en el valor `fill`. Este valor conocido muestra las ubicaciones de memoria del montón que contienen nodos libres y las que contienen datos que se escribieron involuntariamente en la memoria liberada. Si el sistema operativo no admite `_heapset`(por ejemplo Windows 98), la función devuelve `_HEAPOK` y establece `errno` en `ENOSYS`.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|Encabezado opcional|  
|-------------|---------------------|---------------------|  
|`_heapset`|\<malloc.h>|\<errno.h>|  
  
 Para obtener más información sobre compatibilidad, consulte [Compatibilidad](../c-runtime-library/compatibility.md) en la introducción.  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_heapset.c  
// This program checks the heap and  
// fills in free entries with the character 'Z'.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int heapstatus;  
   char *buffer;  
  
   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is   
      exit( 0 );                        //    initialized       
   heapstatus = _heapset( 'Z' );        // Fill in free entries   
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf( "OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf( "OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
   free( buffer );  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>Vea también  
 [Asignación de memoria](../c-runtime-library/memory-allocation.md)   
 [_heapadd](../c-runtime-library/heapadd.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)