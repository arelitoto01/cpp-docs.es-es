---
title: logical_or (struct)
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::logical_or
helpviewer_keywords:
- logical_or class
- logical_or struct
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
ms.openlocfilehash: 9921fe01b7b2a9b5c581839af4af5c125ddc7108
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523408"
---
# <a name="logicalor-struct"></a>logical_or (struct)

Objeto de función predefinido que realiza la operación de disyunción lógica (`operator||`) sobre sus argumentos.

## <a name="syntax"></a>Sintaxis

```
template <class Type = void>
struct logical_or : public binary_function<Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator||
template <>
struct logical_or<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) || std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parámetros

*Tipo*, *T*, *U* cualquier tipo que admita un `operator||` que toma operandos de los tipos especificados o deducidos.

*Izquierda*<br/>
Operando izquierdo de la operación de disyunción lógica. La plantilla no especializada toma un argumento de referencia de valor l de tipo *tipo*. La plantilla especializada realiza el reenvío de valor l directo y los argumentos de referencia de valor r del tipo deducen *T*.

*Derecha*<br/>
Operando derecho de la operación de disyunción lógica. La plantilla no especializada toma un argumento de referencia de valor l de tipo *tipo*. La plantilla especializada realiza el reenvío de valor l directo y los argumentos de referencia de valor r del tipo deducen *U*.

## <a name="return-value"></a>Valor devuelto

Resultado de `Left || Right`. La plantilla especializada realiza el reenvío directo del resultado, que tiene el tipo devuelto por `operator||`.

## <a name="remarks"></a>Comentarios

Para los tipos definidos por el usuario, no se realiza la evaluación cortocircuitada de los operandos. `operator||` evalúa ambos argumentos.

## <a name="example"></a>Ejemplo

```cpp
// functional_logical_or.cpp
// compile with: /EHsc
#include <deque>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   deque <bool> d1, d2, d3( 7 );
   deque <bool>::iterator iter1, iter2, iter3;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
   {
      d1.push_back((bool)((rand() % 2) != 0));
   }

   int j;
   for ( j = 0 ; j < 7 ; j++ )
   {
      d2.push_back((bool)((rand() % 2) != 0));
   }

   cout << boolalpha;    // boolalpha I/O flag on

   cout << "Original deque:\n d1 = ( " ;
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )
      cout << *iter1 << " ";
   cout << ")" << endl;

   cout << "Original deque:\n d2 = ( " ;
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )
      cout << *iter2 << " ";
   cout << ")" << endl;

   // To find element-wise disjunction of the truth values
   // of d1 & d2, use the logical_or function object
   transform( d1.begin( ), d1.end( ), d2.begin( ),
      d3.begin( ), logical_or<bool>( ) );
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )
      cout << *iter3 << " ";
   cout << ")" << endl;
}
/* Output:
Original deque:
d1 = ( true true false false true false false )
Original deque:
d2 = ( false false false true true true true )
The deque which is the disjuction of d1 & d2 is:
d3 = ( true true false true true true true )
*/
```

## <a name="requirements"></a>Requisitos

**Encabezado:** \<functional>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
