---
title: "Asignación de memoria | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 10
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c8bbb5b6f634b401889c787977fde866ecd41eaa
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="memory-allocation"></a>Asignación de memoria
Use estas rutinas para asignar, liberar y reasignar memoria.  
  
### <a name="memory-allocation-routines"></a>Rutinas de asignación de memoria  
  
|Rutina|Uso|  
|-------------|---------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Asignar memoria de una pila|  
|[calloc](../c-runtime-library/reference/calloc.md)|Asignar almacenamiento para la matriz, inicializando a 0 cada byte en el bloque asignado|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Depurar la versión de `calloc`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|Liberar un bloque asignado|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Liberar un bloque asignado|  
|[_expand](../c-runtime-library/reference/expand.md)|Expandir o reducir un bloque de memoria sin moverlo|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Depurar la versión de `_expand`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[free](../c-runtime-library/reference/free.md)|Liberar un bloque asignado|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Depurar la versión de `free`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[_freea](../c-runtime-library/reference/freea.md)|Liberar un bloque asignado de la pila|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Obtener identificador de Win32 en el montón de CRT.|  
|[_heapadd](../c-runtime-library/heapadd.md)|Agregar memoria al montón|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Comprobar la coherencia del montón|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Liberar la memoria sin usar del montón|  
|[_heapset](../c-runtime-library/heapset.md)|Rellenar las entradas de montón libres con el valor especificado|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Devolver información sobre cada entrada en el montón|  
|[malloc](../c-runtime-library/reference/malloc.md)|Asignar un bloque de memoria del montón|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Depurar la versión de `malloc`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[_msize](../c-runtime-library/reference/msize.md)|Devolver el tamaño del bloque asignado|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Depurar la versión de `_msize`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[new](../c-runtime-library/operator-new-crt.md)|Asignar un bloque de memoria del montón|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Asignar un bloque de memoria del montón|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Devolver la dirección de la nueva rutina de controlador actual, según lo establecido por `_set_new_handler`|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Devolver un entero que indique el nuevo modo de controlador establecido por `_set_new_mode` para `malloc`|  
|[realloc](../c-runtime-library/reference/realloc.md)|Reasignar un nuevo tamaño al bloque|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Depurar la versión de `realloc`; disponible únicamente en las versiones de depuración de las bibliotecas en tiempo de ejecución|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Habilitar el mecanismo de tratamiento de errores cuando el operador `new` no pueda asignar memoria y habilitar la compilación de bibliotecas de C++ Standard|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|Definir el nuevo modo de controlador para `malloc`|  
  
## <a name="see-also"></a>Vea también  
 [Rutinas en tiempo de ejecución por categoría](../c-runtime-library/run-time-routines-by-category.md)