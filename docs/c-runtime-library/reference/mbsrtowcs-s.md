---
title: mbsrtowcs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: 24
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
ms.openlocfilehash: 920af1d0e06c7af71c3a98bf07f451f4d50f2659
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
Convierte una cadena de caracteres multibyte en la configuración regional actual en su representación de cadena de caracteres anchos. Versión de [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) con mejoras de seguridad, como se describe en [Características de seguridad de CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parámetros  
 [out] `pReturnValue`  
 El número de caracteres convertidos.  
  
 [out] `wcstr`  
 Dirección de búfer para almacenar la cadena de caracteres anchos convertida.  
  
 [out] `sizeInWords`  
 Tamaño de `wcstr` en palabras (caracteres anchos).  
  
 [in, out] `mbstr`  
 Puntero indirecto a la ubicación de la cadena de caracteres multibyte a convertir.  
  
 [in] `count`  
 Número máximo de caracteres anchos que se va a almacenar en el búfer `wcstr`, sin incluir el terminador nulo, o [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in, out] `mbstate`  
 Un puntero a un objeto `mbstate_t` de estado de la conversión. Si este valor es un puntero nulo, se utiliza un objeto de estado de la conversión interno estático. Dado que el objeto `mbstate_t` interno no es seguro para subprocesos, se recomienda pasar siempre su propio parámetro `mbstate`.  
  
## <a name="return-value"></a>Valor devuelto  
 Cero si la conversión es correcta, o un código de error en caso de error.  
  
|Condición de error|Valor devuelto y `errno`|  
|---------------------|------------------------------|  
|`wcstr` es un puntero nulo y `sizeInWords` > 0|`EINVAL`|  
|`mbstr` es un puntero nulo|`EINVAL`|  
|La cadena señalada indirectamente por `mbstr` contiene una secuencia multibyte que no es válida para la configuración regional actual.|`EILSEQ`|  
|El búfer de destino es demasiado pequeño para contener la cadena convertida (a menos que en `count` se use `_TRUNCATE`; para obtener más información, vea la sección Comentarios)|`ERANGE`|  
  
 Si solo se produce una de estas condiciones, se invoca la excepción de parámetro no válido, como se describe en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si se permite que la ejecución continúe, la función devuelve un código de error y establece `errno` como se indica en la tabla.  
  
## <a name="remarks"></a>Comentarios  
 La función `mbsrtowcs_s` convierte una cadena de caracteres multibyte indirectamente señalada por `mbstr` en caracteres anchos almacenados en el búfer señalado por `wcstr`, utilizando el estado de conversión contenido en `mbstate`. La conversión continuará para cada carácter hasta que se cumpla alguna de estas condiciones:  
  
-   Se encuentra un carácter multibyte nulo  
  
-   Se encuentra un carácter multibyte no válido  
  
-   El número de caracteres anchos almacenados en el búfer `wcstr` es igual a `count`.  
  
 La cadena de destino `wcstr` siempre está terminada en nulo, incluso si se produce un error, a menos que `wcstr` sea un puntero nulo.  
  
 Si `count` es el valor especial [_TRUNCATE](../../c-runtime-library/truncate.md), `mbsrtowcs_s` convierte tanto de la cadena como cabe en el búfer de destino, dejando espacio para un terminador nulo.  
  
 Si `mbsrtowcs_s` convierte correctamente la cadena de origen, pone el tamaño en caracteres anchos de la cadena convertida y establece el terminador nulo en `*``pReturnValue`, siempre que `pReturnValue` no sea un puntero nulo. Esto ocurre incluso si el argumento `wcstr` es un puntero nulo y le permite determinar el tamaño de búfer necesario. Tenga en cuenta que si `wcstr` es un puntero nulo, `count` se ignora.  
  
 Si `wcstr` no es un puntero nulo, al objeto de puntero señalado por `mbstr` se le asigna un puntero nulo si la conversión se detuvo por encontrarse un carácter nulo de terminación. De lo contrario, se le asigna la dirección inmediatamente posterior al último carácter multibyte convertido, de haberlo. Esto permite que una llamada de función subsiguiente reinicie la conversión en el punto en que se detuvo esta llamada.  
  
 Si `mbstate` es un puntero nulo, se utiliza el objeto de estado de la conversión estático interno de biblioteca `mbstate_t`. Dado que este objeto estático interno no es seguro para subprocesos, le recomendamos pasar siempre su propio valor para `mbstate`.  
  
 Si `mbsrtowcs_s` encuentra un carácter multibyte no válido en la configuración regional actual, pone -1 en `*``pReturnValue`, establece el búfer de destino `wcstr` a una cadena vacía, establece `errno` en `EILSEQ` y devuelve `EILSEQ`.  
  
 Si las secuencias señaladas por `mbstr` y `wcstr` se superponen, el comportamiento de `mbsrtowcs_s` no está definido. `mbsrtowcs_s` se ve afectado por la categoría LC_TYPE de la configuración regional actual.  
  
> [!IMPORTANT]
>  Asegúrese de que `wcstr` y `mbstr` no se superponen, y de que `count` refleja correctamente el número de caracteres multibyte a convertir.  
  
 La función `mbsrtowcs_s` difiere de [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md) en que se puede reiniciar. El estado de la conversión se almacena en `mbstate` para llamadas posteriores a la misma o a otras funciones reiniciables. Los resultados no están definidos cuando se combina el uso de funciones reiniciables y no reiniciables. Por ejemplo, una aplicación debe utilizar `mbsrlen` en lugar de `mbslen` si se utiliza una llamada subsiguiente a `mbsrtowcs_s` en lugar de a `mbstowcs_s.`  
  
 En C++, el uso de estas funciones se simplifica con las sobrecargas de plantilla. Las sobrecargas pueden realizar una inferencia automáticamente de la longitud de búfer (lo que elimina el requisito de especificar un argumento de tamaño) y pueden reemplazar automáticamente funciones anteriores no seguras con sus homólogos seguros más recientes. Para obtener más información, vea [Sobrecargas de plantilla seguras](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Excepciones  
 La función `mbsrtowcs_s` es segura para subprocesos si ninguna función en el proceso actual llama a `setlocale`, mientras se ejecute esta función y el argumento `mbstate` no sea un puntero nulo.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Vea también  
 [Conversión de datos](../../c-runtime-library/data-conversion.md)   
 [Configuración regional](../../c-runtime-library/locale.md)   
 [Interpretación de secuencias de caracteres de varios bytes](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)