---
title: Operadores de &lt;thread&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 04b9f1a76c637f7bca9f230092e51246da0c6075
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="ltthreadgt-operators"></a>Operadores de &lt;thread&gt;
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|  
|[operator==](#op_eq_eq)|  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
 Determina si un objeto `thread::id` es mayor o igual que otro objeto.  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `!(Left < Right)`  
  
### <a name="remarks"></a>Comentarios  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_gt"></a>  operator&gt;  
 Determina si un objeto `thread::id` es mayor que otro objeto.  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `Right < Left`  
  
### <a name="remarks"></a>Comentarios  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
 Determina si un objeto `thread::id` es menor o igual que otro objeto.  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `!(Right < Left)`  
  
### <a name="remarks"></a>Comentarios  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_lt"></a>  operator&lt;  
 Determina si un objeto `thread::id` es menor que otro objeto.  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `true` si `Left` precede a `Right` en la ordenación total. De lo contrario es `false`.  
  
### <a name="remarks"></a>Comentarios  
 El operador define una ordenación total en todos los objetos `thread::id`. Estos objetos pueden usarse como claves en contenedores asociativos.  
  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_neq"></a>  operator!=  
 Compara dos objetos `thread::id` para determinar si no son iguales.  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `!(Left == Right)`  
  
### <a name="remarks"></a>Comentarios  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_eq_eq"></a>  operator==  
 Compara dos objetos `thread::id` para determinar si son iguales.  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parámetros  
 `Left`  
 Objeto `thread::id` izquierdo.  
  
 `Right`  
 Objeto `thread::id` derecho.  
  
### <a name="return-value"></a>Valor devuelto  
 `true` si los dos objetos representan el mismo subproceso de ejecución o si ninguno de estos objetos representa un subproceso de ejecución. De lo contrario es `false`.  
  
### <a name="remarks"></a>Comentarios  
 Esta función no produce ninguna excepción.  
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
 Inserta una representación de texto de un objeto `thread::id` en una secuencia.  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>Parámetros  
 `Ostr`  
 Un objeto [basic_ostream](../standard-library/basic-ostream-class.md).  
  
 `Id`  
 Objeto `thread::id`.  
  
### <a name="return-value"></a>Valor devuelto  
 `Ostr`Operador  
  
### <a name="remarks"></a>Comentarios  
 Esta función inserta `Id` en `Ostr`.  
  
 Si dos objetos `thread::id` son iguales, las representaciones de texto insertadas de dichos objetos son iguales.  
  
## <a name="see-also"></a>Vea también  
 [\<thread>](../standard-library/thread.md)



