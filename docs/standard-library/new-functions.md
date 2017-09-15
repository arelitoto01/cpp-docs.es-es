---
title: Funciones &lt;new&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 53a31f533ee777dbbcc486283034094481ab0c31
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="ltnewgt-functions"></a>Funciones &lt;new&gt;
|||  
|-|-|  
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|  
  
##  <a name="nothrow"></a> nothrow  
 Proporciona un objeto que se usará como argumento para las versiones `nothrow` de **new** y **delete**.  
  
```  
extern const std::nothrow_t nothrow;  
```  
  
### <a name="remarks"></a>Comentarios  
 El objeto se usa como un argumento de función para que coincida con el tipo de parámetro [std::nothrow_t](../standard-library/nothrow-t-structure.md).  
  
### <a name="example"></a>Ejemplo  
  Vea [operator new](../standard-library/new-operators.md#op_new) y [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) para obtener ejemplos de cómo se usa `std::nothrow_t` como un parámetro de función.  
  
##  <a name="set_new_handler"></a> set_new_handler  
 Instala una función de usuario que se va a llamar cuando `operator new` no pueda asignar memoria.  
  
```  
new_handler set_new_handler(new_handler Pnew) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `Pnew`  
 El objeto new_handler que se va a instalar.  
  
### <a name="return-value"></a>Valor devuelto  
 0 en la primera llamada y el valor `new_handler` anterior en las llamadas posteriores.  
  
### <a name="remarks"></a>Comentarios  
 La función almacena `Pnew` en un puntero del [controlador nuevo](../standard-library/new-typedefs.md#new_handler) estático que mantiene y, después, devuelve el valor almacenado previamente en el puntero. El controlador nuevo se usa mediante [operator new](../standard-library/new-operators.md#op_new)( **size_t**).  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// new_set_new_handler.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
void __cdecl newhandler( )  
{  
   cout << "The new_handler is called:" << endl;  
   throw bad_alloc( );  
   return;  
}  
  
int main( )   
{  
   set_new_handler (newhandler);  
   try  
   {  
      while ( 1 )   
      {  
         new int[5000000];  
         cout << "Allocating 5000000 ints." << endl;  
      }  
   }  
   catch ( exception e )  
   {  
      cout << e.what( ) << endl;  
   }  
}  
```  
  
```Output  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
The new_handler is called:  
bad allocation  
```  
  
## <a name="see-also"></a>Vea también  
 [\<new>](../standard-library/new.md)

