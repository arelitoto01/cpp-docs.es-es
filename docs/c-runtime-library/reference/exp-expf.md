---
title: EXP, expf, expl | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _expl
- expf
- expl
- exp
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bce9249134b9d0e3716d8b79a0bc0642c64fc5e6
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="exp-expf-expl"></a>EXP, expf, expl
Calcula el valor exponencial.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `x`  
 Valor del punto flotante a exponentiate la base del logaritmo natural *e* por.  
  
## <a name="return-value"></a>Valor devuelto  
 El `exp` funciones devuelven el valor exponencial del parámetro de punto flotante, *x*, si se realiza correctamente. Es decir, el resultado es *e*<sup>*x*</sup>, donde *e* es la base del logaritmo natural. Si se produce desbordamiento, la función devuelve INF (infinito) y en subdesbordamiento, `exp` devuelve 0.  
  
|Entrada|Excepción SEH|Excepción de Matherr|  
|-----------|-------------------|-----------------------|  
|± Valor NaN reservado, indeterminado|Ninguna|_DOMAIN|  
|± Infinito|INVALID|_DOMAIN|  
|x ≥ 7,097827e+002|INEXACTO+DESBORDAMIENTO|OVERFLOW|  
|X ≤ -7,083964e+002|INEXACTO+SUBDESBORDAMIENTO|DESBORDAMIENTO|  
  
 El `exp` función tiene una implementación que usa Extensiones SIMD de transmisión por secuencias 2 (SSE2). Consulte [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) para obtener información y conocer las restricciones sobre el uso de la implementación de SSE2.  
  
## <a name="remarks"></a>Comentarios  
 C++ permite las sobrecargas, es posible llamar a las sobrecargas de `exp` que toman un **float** o **long double** argumento. En un programa C, `exp` siempre toma y devuelve un **doble**.  
  
## <a name="requirements"></a>Requisitos  
  
|Función|Encabezado C necesario|Encabezado C++ necesario|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> o \<math.h>|  
  
 Para obtener información adicional de compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con el punto flotante](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)