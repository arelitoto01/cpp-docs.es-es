---
title: Error del compilador C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: 21ca3bdcb156aaa654ae3d5d0c1c467a97129dcc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588609"
---
# <a name="compiler-error-c2509"></a>Error del compilador C2509

'identifier': función miembro no declarada en 'class'

La función no se declara en la clase especificada.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C2509.

```
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```