---
title: _except_handler3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
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
ms.openlocfilehash: ce3717ea39cec55ab982de3c9d8fddd0b50632ee
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="excepthandler3"></a>_except_handler3
Función de CRT interna. Usada por un marco para encontrar el controlador de excepciones adecuado para procesar la excepción actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 [in] `exception_record`  
 Información sobre la excepción específica.  
  
 [in] `registration`  
 Registro que indica qué tabla de ámbito se debe usar para encontrar el controlador de excepciones.  
  
 [in] `context`  
 Reservado.  
  
 [in] `dispatcher`  
 Reservado.  
  
## <a name="return-value"></a>Valor devuelto  
 En caso de que una excepción deba descartarse, devuelve `DISPOSITION_DISMISS`. Si la excepción debe trasladarse a un nivel superior de controladores de excepciones, devuelve `DISPOSITION_CONTINUE_SEARCH`.  
  
## <a name="remarks"></a>Comentarios  
 Si se encuentra un controlador de excepciones adecuado con este método, la excepción se pasa a dicho controlador. En este caso, el método no regresa al código que lo llamó y el valor devuelto es irrelevante.  
  
## <a name="see-also"></a>Vea también  
 [Referencia alfabética de funciones](../c-runtime-library/reference/crt-alphabetical-function-reference.md)