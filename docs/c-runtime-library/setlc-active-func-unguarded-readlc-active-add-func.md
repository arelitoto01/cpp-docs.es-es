---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs:
- C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
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
ms.openlocfilehash: 08cda2e2b3f04663f3435ac9259117d54de80beb
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func
OBSOLETO. CRT exporta estas funciones internas únicamente para conservar la compatibilidad binaria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto no es significativo.  
  
## <a name="remarks"></a>Comentarios  
 Las funciones de CRT internas `___setlc_active_func` y `___unguarded_readlc_active_add_func` están obsoletas y ya no se usan, pero la biblioteca de CRT las puede exportar para conservar la compatibilidad binaria. La finalidad primera de `___setlc_active_func` era devolver el número de llamadas activas actualmente a la función `setlocale`. La finalidad primera de `___unguarded_readlc_active_add_func` era devolver el número de funciones que hacían referencia a la configuración local sin bloquearla.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|ninguna|  
  
## <a name="see-also"></a>Vea también  
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)