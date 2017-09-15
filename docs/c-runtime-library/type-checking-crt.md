---
title: "Comprobación de tipos (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: feb455f63b5e55fe055bfe2ad9b0026026fb0626
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="type-checking-crt"></a>Comprobación de tipos (CRT)
El compilador realiza una comprobación de tipos limitada de las funciones que pueden usar un número variable de argumentos, como sigue:  
  
|Llamada a función|Argumentos con tipos comprobados|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Primer argumento (cadena de formato)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Primeros dos argumentos (archivo o búfer y cadena de formato)|  
|`_snprintf_s`|Primeros tres argumentos (archivo o búfer, recuento y cadena de formato)|  
|`_open`|Primeros dos argumentos (ruta de acceso y marca `_open`)|  
|`_sopen_s`|Primeros tres argumentos (ruta de acceso, marca `_open` y modo compartido)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Primeros dos argumentos (ruta de acceso y primer puntero de argumento)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Primeros tres argumentos (marca de modo, ruta de acceso y primer puntero de argumento)|  
  
 El compilador realiza la misma comprobación de tipo limitada en los homólogos de caracteres anchos de estas funciones.  
  
## <a name="see-also"></a>Vea también  
 [Características de la biblioteca CRT](../c-runtime-library/crt-library-features.md)