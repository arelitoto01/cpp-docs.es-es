---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDumpStatistics
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
apitype: DLLExport
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 524c875f5cf25eb41d09e0f5dc99c32efcae8661
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
Vuelca la información del encabezado de depuración de un estado del montón especificado en un formato legible para el usuario (solo versión de depuración).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `state`  
 Puntero al estado del montón que se va a volcar.  
  
## <a name="remarks"></a>Comentarios  
 La función `_CrtMemDumpStatistics` vuelca la información del encabezado de depuración de un estado del montón especificado en un formato legible para el usuario. La aplicación puede usar las estadísticas del volcado para realizar el seguimiento de las asignaciones y detectar problemas de memoria. El estado de la memoria puede contener un estado de montón concreto o la diferencia entre dos estados. Cuando no se define [_DEBUG](../../c-runtime-library/debug.md) , las llamadas a `_CrtMemDumpStatistics` se quitan durante el preprocesamiento.  
  
 La función `state` debe ser un puntero a una estructura de `_CrtMemState` que ha sido rellenada por [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) o devuelta por [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) antes de llamar a `_CrtMemDumpStatistics` . Si `state` es `NULL`, se invoca el controlador de parámetros no válidos, como se describe en [Parameter Validation](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, `errno` se establece en `EINVAL` y no se realiza ninguna acción. Para obtener más información, consulte [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Para obtener más información sobre las funciones de estado del montón y la estructura `_CrtMemState`, consulte [Funciones que indican el estado del montón](/visualstudio/debugger/crt-debug-heap-details). Para obtener más información sobre cómo se asignan, inicializan y administran los bloques de memoria en la versión de depuración del montón base, consulte [Detalles del montón de depuración de CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|Encabezados opcionales|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 Para obtener más información sobre compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la introducción.  
  
 **Bibliotecas:** solo versiones de depuración de [Características de la biblioteca CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Vea también  
 [Rutinas de depuración](../../c-runtime-library/debug-routines.md)