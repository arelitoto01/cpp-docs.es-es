---
title: _umask_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 5c8efcdf5d3f44a6cd3bbcc39f2a98e3659c95ab
ms.contentlocale: es-es
ms.lasthandoff: 04/04/2017

---
# <a name="umasks"></a>_umask_s
Establece la máscara de permisos de archivo predeterminados. Versión de [_umask](../../c-runtime-library/reference/umask.md) con mejoras de seguridad, como se explica en [Características de seguridad de CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [in] `mode`  
 Configuración de permisos predeterminada.  
  
 [out] `oldMode`  
 Valor anterior de la configuración de permisos.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve un código de error si `Mode` no especifica un modo válido o si el puntero `pOldMode` es `NULL`.  
  
### <a name="error-conditions"></a>Condiciones de error  
  
|`mode`|`pOldMode`|**Valor devuelto**|**Contenido de** `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|cualquiera|`NULL`|`EINVAL`|no modificado|  
|modo no válido|cualquiera|`EINVAL`|no modificado|  
  
 Si se da una de las condiciones anteriores, se invoca al controlador de parámetros no válidos, tal como se explica en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, `_umask_s` devuelve `EINVAL` y establece `errno` en `EINVAL`.  
  
## <a name="remarks"></a>Comentarios  
 El `_umask_s` función establece la máscara de permisos de archivo del proceso actual en el modo especificado por `mode`. La máscara de permisos de archivo modifica la configuración de permisos de los nuevos archivos creados por `_creat`, `_open` o `_sopen`. Si un bit de la máscara es 1, el bit correspondiente del valor de permiso solicitado del archivo se establece en 0 (no permitido). Si un bit de la máscara es 0, el bit correspondiente se deja sin modificar. La configuración de permisos de un nuevo archivo no se establece hasta que se cierra el archivo por primera vez.  
  
 La expresión de entero `pmode` contiene una o las dos constantes del manifiesto siguientes, definidas en SYS\STAT.H:  
  
 `_S_IWRITE`  
 Escritura permitida.  
  
 `_S_IREAD`  
 Lectura permitida.  
  
 `_S_IREAD | _S_IWRITE`  
 Lectura y escritura permitidas.  
  
 Cuando se proporcionan ambas constantes, se unen mediante el operador OR bit a bit (`|`). Si el argumento `mode` es `_S_IREAD`, no se permite la lectura (el archivo es de solo escritura). Si el argumento `mode` es `_S_IWRITE`, no se permite la escritura (el archivo es de solo lectura). Por ejemplo, si el bit de escritura está establecido en la máscara, los nuevos archivos serán de solo lectura. Tenga en cuenta que en los sistemas operativos MS-DOS y Windows, todos los archivos se pueden leer; no se puede conceder permiso de solo escritura. Por tanto, el establecimiento del bit de lectura con `_umask_s` no tiene ningún efecto sobre los modos del archivo.  
  
 Si `pmode` no es una combinación de una de las constantes del manifiesto o incorpora un conjunto alternativo de constantes, la función simplemente las omitirá.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`_umask_s`|\<io.h>, \<sys/stat.h> y \<sys/types.h>|  
  
 Para obtener información adicional de compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>Vea también  
 [Control de archivos](../../c-runtime-library/file-handling.md)   
 [E/S de bajo nivel](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)