---
title: "_mbccpy_s, _mbccpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbccpy_s"
  - "_mbccpy_s_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbccpy_s_l"
  - "mbccpy_s_l"
  - "mbccpy_s"
  - "_mbccpy_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbccpy_s (función)"
  - "_mbccpy_s_l (función)"
  - "_tccpy_s (función)"
  - "_tccpy_s_l (función)"
  - "mbccpy_s (función)"
  - "mbccpy_s_l (función)"
  - "tccpy_s (función)"
  - "tccpy_s_l (función)"
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# _mbccpy_s, _mbccpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copia un carácter multibyte de una cadena en otra.  Estas versiones de [\_mbccpy, \_mbccpy\_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) tienen mejoras de seguridad, como se describe en [Características de seguridad de CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Esta API no se puede usar en aplicaciones que se ejecutan en Windows en tiempo de ejecución.  Para obtener más información, vea [Funciones de CRT no admitidas con \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Sintaxis  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### Parámetros  
 \[out\] `dest`  
 Destino de la copia.  
  
 \[in\] `buffSizeInBytes`  
 Tamaño del búfer de destino.  
  
 \[out\] `pCopied`  
 Se rellena con el número de bytes copiados \(1 o 2 si la operación se ejecuta correctamente\).  Pase `NULL` si el número da igual.  
  
 \[in\] `src`  
 Carácter multibyte que se va a copiar.  
  
 \[in\] `locale`  
 Configuración regional que se va a usar.  
  
## Valor devuelto  
 Devuelve cero si se ejecuta correctamente; devuelve un código de error si se produce un error.  Si `src` o `dest` es `NULL`, o si se copiarían más de `buffSizeinBytes` bytes en `dest`, se invoca el controlador de parámetros no válidos, como se describe en [Validación de parámetros](../../c-runtime-library/parameter-validation.md).  Si la ejecución puede continuar, las funciones devuelven `EINVAL` y `errno` se establece en `EINVAL`.  
  
## Comentarios  
 La función `_mbccpy_s` copia un carácter multibyte de `src` en `dest`.  Si `src` no señala al byte inicial de un carácter multibyte determinado por una llamada implícita a [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), se copia el byte único al que señala `src`.  Si `src` señala a un byte inicial pero el byte siguiente es 0, y por tanto no válido, en `dest` se copia 0, `errno` se establece en `EILSEQ` y la función devuelve `EILSEQ`.  
  
 `_mbccpy_s` no anexa un terminador null; sin embargo, si `src` señala a un carácter nulo, ese carácter nulo se copia en `dest` \(es simplemente una copia normal de un único byte\).  
  
 El valor de `pCopied` se rellena con el número de bytes copiados.  Los valores posibles son 1 y 2 si la operación es correcta.  Si se pasa `NULL`, se omite este parámetro.  
  
|`src`|se copia en `dest`|`pCopied`|Valor devuelto|  
|-----------|------------------------|---------------|--------------------|  
|byte no inicial|byte no inicial|1|0|  
|0|0|1|0|  
|byte inicial seguido por un valor distinto de 0|byte inicial seguido por un valor distinto de 0|2|0|  
|byte inicial seguido por 0|0|1|`EILSEQ`|  
  
 Observe que la segunda fila simplemente es un caso especial de la primera.  Observe también que la tabla supone que `buffSizeInBytes` \>\= `pCopied`.  
  
 `_mbccpy_s` usa la configuración regional actual para cualquier comportamiento que dependa de la configuración regional.  `_mbccpy_s_l` y `_mbccpy_s` son exactamente iguales, salvo que `_mbccpy_s_l` usa la configuración regional que se pasa para todo comportamiento dependiente de la configuración regional.  
  
 En C\+\+, el uso de estas funciones se simplifica mediante sobrecargas de plantilla. Las sobrecargas pueden deducir la longitud del búfer automáticamente, lo que elimina la necesidad de especificar un argumento de tamaño.  Para obtener más información, vea [Sobrecargas de plantilla seguras](../../c-runtime-library/secure-template-overloads.md).  
  
### Asignaciones de rutina de texto genérico  
  
|Rutina Tchar.h|\_UNICODE y \_MBCS no definidos|\_MBCS definido|\_UNICODE definido|  
|--------------------|-------------------------------------|---------------------|------------------------|  
|`_tccpy_s`|Se asigna a una macro o una función insertada.|`_mbccpy_s`|Se asigna a una macro o una función insertada.|  
  
## Requisitos  
  
|Rutina|Encabezado necesario|  
|------------|--------------------------|  
|`_mbccpy_s`|\<mbstring.h\>|  
|`_mbccpy_s_l`|\<mbstring.h\>|  
  
 Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## Vea también  
 [Configuración regional](../../c-runtime-library/locale.md)   
 [Interpretación de secuencias de caracteres de varios bytes](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)