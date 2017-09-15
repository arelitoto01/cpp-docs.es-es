---
title: unexpected (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- unexpected
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
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
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
ms.openlocfilehash: 7e1188d3cf2136e67d2e212640b2c2c29b7cf1f5
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="unexpected-crt"></a>unexpected (CRT)
Llama a `terminate` o a una función que se especifique mediante `set_unexpected`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>Comentarios  
 La rutina `unexpected` no se usa con la implementación actual de control de excepciones de C++. `unexpected` llama a `terminate` de forma predeterminada. Puede cambiar este comportamiento predeterminado si escribe una función de finalización personalizada y llama a `set_unexpected` con el nombre de esta función como su argumento. `unexpected` llama a la última función especificada como argumento para `set_unexpected`.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`unexpected`|\<eh.h>|  
  
 Para obtener información adicional de compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="see-also"></a>Vea también  
 [Rutinas para el control de excepciones](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)