---
title: char_traits&lt;char16_t&gt; (Struct)
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: def0023b259a7b4816bdda29684c1dd9853d5f5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619107"
---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt; (Struct)

Un struct que es una especialización del struct de plantilla **char_traits\<CharType>** para un elemento de tipo `char16_t`.

## <a name="syntax"></a>Sintaxis

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>Comentarios

La especialización permite que struct aproveche las funciones de biblioteca que manipulan objetos del tipo `char16_t`.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<string>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[\<string>](../standard-library/string.md)<br/>
[char_traits (Struct)](../standard-library/char-traits-struct.md)<br/>
[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
