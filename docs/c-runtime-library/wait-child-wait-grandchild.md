---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
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
ms.openlocfilehash: 842d2121ae1bc1f90f50f7fe3feb2a109af5c813
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD
## <a name="syntax"></a>Sintaxis  
  
```  
  
#include <process.h>  
  
```  
  
## <a name="remarks"></a>Comentarios  
 La función `_cwait` se puede usar en cualquier proceso para esperar a cualquier otro proceso (si se conoce el identificador de proceso). El argumento de acción puede ser cualquiera de los siguientes valores:  
  
|Constante|Significado|  
|--------------|-------------|  
|`_WAIT_CHILD`|El proceso que realiza la llamada espera hasta que finaliza el proceso nuevo especificado.|  
|`_WAIT_GRANDCHILD`|El proceso que realiza la llamada espera hasta que el nuevo proceso especificado y todos los procesos creados por ese proceso nuevo finalizan.|  
  
## <a name="see-also"></a>Vea también  
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)