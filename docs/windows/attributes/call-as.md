---
title: call_as (atributo de COM de C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: 16839f5a5040e6b0019005912782ba359178cc47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579908"
---
# <a name="callas"></a>call_as

Permite un [local](local-cpp.md) función a la que se asignan a una función remota para que cuando se llama a la función remota, se invoca la función local.

## <a name="syntax"></a>Sintaxis

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Parámetros

*function*<br/>
La función local que desea que se llama cuando se invoca una función remota.

## <a name="remarks"></a>Comentarios

El **call_as** atributo de C++ tiene la misma funcionalidad que el [call_as](/windows/desktop/Midl/call-as) atributo MIDL.

## <a name="example"></a>Ejemplo

El código siguiente muestra cómo puede usar **call_as** para asignar una función utilizables (`f1`) a una función remota (`Remf1`):

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Contexto de atributo

|||
|-|-|
|**Se aplica a**|Método de interfaz|
|**Reiterativo**|No|
|**Atributos requeridos**|Ninguna|
|**Atributos no válidos**|Ninguna|

Para obtener más información acerca de los contextos de atributo, consulte [Contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Vea también

[Atributos IDL](idl-attributes.md)<br/>
[Atributos de método](method-attributes.md)<br/>
[local](local-cpp.md)