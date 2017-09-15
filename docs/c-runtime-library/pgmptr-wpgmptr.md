---
title: _pgmptr, _wpgmptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
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
ms.openlocfilehash: 221d1bd8259d8922695e9060eb8f2ada63d63631
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="pgmptr-wpgmptr"></a>_pgmptr, _wpgmptr
Ruta de acceso al archivo ejecutable. En desuso; use [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) y [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## <a name="remarks"></a>Comentarios  
 Cuando se ejecuta un programa desde el intérprete de comandos (Cmd.exe), `_pgmptr` se inicializa automáticamente en la ruta de acceso completa al archivo ejecutable. Por ejemplo, si se encuentra Hello.exe en C:\BIN, y C:\BIN está en la ruta de acceso, `_pgmptr` se establece en C:\BIN\Hello.exe cuando se ejecuta:  
  
```  
C> hello   
```  
  
 Cuando un programa no se ejecuta desde la línea de comandos, `_pgmptr` podría inicializarse en el nombre del programa (nombre base del archivo sin la extensión de nombre de archivo) o en un nombre de archivo, una ruta de acceso relativa o una ruta de acceso completa.  
  
 `_wpgmptr` es el equivalente de caracteres anchos de `_pgmptr` para su uso con los programas que utilizan `wmain`.  
  
### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico  
  
|Rutina Tchar.h|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="requirements"></a>Requisitos  
  
|Variable|Encabezado necesario|  
|--------------|---------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h>|  
  
## <a name="example"></a>Ejemplo  
 El siguiente programa muestra el uso de `_pgmptr`.  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 Puede usar `_wpgmptr` cambiando `%Fs` a `%S` y `main` a `wmain`.  
  
## <a name="see-also"></a>Vea también  
 [Variables globales](../c-runtime-library/global-variables.md)