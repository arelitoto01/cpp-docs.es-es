---
title: _abnormal_termination | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
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
ms.openlocfilehash: d826dd3c0293393a960657f45ac4b68370d7030c
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="abnormaltermination"></a>_abnormal_termination
Indica si el bloque `__finally` de una [instrucción try-finally](../cpp/try-finally-statement.md) se especifica mientras el sistema ejecuta una lista interna de controladores de terminación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si el sistema *desenreda* la pila; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Se trata de una función interna que se usa para administrar las excepciones de desenredado y no está pensada para que se llame desde el código de usuario.  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>Vea también  
 [try-finally (Instrucción)](../cpp/try-finally-statement.md)