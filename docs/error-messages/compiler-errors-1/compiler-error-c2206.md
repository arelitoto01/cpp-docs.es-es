---
title: Error del compilador C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: 3ee2dc24dd2472be8b69a389df1cad77337abf90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511792"
---
# <a name="compiler-error-c2206"></a>Error del compilador C2206

'function' : typedef no se puede utilizar para la definición de función

Se usa una `typedef` para definir un tipo de función.

El ejemplo siguiente genera la advertencia C2206:

```
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```