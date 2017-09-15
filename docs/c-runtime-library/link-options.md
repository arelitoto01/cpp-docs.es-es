---
title: "Opciones de vínculo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 3747170eb13e1b6fe5d489bc6cfdcf4c24195606
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="link-options"></a>Opciones de vínculo
El directorio lib de CRT incluye una serie de archivos de objetos pequeños que habilitan características de CRT específicas sin realizar ningún cambio en el código. Se denominan "opciones de vínculo" puesto que solo hay que agregarlas a la línea de comandos del enlazador para usarlas.  
  
 Las versiones de modo puro existen pero están en desuso en Visual Studio 2015. Use las versiones normales con código nativo y /clr, use las versiones puras (usando una p como prefijo) con el modo /clr:pure. Las opciones del compilador **/clr:pure** y **/clr:safe** están en desuso en Visual Studio 2015.  
  
|Nativo y /clr|Modo puro|Descripción|  
|----------------------|---------------|-----------------|  
|binmode.obj|pbinmode.obj|Establece el modo de traducción de archivo predeterminado en binario. Consulte [_fmode](../c-runtime-library/fmode.md).|  
|chkstk.obj|no disponible|Ofrece compatibilidad con comprobación de pila y alloca cuando no se use CRT.|  
|commode.obj|pcommode.obj|Establece la marca global de confirmación en "commit". Consulte [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) y [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|  
|fp10.obj|no disponible|Cambia el control de precisión predeterminado a 64 bits. Consulte [Compatibilidad con el punto flotante](../c-runtime-library/floating-point-support.md).|  
|invalidcontinue.obj|pinvalidcontinue.obj|Establece un controlador de parámetros no válidos predeterminado que no hace nada, lo que significa que los parámetros no válidos que se pasen a funciones de CRT solo establecerán errno y devolverán un resultado de error.|  
|loosefpmath.obj|no disponible|Se asegura de que el código de punto flotante tolera valores desnormalizados.|  
|newmode.obj|pnewmode.obj|Hace que [malloc](../c-runtime-library/reference/malloc.md) llame al nuevo controlador en caso de error. Consulte [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) y [realloc](../c-runtime-library/reference/realloc.md).|  
|noarg.obj|pnoarg.obj|Deshabilita todo el procesamiento de argc y argv.|  
|nochkclr.obj|no disponible|No hace nada. Quitar del proyecto.|  
|noenv.obj|pnoenv.obj|Deshabilita la creación de un entorno almacenado en caché para el CRT.|  
|nothrownew.obj|pnothrownew.obj|Habilita la versión que no produce excepciones de new en el CRT. Consulte [Operadores new y delete](../cpp/new-and-delete-operators.md).|  
|setargv.obj|psetargv.obj|Habilita la expansión de caracteres comodín de argumento de línea de comandos. Consulte [Expandir argumentos de caracteres comodín](../c-language/expanding-wildcard-arguments.md).|  
|threadlocale.obj|pthreadlocale.obj|Habilita de forma predeterminada la configuración regional por subproceso para todos los nuevos subprocesos.|  
|wsetargv.obj|pwsetargv.obj|Habilita la expansión de caracteres comodín de argumento de línea de comandos. Consulte [Expandir argumentos de caracteres comodín](../c-language/expanding-wildcard-arguments.md).|  
  
## <a name="see-also"></a>Vea también  
 [Características de la biblioteca CRT](../c-runtime-library/crt-library-features.md)