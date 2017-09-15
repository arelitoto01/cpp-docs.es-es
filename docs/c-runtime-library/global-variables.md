---
title: Variables globales | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.variables
dev_langs:
- C++
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b4fb921a0685181aa3cd4dd2cf0422e3d6256ac5
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="global-variables"></a>Variables globales
La biblioteca en tiempo de ejecución de C de Microsoft proporciona las siguientes macros o variables globales. Algunas de estas macros o variables globales están desusadas y, en su lugar, se usan versiones funcionales más seguras que le recomendamos que use en lugar de las variables globales.  
  
|Variable|Descripción|  
|--------------|-----------------|  
|[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)|Contiene argumentos de la línea de comandos.|  
|[_daylight, _dstbias, _timezone y _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Desusado. En su lugar, use `_get_daylight`, `_get_dstbias`, `_get_timezone` y `_get_tzname`.<br /><br /> Se ajusta a la hora local. Usada en algunas funciones de fecha y hora.|  
|[errno, _doserrno, _sys_errlist y _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Desusado. En su lugar, use `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` y `strerror`.<br /><br /> Almacena códigos de error e información relacionada.|  
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Desusado. En su lugar, use `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` y `_wputenv_s`.<br /><br /> Punteros a matrices de punteros a cadenas de entorno del proceso. Se inicializa al inicio.|  
|[_fmode](../c-runtime-library/fmode.md)|Desusado. En su lugar, use `_get_fmode` o `_set_fmode`.<br /><br /> Establece el modo de traducción de archivo predeterminado.|  
|[_iob](../c-runtime-library/iob.md)|Matriz de estructuras de control de E/S para la consola, archivos y dispositivos.|  
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Contiene la información que usan las funciones de clasificación de caracteres.|  
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Desusado. En su lugar, use `_get_pgmptr` o `_get_wpgmptr`.<br /><br /> Se inicializa al iniciarse el programa en la ruta de acceso completa o relativa del programa, en el nombre de programa completo o en el nombre de programa sin la extensión de archivo, según cómo se haya invocado el programa.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de la biblioteca en tiempo de ejecución de C](../c-runtime-library/c-run-time-library-reference.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)   
 [__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)   
 [_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)