---
title: _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sprintf_p
- _swprintf_p_l
- _swprintf_p
- _sprintf_p_l
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
- _sprintf_p
- _swprintf_p_l
- _sprintf_p_l
- _swprintf_p
- sprintf_p
- swprint_p_l
- swprintf_p
- swprintf_p_l
dev_langs:
- C++
helpviewer_keywords:
- sprintf_p_l function
- swprintf_p function
- swprintf_p_l function
- _sprintf_p function
- _sprintf_p_l function
- _swprintf_p function
- sprintf_p function
- _stprintf_p function
- stprintf_p function
- _swprintf_p_l function
- stprintf_p_l function
- formatted text [C++]
- _stprintf_p_l function
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 35501213c0d9e0ee60472e4082bc03eabe8440e0
ms.contentlocale: es-es
ms.lasthandoff: 04/04/2017

---
# <a name="sprintfp-sprintfpl-swprintfp-swprintfpl"></a>_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
Escriba datos con formato en una cadena con la capacidad de especificar el orden en el que se usan los parámetros en la cadena de formato.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument_list]  
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument_list]  
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument_list]  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument_list]   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `buffer`  
 Ubicación de almacenamiento para los resultados  
  
 `sizeOfBuffer`  
 Número máximo de caracteres que se pueden almacenar.  
  
 `format`  
 Cadena de control de formato.  
  
 `argument_list`  
 Argumentos opcionales a la cadena de formato.  
  
 `locale`  
 Configuración regional que se va a usar.  
  
 Para más información, vea [Especificaciones de formato](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Valor devuelto  
 El número de caracteres escritos, o -1 si se produjo un error.  
  
## <a name="remarks"></a>Comentarios  
 La función `_sprintf_p` da formato y almacena una serie de caracteres y valores en `buffer`. Cada argumento de la `argument_list` (si existe) se convierte y sale según la especificación de formato correspondiente de `format`. El `format` argumento utiliza la [formato de sintaxis de especificación de funciones de printf y wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Se anexa un carácter `NULL` después del último carácter escrito. Si la copia tiene lugar entre cadenas que se superponen, el comportamiento es indefinido. La diferencia entre `_sprintf_p` y `sprintf_s` es que `_sprintf_p` admite parámetros posicionales, lo que permite especificar el orden en el que se usan los argumentos en la cadena de formato. Para obtener más información, vea [printf_p (Parámetros de posición)](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_swprintf_p` es una versión con caracteres anchos de `_sprintf_p`; los argumentos de puntero a `_swprintf_p` son cadenas de carácter ancho. La detección de errores de codificación en `_swprintf_p` puede diferir de la de `_sprintf_p`. `_swprintf_p` y `fwprintf_p` se comportan exactamente igual, salvo por el hecho de que `_swprintf_p` escribe la salida en una cadena y no en un destino de tipo `FILE`, y `_swprintf_p` requiere el parámetro `count` para especificar el número máximo de caracteres que se escribirán. Las versiones de estas funciones con el sufijo `_l` son idénticas salvo que usan el parámetro locale pasado en lugar de la configuración regional del subproceso actual.  
  
 `_sprintf_p` devuelve el número de bytes almacenados en `buffer`, sin contar el carácter `NULL` de terminación. `_swprintf_p`Devuelve el número de caracteres anchos almacenados en `buffer`, sin contar el carácter final `NULL` carácter ancho. Si `buffer` o `format` es un puntero nulo, o si la cadena de formato contiene caracteres de formato no válidos, se invoca al controlador de parámetros no válidos, como se describe en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, estas funciones devuelven -1 y establecen `errno` en `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Asignaciones de rutina de texto genérico  
  
|Rutina TCHAR.H|_UNICODE y _MBCS no definidos|_MBCS definido|_UNICODE definido|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h> o \<wchar.h>|  
  
 Para obtener información adicional de compatibilidad, consulte [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## <a name="example"></a>Ejemplo  
  
```C  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>Ejemplo  
  
```C  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
```Output  
Wrote 24 characters  
Wrote -1 characters  
```  
  
## <a name="see-also"></a>Vea también  
 [E/S de secuencia](../../c-runtime-library/stream-i-o.md)   
 [_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [vprintf (Funciones)](../../c-runtime-library/vprintf-functions.md)   
 [printf_p (Parámetros de posición)](../../c-runtime-library/printf-p-positional-parameters.md)