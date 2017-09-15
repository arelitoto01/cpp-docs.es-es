---
title: pointer_to_unary_function (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_unary
- pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 2089886ff915ce9176c883c9dc552f2a45b5c576
ms.contentlocale: es-es
ms.lasthandoff: 04/19/2017

---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function (Clase)
Convierte un puntero a función unaria en una función unaria adaptable.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```  
  
#### <a name="parameters"></a>Parámetros  
 `pfunc`  
 La función binaria que se va a convertir.  
  
 `left`  
 El objeto al que *\*pfunc* está llamado.  
  
## <a name="return-value"></a>Valor devuelto  
 La clase de plantilla almacena una copia de **pfunc**. Define su función miembro `operator()` para que devuelva (\* **pfunc**)(_ *Left*).  
  
## <a name="remarks"></a>Comentarios  
 Un puntero de función unaria es un objeto de función y puede pasarse a cualquier algoritmo de la biblioteca estándar de C++ que esté esperando una función unaria como un parámetro, pero no es adaptable. Para usarlo como un adaptador, por ejemplo al enlazar un valor a este o usándolo con un negador, debe proporcionarse con los tipos anidados **argument_type** y **result_type** que hacen posible dicha adaptación. La conversión mediante `pointer_to_unary_function` permite a los adaptadores de función que funcionen con punteros de función binaria.  
  
## <a name="example"></a>Ejemplo  
 El constructor de `pointer_to_unary_function` no suele usarse directamente. Vea la función auxiliar [ptr_fun](../standard-library/functional-functions.md#ptr_fun) para obtener un ejemplo de cómo declarar y usar el predicador del adaptador de `pointer_to_unary_function`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<functional>  
  
 **Espacio de nombres:** std  
  
## <a name="see-also"></a>Vea también  
 [Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)



