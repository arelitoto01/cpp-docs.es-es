---
title: catan, catanf, catanl | Microsoft Docs
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
- catan
- catanf
- catanl
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
- catan
- catanf
- catanl
- complex/catan
- complex/catanf
- complex/catanl
dev_langs:
- C++
helpviewer_keywords:
- catan function
- catanf function
- catanl function
ms.assetid: 8415ed9c-7909-4d08-b532-4630bafdc7e8
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 840e4fd2231d9eca61dc508b15a11ed75822bb6b
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="catan-catanf-catanl"></a>catan, catanf, catanl
Recupera el arco tangente de un número complejo con cortes de bifurcación fuera del intervalo [-1; + 1] en el eje imaginario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
_Dcomplex catan(   
   _Dcomplex z   
);  
_Fcomplex catan(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex catan(   
  _Lcomplex z   
);  // C++ only  
_Fcomplex catanf(   
   _Fcomplex z   
);  
_Lcomplex catanl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `z`  
 Número complejo que representa un ángulo en radianes.  
  
## <a name="return-value"></a>Valor devuelto  
 Arco tangente de `z` en radianes. El resultado es ilimitado a lo largo del eje imaginario y en el intervalo [-π/2; + π/2] en el eje real.  
  
## <a name="remarks"></a>Comentarios  
 Puesto que C++ permite las sobrecargas, es posible llamar a las sobrecargas de `catan` que toman y devuelven los valores `_Fcomplex` y `_Lcomplex`. En un programa de C, `catan` siempre toma y devuelve un valor `_Dcomplex` .  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado C|Encabezado C++|  
|-------------|--------------|------------------|  
|`catan`,               `catanf`, `catanl`|\<complex.h>|\<ccomplex>|  
  
 Para obtener más información sobre compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la introducción.  
  
## <a name="see-also"></a>Vea también  
 [Referencia alfabética de funciones](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)