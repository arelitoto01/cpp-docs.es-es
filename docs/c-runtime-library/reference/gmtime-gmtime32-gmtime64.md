---
title: gmtime, _gmtime32, _gmtime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: d6acd03622ffd309e394fc076c2922492ac2475b
ms.contentlocale: es-es
ms.lasthandoff: 04/01/2017

---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64
Convierte un valor de hora en una estructura. Hay disponibles versiones más seguras de estas funciones; vea [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `timer`  
 Puntero a la hora almacenada. La hora se representa como los segundos transcurridos desde la medianoche (00:00:00) del 1 de enero de 1970, hora universal coordinada (UTC).  
  
## <a name="return-value"></a>Valor devuelto  
 Puntero a una estructura de tipo [tm](../../c-runtime-library/standard-types.md). Los campos de la estructura devuelta contienen el valor evaluado del argumento de `timer` en hora UTC y no en hora local. Cada uno de los campos de la estructura es de tipo `int`, como se indica a continuación:  
  
 `tm_sec`  
 Segundos después del minuto (0 - 59).  
  
 `tm_min`  
 Minutos después de la hora (0 - 59).  
  
 `tm_hour`  
 Horas desde la medianoche (0 - 23).  
  
 `tm_mday`  
 Día del mes (1-31).  
  
 `tm_mon`  
 Mes (0 - 11; Enero = 0).  
  
 `tm_year`  
 Año (año actual menos 1900).  
  
 `tm_wday`  
 Día de la semana (0 - 6; El domingo = 0).  
  
 `tm_yday`  
 Día del año (0 - 365; El 1 de enero = 0).  
  
 `tm_isdst`  
 Es siempre 0 para `gmtime`.  
  
 Las versiones de 32 bits y 64 bits de `gmtime`, `mktime`, `mkgmtime` y `localtime` usan una estructura de `tm` común por subproceso para realizar la conversión. Cada llamada a una de estas funciones destruye el resultado de las llamadas anteriores. Si `timer` representa una fecha anterior a la medianoche del 1 de enero de 1970, `gmtime` devuelve `NULL`. No se devuelve ningún error.  
  
 `_gmtime64`, que usa la estructura de `__time64_t`, permite expresar fechas hasta las 23:59:59 del 31 de diciembre de 3000, hora UTC, mientras que `_gmtime32` solo representa fechas hasta las 23:59:59 del 18 de enero de 2038, hora UTC. La medianoche del 1 de enero de 1970 es el límite inferior del intervalo de fechas para ambas funciones.  
  
 `gmtime` es una función insertada que se evalúa como `_gmtime64`, y `time_t` es equivalente a `__time64_t` a menos que se defina `_USE_32BIT_TIME_T`. Si es necesario que el compilador interprete `time_t` como el valor `time_t` de 32 bits anterior, puede definir `_USE_32BIT_TIME_T`, pero si lo hace `gmtime` se insertará en `_gmtime32` y `time_t` se definirá como `__time32_t`. Esta operación no es recomendable, porque no se permite en plataformas de 64 bits y, en todo caso, la aplicación puede producir un error después del 18 de enero de 2038.  
  
 Estas funciones validan sus parámetros. Si `timer` es un puntero nulo, o si el valor del temporizador es negativo, estas funciones invocan un controlador de parámetros no válidos, tal y como se describe en [Validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, las funciones devuelven `NULL` y establecen `errno` en `EINVAL`.  
  
## <a name="remarks"></a>Comentarios  
 La función `_gmtime32` desglosa el valor de `timer` y lo almacena en una estructura asignada estáticamente de tipo `tm`, definida en TIME.H. El valor de `timer` se suele obtener de una llamada a la función `time`.  
  
> [!NOTE]
>  En la mayoría de los casos, el entorno de destino intenta determinar si está vigente el horario de verano. La biblioteca en tiempo de ejecución de C usa las reglas de Estados Unidos para implementar el cálculo del horario de verano (DST).  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 Para obtener información adicional sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Ejemplo  
  
```C  
// crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time is Tue Feb 12 23:11:31 2002  
```  
  
## <a name="see-also"></a>Vea también  
 [Administración del tiempo](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)