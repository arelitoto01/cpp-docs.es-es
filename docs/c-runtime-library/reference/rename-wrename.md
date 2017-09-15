---
title: rename, _wrename | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rename
- _wrename
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
dev_langs:
- C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
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
ms.openlocfilehash: 5aeb9d9ceac7eabac061f211f48835d07f2ec38e
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="rename-wrename"></a>rename, _wrename
Cambia el nombre de un archivo o de un directorio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 *oldname*  
 Puntero al nombre anterior.  
  
 *newname*  
 Puntero al nombre nuevo.  
  
## <a name="return-value"></a>Valor devuelto  
 Cada una de estas funciones devuelve 0 si se realiza correctamente. Si se produce un error, la función devuelve un valor distinto de cero y establece `errno` en uno de los siguientes valores:  
  
 `EACCES`  
 El archivo o directorio especificado por *newname* ya existe o no se pudo crear (ruta de acceso no válida), o bien *oldname* es un directorio y *newname* especifica otra ruta de acceso.  
  
 `ENOENT`  
 Archivo o ruta de acceso especificado por *oldname* no encontrado.  
  
 `EINVAL`  
 El nombre contiene caracteres no válidos.  
  
 Para otros valores devueltos posibles, vea [_doserrno, _errno, syserrlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Comentarios  
 La función **rename** cambia el nombre del archivo o directorio especificado por *oldname* por el nombre proporcionado por *newname*. El nombre anterior debe ser la ruta de acceso de un archivo o directorio existente. El nombre nuevo no debe ser el nombre de un archivo o directorio existente. Puede usar **rename** para mover un archivo de un directorio o dispositivo a otro indicando una ruta de acceso diferente en el argumento *newname*. Sin embargo, no puede usar **rename** para mover un directorio. Se puede cambiar el nombre de los directorios, pero estos no se pueden mover.  
  
 `_wrename` es una versión con caracteres anchos de **_rename**; los argumentos para `_wrename` son cadenas de caracteres anchos. `_wrename` y **_rename** se comportan de forma idéntica.  
  
### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico  
  
|Rutina TCHAR.H|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_trename`|**rename**|**rename**|`_wrename`|  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|**rename**|\<io.h> o \<stdio.h>|  
|`_wrename`|\<stdio.h> o \<wchar.h>|  
  
 Para obtener información adicional de compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="libraries"></a>Bibliotecas  
 Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## <a name="output"></a>Salida  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## <a name="see-also"></a>Vea también  
 [Control de archivos](../../c-runtime-library/file-handling.md)