---
title: Compatibilidad | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: c0c031bfc53bd28c6bd00e4b6e0f136c2bf607b7
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="compatibility"></a>Compatibilidad
La biblioteca en tiempo de ejecución de C Universal (UCRT) admite la mayor parte de la biblioteca estándar de C requerida para la conformidad con C++. Implementa la biblioteca C99 (ISO/IEC 9899:1999), con las excepciones de las macros de tipo genérico definidas en \<tgmath.h> y la compatibilidad de tipos estricta en \<complex.h>. La UCRT también implementa un gran subconjunto de la biblioteca de C POSIX.1 (ISO/IEC 9945-1:1996, la interfaz de programación de aplicaciones de sistema de POSIX), pero no cumple totalmente ningún estándar POSIX concreto.  Además, la UCRT implementa varias macros y funciones específicas de Microsoft que no forman parte de un estándar.  
  
 Las funciones concretas de la implementación de Microsoft de Visual C++ se encuentran en la biblioteca vcruntime.  Muchas de estas funciones son para uso interno y no es posible llamarlas mediante código de usuario. Algunas están documentadas para su uso en la depuración y la compatibilidad de implementación.  
  
 El estándar de C++ reserva los nombres que comienzan con un carácter de subrayado en el espacio de nombres global para la implementación. Como las funciones POSIX están en el espacio de nombres global, pero no forman parte de la biblioteca en tiempo de ejecución estándar de C, las implementaciones específicas de Microsoft de estas funciones tienen un carácter de subrayado inicial. Para la portabilidad, la UCRT también admite los nombres predeterminados, pero el compilador de Visual C++ emite una advertencia de desuso cuando se compila código que los usa. Solo los nombres POSIX predeterminados están en desuso, las funciones no. Para suprimir la advertencia, defina `_CRT_NONSTDC_NO_WARNINGS` antes de incluir encabezados en el código que utiliza los nombres POSIX originales.  
  
 Algunas funciones de la biblioteca de C estándar tienen un historial de uso no seguro, debido a mal uso de parámetros y búferes sin comprobar. Estas funciones son a menudo el origen de los problemas de seguridad en el código. Microsoft creó un conjunto de versiones más seguras de estas funciones que comprueban el uso de parámetros e invocan el controlador de parámetros no válidos si se detecta un problema en tiempo de ejecución.  De forma predeterminada, el compilador de Visual C++ emite una advertencia de desuso cuando se utiliza una función que tiene una variante más segura disponible. Al compilar el código como C++, puede definir `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` en 1 para eliminar la mayoría de las advertencias. De esta forma, se usan sobrecargas de plantilla para llamar a las variantes más seguras a la vez que se mantiene el código portable. Para suprimir la advertencia, defina `_CRT_SECURE_NO_WARNINGS` antes de incluir encabezados en el código que utiliza estas funciones. Para obtener más información, consulta [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
 A menos que se indique lo contrario en la documentación de funciones concretas, la UCRT es compatible con la API de Windows.  Algunas funciones no se admiten en aplicaciones de la Tienda de Windows 8 ni en aplicaciones universales de Windows en Windows 10. Estas funciones se muestran en [Funciones de CRT que no se admiten con /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx), donde se enumeran las funciones que no admite [Windows Runtime](http://msdn.microsoft.com/en-us/9a1a18b8-9802-4ec5-b9de-0d2dfdf414e9).  
  
## <a name="related-articles"></a>Artículos relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Aplicaciones de la Tienda Windows, Windows Runtime y tiempo de ejecución de C](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Describe cuándo no son compatibles las rutinas UCRT con aplicaciones universales de Windows o aplicaciones de la Tienda Windows.|  
|[Conformidad con ANSI C](../c-runtime-library/ansi-c-compliance.md)|Describe la nomenclatura conforme a los estándares en la UCRT.|  
|[UNIX](../c-runtime-library/unix.md)|Proporciona directrices para trasladar programas a UNIX.|  
|[Plataformas de Windows (CRT)](../c-runtime-library/windows-platforms-crt.md)|Enumera los sistemas operativos que admite CRT.|  
|[Compatibilidad con versiones anteriores](../c-runtime-library/backward-compatibility.md)|Describe cómo asignar nombres de CRT antiguos a los nombres nuevos.|  
|[Características de la biblioteca CRT](../c-runtime-library/crt-library-features.md)|Proporciona información general sobre los archivos de biblioteca (.lib) de CRT y las opciones del compilador asociadas.|