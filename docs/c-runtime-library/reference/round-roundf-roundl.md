---
title: round, roundf, roundl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- round
- roundl
- roundf
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
- roundf
- roundl
- round
dev_langs:
- C++
helpviewer_keywords:
- roundl function
- round function
- roundf function
ms.assetid: 6be90877-193c-4b80-a32b-c3eca33f9c6f
caps.latest.revision: 6
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
ms.openlocfilehash: e3b7e95451b53a9dde45c1a156ff0ceeaac5aca0
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="round-roundf-roundl"></a>round, roundf, roundl
Redondea un valor de punto flotante al entero más cercano.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
double round(   
   double x   
);  
float round(  
   float x  
);  // C++ only  
long double round(  
   long double x  
);  // C++ only  
float roundf(  
   float x  
);  
long double roundl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `x`  
 Valor de punto flotante que se va a redondear.  
  
## <a name="return-value"></a>Valor devuelto  
 Las funciones `round` devuelven un valor de punto flotante que representa el entero más cercano a `x`. Los valores que se encuentran a medio camino se redondean en cero, independientemente de la configuración del modo de redondeo del punto flotante. No se devuelve ningún error.  
  
|Entrada|Excepción SEH|Excepción de Matherr|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|ninguna|`_DOMAIN`|  
  
## <a name="remarks"></a>Comentarios  
 Puesto que C++ permite las sobrecargas, es posible llamar a las sobrecargas de `round` que toman y devuelven los valores `float` y `long double`. En un programa C, `round` siempre y devuelve `double`.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`round`, `roundf`, `roundl`|\<math.h>|  
  
 Para obtener información adicional sobre compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_round.c  
// Build with: cl /W3 /Tc crt_round.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 2.5 and -2.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 2.5;  
  
   printf("round(%f) is %.0f\n", x, round(x));  
   printf("round(%f) is %.0f\n", -x, round(-x));  
   printf("roundf(%f) is %.0f\n", y, roundf(y));  
   printf("roundf(%f) is %.0f\n", -y, roundf(-y));  
   printf("roundl(%Lf) is %.0Lf\n", z, roundl(z));  
   printf("roundl(%Lf) is %.0Lf\n", -z, roundl(-z));  
}  
```  
  
```Output  
round(2.499999) is 2  
round(-2.499999) is -2  
roundf(2.800000) is 3  
roundf(-2.800000) is -3  
roundl(2.500000) is 3  
roundl(-2.500000) is -3  
```  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con el punto flotante](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](http://msdn.microsoft.com/en-us/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [lround, lroundf, lroundl, llround, llroundf, llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint, nearbyintf, nearbyintl](http://msdn.microsoft.com/en-us/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)