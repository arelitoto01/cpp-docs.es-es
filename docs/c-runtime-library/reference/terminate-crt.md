---
title: terminate (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- terminate
dev_langs:
- C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 101ecce2a1cb991c5f4d0edda6fea5f2a1818fc0
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---
# <a name="terminate-crt"></a>terminate (CRT)
Llama a `abort` o a una función que se especifique mediante `set_terminate`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void terminate( void );  
```  
  
## <a name="remarks"></a>Comentarios  
 La función `terminate` se usa con el control de excepciones de C++ y se llama en los casos siguientes:  
  
-   Cuando no se encuentra un controlador catch coincidente para una excepción de C++.  
  
-   Cuando una función de destructor produce una excepción durante un desenredo de pila.  
  
-   Cuando la pila se daña después de producir una excepción.  
  
 `terminate` llama a `abort` de forma predeterminada. Puede cambiar este comportamiento predeterminado si escribe su propia función de finalización y llama a `set_terminate` con el nombre de esta función como argumento. `terminate` llama a la última función especificada como argumento para `set_terminate`. Para más información, vea [Excepciones de C++ no controladas](../../cpp/unhandled-cpp-exceptions.md).  
  
## <a name="requirements"></a>Requisitos  
  
|Rutina|Encabezado necesario|  
|-------------|---------------------|  
|`terminate`|\<eh.h>|  
  
 Para obtener información adicional de compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md) en la introducción.  
  
## <a name="example"></a>Ejemplo  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
```Output  
term_func() was called by terminate().  
```  
  
## <a name="see-also"></a>Vea también  
 [Rutinas para el control de excepciones](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)