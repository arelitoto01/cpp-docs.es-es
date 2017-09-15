---
title: malloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 22
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
ms.openlocfilehash: 3c024862e1bf993c4e602846d4da125599f3fe7f
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="malloc"></a>malloc
Asigna bloques de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `size`  
 Bytes para asignar.  
  
## <a name="return-value"></a>Valor devuelto  
 `malloc` devuelve un puntero void al espacio asignado o `NULL` si no hay suficiente memoria disponible. Para devolver un puntero a un tipo distinto de `void`, use una conversión de tipo en el valor devuelto. Se garantiza que el espacio de almacenamiento que apunta el valor devuelto está correctamente alineado para almacenar cualquier tipo de objeto que tenga un requisito de alineación inferior o igual al de la alineación básica. (En Visual C++, la alineación básica es la alineación necesaria para un `double` u 8 bytes. En el código destinado a las plataformas de 64 bits, son 16 bytes). Use [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) para asignar el almacenamiento para los objetos que tienen un requisito de alineación superior (por ejemplo, los tipos de SSE [__m128](../../cpp/m128.md) y `__m256`), así como los tipos que se declaran mediante `__declspec(align(``n``))`, donde `n` es mayor que 8. Si `size` es 0, `malloc` asigna un elemento de longitud cero en el montón y devuelve un puntero válido para ese elemento. Compruebe siempre el valor devuelto de `malloc`, incluso si la cantidad de memoria solicitada es pequeña.  
  
## <a name="remarks"></a>Comentarios  
 La función `malloc` asigna un bloque de memoria de al menos `size` bytes. El bloque podría ser mayor que `size` bytes debido al espacio necesario para obtener información de alineación y de mantenimiento.  
  
 `malloc` establece `errno` en `ENOMEM` si se produce un error de asignación de memoria o si la cantidad de memoria solicitada supera `_HEAP_MAXREQ`. Para obtener información sobre este y otros códigos de error, vea [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 El código de inicio usa `malloc` para asignar el almacenamiento para las variables `_environ`, `envp` y `argv`. Las siguientes funciones y sus equivalentes en caracteres anchos también llaman a `malloc`.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[_exec (funciones)](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[_spawn (funciones)](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[system](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 La función [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) de C++ establece el nuevo modo de controlador para `malloc`. El nuevo modo de controlador indica si, en caso de error, `malloc` va a llamar a la rutina del nuevo controlador según lo establecido por [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). De forma predeterminada, `malloc` no llama a la rutina del nuevo controlador en caso de error al asignar memoria. Puede invalidar este comportamiento predeterminado para que, cuando `malloc` no pueda asignar memoria, `malloc` llame a la rutina del nuevo controlador de la misma forma que hace el operador `new` cuando se produce un error por la misma razón. Para invalidar el valor predeterminado, llame a `_set_new_mode(1)` temprano en el programa o el vínculo con NEWMODE. OBJ (vea [opciones de vínculo](../../c-runtime-library/link-options.md)).  
  
 Cuando la aplicación se vincula con una versión de depuración de las bibliotecas en tiempo de ejecución de C, `malloc` se resuelve como [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md). Para obtener más información sobre cómo se administra el montón durante el proceso de depuración, vea [Detalles del montón de depuración de CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `malloc` está marcado como `__declspec(noalias)` y `__declspec(restrict)`; esto significa que se garantiza que la función no modifica variables globales y que el puntero devuelto no tiene alias. Para obtener más información, vea [noalias](../../cpp/noalias.md) y [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h> y \<malloc.h>|  
  
 Para obtener información adicional sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotecas  
 Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Ejemplo  
  
```C  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
```Output  
Memory space allocated for path name  
Memory freed  
```  
  
## <a name="see-also"></a>Vea también  
 [Asignación de memoria](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)
