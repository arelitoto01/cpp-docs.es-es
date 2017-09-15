---
title: fesetenv | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fesetenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
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
ms.openlocfilehash: 96453fb182aa3c14bec8a296899cfcd15d39222c
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="fesetenv"></a>fesetenv
Establece el entorno actual de punto flotante.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `penv`  
 Puntero a un objeto `fenv_t` que contiene un entorno de punto flotante que se establece con una llamada a [fegetenv](fegetenv1.md) o [feholdexcept](feholdexcept2.md). También puede especificar el entorno de punto flotante de inicio predeterminado mediante la macro FE_DFL_ENV.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve 0 si el entorno se ha establecido correctamente. De lo contrario, devuelve un valor distinto de cero.  
  
## <a name="remarks"></a>Comentarios  
 La función `fesetenv` establece el entorno actual de punto flotante a partir del valor almacenado en el objeto `fenv_t` al que apunta `penv`. El entorno de punto flotante consiste en el conjunto de marcas de estado y modos de control que afectan a los cálculos de punto flotante. Incluye el modo de redondeo y las marcas de estado de las excepciones de punto flotante.  Si `penv` no es FE_DFL_ENV o no apunta a un objeto `fenv_t` válido, el comportamiento posterior es indefinido.  
  
 Una llamada a esta función establece las marcas de estado de excepción que se encuentran en el objeto `penv`, pero no genera esas excepciones.  
  
 Para usar esta función, debe desactivar las optimizaciones de punto flotante que podrían impedir el acceso mediante la directiva `#pragma fenv_access(on)` antes de la llamada. Para obtener más información, consulte [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Requisitos  
  
|Función|Encabezado C|Encabezado C++|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h>|\<cfenv>|  
  
 Para obtener información adicional sobre compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia alfabética de funciones](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)