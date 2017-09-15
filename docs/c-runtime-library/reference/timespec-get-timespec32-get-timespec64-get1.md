---
title: "timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
  - "time/timespec_get"
  - "time/_timespec32_get"
  - "time/_timespec64_get"
  - "timespec"
  - "_timespec32"
  - "_timespec64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timespec_get (función)"
  - "_timespec32_get (función)"
  - "_timespec64_get (función)"
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# timespec_get, _timespec32_get, _timespec64_get
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Establece el intervalo al que apunta el primer argumento en la hora actual del calendario, basándose en la base de tiempo especificada.  
  
## Sintaxis  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### Parámetros  
 `time_spec`  
 Puntero para una estructura que se establece en el tiempo en segundos y nanosegundos desde el inicio de la época.  
  
 `base`  
 Un valor específico de implementación distinta de cero que especifica la base de tiempo.  
  
## Valor devuelto  
 El valor de `base` si es correcto; de lo contrario, devuelve cero.  
  
## Comentarios  
 Las funciones `timespec_get` establecen la hora actual en la estructura a la que apunta el argumento `time_spec`. Todas las versiones de esta estructura tienen dos miembros, `tv_sec` y `tv_nsec`. El valor `tv_sec` se establece en el número entero de segundos y `tv_nsec` en el número integral de nanosegundos, redondeado a la resolución del reloj del sistema, desde el inicio de la época especificada por `base`.  
  
 **Específicos de Microsoft**  
  
 Estas funciones solo admiten `TIME_UTC` como el valor `base`. Esto establece el valor `time_spec` en el número de segundos y nanosegundos desde el inicio de la época, medianoche, 1 de enero de 1970, Hora universal coordinada \(UTC\). En `struct _timespec32`, `tv_sec` es un valor `__time32_t`. En `struct _timespec64`, `tv_sec` es un valor `__time64_t`. En `struct timespec`, `tv_sec` es un tipo `time_t`, que tiene una longitud de 32 o 64 bits, en función de si se define la macro de preprocesador \_USE\_32BIT\_TIME\_T. La función `timespec_get` es una función insertada que llama a `_timespec32_get` si se define \_USE\_32BIT\_TIME\_T; de lo contrario, llama a `_timespec64_get`.  
  
 **Fin de Específicos de Microsoft**  
  
## Requisitos  
  
|Rutina|Encabezado necesario|  
|------------|--------------------------|  
|`timespec_get`, `_timespec32_get`, `_timespec64_get`|C: \<time.h\>, C\+\+: \<ctime\> o \<time.h\>|  
  
 Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## Vea también  
 [Administración del tiempo](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)