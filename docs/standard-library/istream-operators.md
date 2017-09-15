---
title: Operadores de &lt;istream&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f73a5e24fd3864a46ac0c50bbdb18a1089a4a05e
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="ltistreamgt-operators"></a>Operadores de &lt;istream&gt;
 
##  <a name="op_gt_gt"></a>  operator&gt;&gt;  
 Extrae caracteres y cadenas del flujo.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>Parámetros  
 `Ch`  
 Un carácter.  
  
 `Istr`  
 Flujo.  
  
 `str`  
 Una cadena.  
  
 `val`  
 Un tipo.  
  
### <a name="return-value"></a>Valor devuelto  
 Flujo.  
  
### <a name="remarks"></a>Comentarios  
 La clase `basic_istream` también define varios operadores de extracción. Para obtener más información, vea [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).  
  
 La función de plantilla:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 extrae hasta *N* - 1 elementos y los almacena en la matriz empezando por _ *Str*. Si `Istr`. [width](../standard-library/ios-base-class.md#width) es mayor que cero, *N* es `Istr`. **width**. En caso contrario, es el tamaño de la matriz más grande de **Elem** que se puede declarar. La función siempre almacena el valor **Elem()** después de los elementos extraídos que haya almacenado. La extracción se detiene anticipadamente al final del archivo, en un carácter con el valor **Elem**(0) (que no se extrae) o en cualquier elemento (que no se extrae) que [ws](../standard-library/istream-functions.md#ws) descartaría. Si la función no extrae ningún elemento, llama a `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). En cualquier caso, llama a `Istr`. **width**(0) y devuelve `Istr`.  
  
 **Nota de seguridad** La cadena terminada en null que se extrae del flujo de entrada no debe superar el tamaño del búfer de destino `str`. Para obtener más información, vea [Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)(Evitar saturaciones del búfer).  
  
 La función de plantilla:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 extrae un elemento, si es posible, y lo almacena en `Ch`. En caso contrario, llama a **is**. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). En cualquier caso, devuelve `Istr`.  
  
 La función de plantilla:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 devuelve `Istr` >> ( `char`**\***) `str`.  
  
 La función de plantilla:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 devuelve `Istr` >> ( **char&**) `Ch`.  
  
 La función de plantilla:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 devuelve `Istr` >> ( **char \***) `str`.  
  
 La función de plantilla:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 devuelve `Istr` >> ( **char&**) `Ch`.  
  
 La función de plantilla:  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 devuelve `Istr` `>>` `val` (y convierte `rvalue reference` en `Istr` en `lvalue` durante el proceso).  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [\<istream>](../standard-library/istream.md)

