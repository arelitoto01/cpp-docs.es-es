---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: cf4cea35386d1f781d6d2946c1730ba2e18dacea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624049"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Específicos de Microsoft**

Las llamadas del **versión** función miembro de `IUnknown` en el puntero de interfaz encapsulado.

## <a name="syntax"></a>Sintaxis

```
void Release( );
```

## <a name="remarks"></a>Comentarios

Las llamadas `IUnknown::Release` en el puntero de interfaz encapsulado y generar un `E_POINTER` error si este puntero de interfaz es NULL.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[_com_ptr_t (Clase)](../cpp/com-ptr-t-class.md)