---
title: Error del compilador C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: f4a17557e5e4ca1eb3f69561c964c9bbe24bb70d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440370"
---
# <a name="compiler-error-c2017"></a>Error del compilador C2017

secuencia de escape no válida

Una secuencia de escape, por ejemplo, \t, aparece fuera de un carácter o cadena constante.

El ejemplo siguiente genera C2017:

```
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017 puede producirse cuando se usa el operador de generación con cadenas que incluyen secuencias de escape.

El ejemplo siguiente genera C2017:

```
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```