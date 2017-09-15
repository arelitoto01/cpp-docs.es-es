---
title: Clase CSimpleArray | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e261f95a375a2edda1d543a36b605d23fc718b99
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearray-class"></a>Clase CSimpleArray
Esta clase proporciona métodos para administrar una matriz simple.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>Parámetros  
 `T`  
 El tipo de datos para almacenar en la matriz.  
  
 `TEqual`  
 Un objeto de rasgo, definiendo la prueba de igualdad para los elementos de tipo `T`.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|El constructor para la matriz simple.|  
|[CSimpleArray:: ~ CSimpleArray](#dtor)|El destructor para la matriz simple.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|Agrega un nuevo elemento a la matriz.|  
|[CSimpleArray::Find](#find)|Busca un elemento de la matriz.|  
|[CSimpleArray::GetData](#getdata)|Devuelve un puntero a los datos almacenados en la matriz.|  
|[CSimpleArray::GetSize](#getsize)|Devuelve el número de elementos almacenados en la matriz.|  
|[CSimpleArray::Remove](#remove)|Quita un elemento determinado de la matriz.|  
|[CSimpleArray::RemoveAll](#removeall)|Quita todos los elementos de la matriz.|  
|[CSimpleArray::RemoveAt](#removeat)|Quita el elemento especificado de la matriz.|  
|[CSimpleArray::SetAtIndex](#setatindex)|Establece el elemento especificado de la matriz.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|Recupera un elemento de la matriz.|  
|[CSimpleArray::operator =](#operator_eq)|Operador de asignación.|  

  
## <a name="remarks"></a>Comentarios  
 `CSimpleArray`Proporciona métodos para crear y administrar la matriz de cualquier tipo simple, `T`.  
  
 El parámetro `TEqual` proporciona un medio para definir una función de la igualdad de dos elementos de tipo `T`. Al crear una clase similar a [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), es posible modificar el comportamiento de la prueba de igualdad para cualquier matriz determinado. Por ejemplo, cuando se trabaja con una matriz de punteros, puede ser útil definir la igualdad como según los valores que hacen referencia a los punteros. La implementación predeterminada usa **operator=()**.  
  
 Ambos `CSimpleArray` y [CSimpleMap](../../atl/reference/csimplemap-class.md) están diseñados para un número pequeño de elementos. [CAtlArray](../../atl/reference/catlarray-class.md) y [CAtlMap](../../atl/reference/catlmap-class.md) debe utilizarse cuando la matriz contiene un gran número de elementos.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlsimpcoll.h  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities&#86;](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleArray::Add  
 Agrega un nuevo elemento a la matriz.  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>Parámetros  
 *t*  
 Elemento que se va a agregar a la matriz.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve TRUE si el elemento se agrega correctamente a la matriz, FALSE en caso contrario.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities&#87;](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="csimplearray"></a>CSimpleArray::CSimpleArray  
 El constructor para el objeto de matriz.  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>Parámetros  
 *src*  
 Objeto `CSimpleArray` existente.  
  
### <a name="remarks"></a>Comentarios  
 Inicializa los miembros de datos, crear un nuevo vacío `CSimpleArray` objeto o una copia de un miembro de `CSimpleArray` objeto.  
  
##  <a name="dtor"></a>CSimpleArray:: ~ CSimpleArray  
 Destructor.  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>Comentarios  
 Libera todos los recursos asignados.  
  
##  <a name="find"></a>CSimpleArray::Find  
 Busca un elemento de la matriz.  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>Parámetros  
 *t*  
 El elemento que desea buscar.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el índice del elemento encontrado o -1 si no se encuentra el elemento.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities&#88;](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="getdata"></a>CSimpleArray::GetData  
 Devuelve un puntero a los datos almacenados en la matriz.  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un puntero a los datos de la matriz.  
  
##  <a name="getsize"></a>CSimpleArray::GetSize  
 Devuelve el número de elementos almacenados en la matriz.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el número de elementos almacenados en la matriz.  
  
##  <a name="operator_at"></a>CSimpleArray::operator\[\]  
 Recupera un elemento de la matriz.  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 El índice del elemento.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el elemento de la matriz que se hace referencia a `nIndex`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities&#89;](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="operator_eq"></a>CSimpleArray::operator =  
 Operador de asignación.  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>Parámetros  
 *src*  
 La matriz para copiar.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve un puntero a la actualización `CSimpleArray` objeto.  
  
### <a name="remarks"></a>Comentarios  
 Copia todos los elementos de la `CSimpleArray` hacen referencia al objeto *src* en el objeto de matriz actual, reemplazando todos los datos existentes.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATL_Utilities&#90;](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="remove"></a>CSimpleArray::Remove  
 Quita un elemento determinado de la matriz.  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>Parámetros  
 *t*  
 Elemento que se va a quitar de la matriz.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve TRUE si el elemento se encuentra y quita, FALSE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se quita un elemento, se vuelven a numerar los elementos restantes de la matriz para rellenar el espacio vacío.  
  
##  <a name="removeall"></a>CSimpleArray::RemoveAll  
 Quita todos los elementos de la matriz.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Comentarios  
 Quita todos los elementos almacenados actualmente en la matriz.  
  
##  <a name="removeat"></a>CSimpleArray::RemoveAt  
 Quita el elemento especificado de la matriz.  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Selecciona el elemento que se va a quitar del índice.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve TRUE si el elemento se ha quitado, y FALSE si el índice no es válido.  
  
### <a name="remarks"></a>Comentarios  
 Cuando se quita un elemento, se vuelven a numerar los elementos restantes de la matriz para rellenar el espacio vacío.  
  
##  <a name="setatindex"></a>CSimpleArray::SetAtIndex  
 Establezca el elemento especificado de la matriz.  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>Parámetros  
 `nIndex`  
 Índice del elemento que se va a cambiar.  
  
 *t*  
 El valor que se va a asignar al elemento especificado.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve TRUE si es correcto, FALSE si el índice no es válido.  
  
## <a name="see-also"></a>Vea también  
 [Información general de la clase](../../atl/atl-class-overview.md)
