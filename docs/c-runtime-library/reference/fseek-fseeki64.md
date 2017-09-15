---
title: fseek, _fseeki64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
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
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: es-es
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
Mueve el puntero de archivo a una ubicación especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `stream`  
 Puntero a la estructura `FILE`.  
  
 `offset`  
 Número de bytes desde `origin`.  
  
 `origin`  
 Posición inicial.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, `fseek` y `_fseeki64` devuelven 0. De lo contrario, devuelve un valor distinto de cero. En los dispositivos incapaces de efectuar búsquedas, el valor devuelto es indefinido. Si `stream` es un puntero nulo o `origin` no es ninguno de los valores permitidos que se describen a continuación, `fseek` y `_fseeki64` invocan al controlador de parámetros no válidos, tal y como se describe en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, estas funciones establecen `errno` en `EINVAL` y devuelven -1.  
  
## <a name="remarks"></a>Comentarios  
 El `fseek` y `_fseeki64` se mueve el puntero de archivo (si existe) asociado a las funciones `stream` a una ubicación nueva `offset` bytes a partir de `origin`. La siguiente operación de la secuencia se realiza en la nueva ubicación. En una secuencia abierta para actualización, la siguiente operación puede ser de lectura o de escritura. El origen del argumento debe ser una de las constantes siguientes, que se definen en STDIO.H:  
  
 `SEEK_CUR`  
 Posición actual del puntero de archivo.  
  
 `SEEK_END`  
 Final de archivo.  
  
 `SEEK_SET`  
 Principio de archivo.  
  
 Puede usar `fseek` y `_fseeki64` para cambiar la posición del puntero a cualquier lugar de un archivo. El puntero también puede colocarse más allá del final del archivo. `fseek`y `_fseeki64` borra el indicador de fin de archivo y anula el efecto de cualquier antes `ungetc` llama en `stream`.  
  
 Cuando un archivo se abre para anexar datos, la posición de archivo actual se determina con la última operación de E/S, no en función de dónde se produciría la siguiente escritura. Si todavía no se ha producido ninguna operación de E/S en un archivo abierto para anexar, la posición de archivo se sitúa al principio del archivo.  
  
 Para las secuencias que se abre en modo de texto, `fseek` y `_fseeki64` haber un uso limitado, porque pueden hacer que las traducciones de avance de línea de retorno de carro `fseek` y `_fseeki64` para producir resultados inesperados. El único `fseek` y `_fseeki64` operaciones siempre funciona en secuencias que se abre en modo de texto son:  
  
-   Búsqueda con un desplazamiento de 0 en relación con cualquiera de los valores de origen.  
  
-   Operaciones de búsqueda desde el principio del archivo con un valor de desplazamiento devuelven desde una llamada a `ftell` al usar `fseek` o `_ftelli64` al usar `_fseeki64`.  
  
 Además, en modo de texto, CTRL+Z se interpreta como un carácter de final de archivo en la entrada. En archivos abiertos para lectura/escritura, `fopen` y todas las rutinas relacionadas buscan un CTRL+Z al final del archivo y, si es posible, lo eliminan. Se hace así porque el uso de `fseek` y `ftell` o `_fseeki64` y `_ftelli64` para desplazarse por un archivo que finaliza con un CTRL+Z puede hacer que `fseek` o `_fseeki64` se comporten de forma incorrecta cerca del final del archivo.  
  
 Cuando CRT abre un archivo que comienza con una marca BOM (Byte Order Mark), el puntero de archivo se sitúa después de esta marca (es decir, al principio del contenido real del archivo). Si tiene que usar `fseek` al principio del archivo, use `ftell` para obtener la posición inicial y `fseek` para ir a ella y no a la posición 0.  
  
 Esta función bloquea otros subprocesos durante la ejecución y por lo tanto es segura para subprocesos. Para obtener una versión que no sea de bloqueo, consulte [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## <a name="requirements"></a>Requisitos  
  
|Función|Encabezado necesario|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 Para obtener información adicional de compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>Vea también  
 [E/S de secuencia](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)