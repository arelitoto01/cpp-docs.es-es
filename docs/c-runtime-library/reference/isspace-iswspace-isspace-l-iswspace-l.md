---
title: isspace, iswspace, _isspace_l, _iswspace_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswspace
- _istspace
- isspace
dev_langs:
- C++
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
caps.latest.revision: 18
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 650f20fff143676530022a915f782b0234128122
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="isspace-iswspace-isspacel-iswspacel"></a>isspace, iswspace, _isspace_l, _iswspace_l
Determina si un entero representa un carácter de espacio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int isspace(  
   int c   
);  
int iswspace(  
   wint_t c   
);  
int _isspace_l(  
   int c,  
   _locale_t locale  
);  
int _iswspace_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `c`  
 Entero que se va a probar.  
  
 `locale`  
 Configuración regional que se va a usar.  
  
## <a name="return-value"></a>Valor devuelto  
 Cada una de estas rutinas devuelve un valor distinto de cero si `c` es una representación concreta de un carácter de espacio. `isspace`Devuelve un valor distinto de cero si `c` es un carácter de espacio en blanco (0 x 09-0x0D o 0 x 20). El resultado de la condición de prueba para la función `isspace` depende del valor de la categoría `LC_CTYPE` de la configuración regional; para obtener más información, vea [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Las versiones de estas funciones sin el sufijo `_l` usan la configuración regional actual del comportamiento dependiente de la configuración regional; las versiones que tienen el sufijo `_l` son idénticas salvo que usan el parámetro de configuración regional que se pasa. Para obtener más información, vea [Configuración regional](../../c-runtime-library/locale.md).  
  
 `iswspace` devuelve un valor distinto de cero si `c` es un carácter ancho que corresponde a un carácter de espacio en blanco estándar.  
  
 El comportamiento de `isspace` e `_isspace_l` es indefinido si `c` no se encuentra al final del archivo ni en el intervalo de 0 a 0xFF, incluidos. Cuando se usa una biblioteca CRT de depuración y `c` no es uno de estos valores, las funciones generan una aserción.  
  
### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico  
  
|Rutina TCHAR.H|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|**_** `istspace`|`isspace`|[_ismbcspace](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswspace`|  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`isspace`|\<ctype.h>|  
|`iswspace`|\<ctype.h> o \<wchar.h>|  
|`_isspace_l`|\<ctype.h>|  
|`_iswspace_l`|\<ctype.h> o \<wchar.h>|  
  
 Para obtener información adicional sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Vea también  
 [Clasificación de caracteres](../../c-runtime-library/character-classification.md)   
 [Configuración regional](../../c-runtime-library/locale.md)   
 [is, isw (Rutinas)](../../c-runtime-library/is-isw-routines.md)