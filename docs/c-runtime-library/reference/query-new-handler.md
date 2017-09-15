---
title: _query_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 63d43e80009b0d6c8f2d827f6ea5b239d7a39663
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="querynewhandler"></a>_query_new_handler
Devuelve la dirección de la nueva rutina de controlador actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve la dirección de la nueva rutina de controlador actual, según lo establecido por `_set_new_handler`.  
  
## <a name="remarks"></a>Comentarios  
 La función `_query_new_handler` de C++ devuelve la dirección de la función de control de excepciones actual establecida por la función [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) de C++. `_set_new_handler` se usa para especificar una función de control de excepciones que tiene el control si el operador **new** no puede asignar memoria. Para obtener más información, vea la descripción de los [operadores new y delete](../../cpp/new-and-delete-operators.md) en la referencia del lenguaje de C++.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h>|  
  
 Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la introducción.  
  
## <a name="libraries"></a>Bibliotecas  
 Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Vea también  
 [Asignación de memoria](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)