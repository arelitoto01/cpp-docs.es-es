---
title: setvbuf (Constantes) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
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
ms.openlocfilehash: 72597020534100f86de855db0095995e50d10f9b
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="setvbuf-constants"></a>setvbuf (Constantes)
## <a name="syntax"></a>Sintaxis  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Comentarios  
 Estas constantes representan el tipo de búfer para `setvbuf`.  
  
 Los posibles valores se indican mediante las constantes de manifiesto siguientes:  
  
|Constante|Significado|  
|--------------|-------------|  
|`_IOFBF`|Almacenamiento en búfer completo: se usa el búfer especificado en la llamada a `setvbuf` y su tamaño se corresponde con el especificado en la llamada `setvbuf`. Si el puntero de búfer es **NULL**, se usa el búfer del tamaño especificado asignado automáticamente.|  
|`_IOLBF`|Igual a `_IOFBF`.|  
|`_IONBF`|No se usa ningún búfer, con independencia de los argumentos de la llamada a `setvbuf`.|  
  
## <a name="see-also"></a>Vea también  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)