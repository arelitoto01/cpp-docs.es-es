---
title: "Funciones Bessel: _j0, _j1, _jn, _y0, _y1, _yn | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.bessel"
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funciones Bessel"
  - "_j0 (función)"
  - "_j1 (función)"
  - "_jn (función)"
  - "_y0 (función)"
  - "_y1 (función)"
  - "_yn (función)"
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Funciones Bessel: _j0, _j1, _jn, _y0, _y1, _yn
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcula la función Bessel de la clase del primer o segundo tipo, de órdenes 0, 1 o n. Lasfunciones Bessel suelen usarse en las matemáticas de la teoría de las ondas electromagnéticas.  
  
## Sintaxis  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### Parámetros  
 `x`  
 Valor de punto flotante.  
  
 `n`  
 Orden de enteros de la función Bessel.  
  
## Valor devuelto  
 Cada una de estas rutinas devuelve una función Bessel de `x`. Si `x` es negativo en las funciones `_y0`, `_y1` o `_yn`, la rutina se establece `errno` en `EDOM`, imprime un mensaje de error `_DOMAIN``stderr` y devuelve `_HUGE_VAL`. Puede modificar el control de errores mediante `_matherr`.  
  
## Comentarios  
 Las rutinas `_j0`, `_j1` y `_jn` devuelven funciones Bessel del primer tipo: ordena 0, 1 y n, respectivamente.  
  
|Entrada|Excepción SEH|Excepción de Matherr|  
|-------------|-------------------|--------------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 Las rutinas `_y0`, `_y1` y `_yn` devuelven funciones Bessel del segundo tipo: ordena 0, 1 y n, respectivamente.  
  
|Entrada|Excepción SEH|Excepción de Matherr|  
|-------------|-------------------|--------------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;\<0.0|`INVALID`|`_DOMAIN`|  
  
## Requisitos  
  
|Rutina|Encabezado necesario|  
|------------|--------------------------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath\> \(C\+\+\), \<math.h\> \(C, C\+\+\)|  
  
 Para obtener información adicional de compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## Ejemplo  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Funciones Bessel para x = 2.387000: Tipo   Orden  Función     Resultado Primero  0      _j0( x )     0.009288 Primero  1      _j1( x )     0.522941 Primero  2      _jn( 2, x )  0.428870 Primero  3      _jn( 3, x )  0.195734 Primero  4      _jn( 4, x )  0.063131 Segundo 0      _y0( x )     0.511681 Segundo 1      _y1( x )     0.094374 Segundo 2      _yn( 2, x )  -0.432608 Segundo 3      _yn( 3, x )  -0.819314 Segundo 4      _yn( 4, x )  -1.626833  
```  
  
## Vea también  
 [Compatibilidad con el punto flotante](../../c-runtime-library/floating-point-support.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)