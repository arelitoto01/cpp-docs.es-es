---
title: "clog10, clog10f, clog10l | Microsoft Docs"
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
  - "clog10"
  - "clog10f"
  - "clog10l"
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
  - "clog10"
  - "clog10f"
  - "clog10l"
  - "complex/clog10"
  - "complex/clog10f"
  - "complex/clog10l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clog10 (función)"
  - "clog10f (función)"
  - "clog10l (función)"
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# clog10, clog10f, clog10l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recupera el logaritmo en base 10 de un número complejo.  
  
## Sintaxis  
  
```  
_Dcomplex clog10(   
   _Dcomplex z   
);  
_Fcomplex clog10(   
  _Fcomplex z   
);  // C++ only  
_Lcomplex clog10(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clog10f(   
   _Fcomplex z   
);  
_Lcomplex clog10l(   
   _Lcomplex z   
);  
```  
  
#### Parámetros  
 `z`  
 Base del logaritmo.  
  
## Valor devuelto  
 Los valores devueltos posibles son:  
  
|parámetro de z|Valor devuelto|  
|--------------------|--------------------|  
|Positivo|Logaritmo en base 10 de z|  
|Cero|\- ∞|  
|Negativo|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## Comentarios  
 Puesto que C\+\+ permite las sobrecargas, es posible llamar a las sobrecargas de `clog10` que toman y devuelven los valores `_Fcomplex` y `_Lcomplex`. En un programa de C, `clog10` siempre toma y devuelve un `_Dcomplex` valor.  
  
## Requisitos  
  
|Rutina|Encabezado C|Encabezado C\+\+|  
|------------|------------------|----------------------|  
|`clog10`, `clog10f`, `clogl`|\<complex.h\>|\< ccomplex \>|  
  
 Para obtener más información de compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la Introducción.  
  
## Vea también  
 [Referencia alfabética de funciones](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [CLOG, clogf, clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)