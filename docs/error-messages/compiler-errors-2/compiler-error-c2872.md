---
title: Error del compilador C2872 | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: c81fc315c4bb893b96876b7b67b42806a3246583
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2872"></a>Error del compilador C2872
'*símbolo*': símbolo ambiguo  
  
El compilador no puede determinar los símbolos que se hace referencia a. Más de un símbolo con el nombre especificado está en el ámbito. Vea las notas que siguen el mensaje de error para las ubicaciones de archivo y las declaraciones el compilador encontró para el símbolo ambiguo. Para corregir este problema, puede calificar por completo el símbolo ambiguo mediante el uso de su espacio de nombres, por ejemplo, `std::byte` o `::byte`. También puede usar un [alias de espacio de nombres](../../cpp/namespaces-cpp.md#namespace_aliases) para conceder a un espacio de nombres incluye un nombre corto adecuado para su uso al eliminar la ambigüedad de símbolos en el código fuente.  
  
El error C2872 puede producirse si un archivo de encabezado incluye un [using (directiva)](../../cpp/namespaces-cpp.md#using_directives), y se incluye un archivo de encabezado posteriores que contiene un tipo que también está en el espacio de nombres especificado en el `using` directiva. Especifique un `using` directiva sólo después de que todos los archivos de encabezado se especifican con `#include`.  
  
 Para obtener más información sobre el error C2872, vea los artículos de Knowledge Base [PRB: compilador errores cuando usas #import con XML en Visual C++ .NET](http://support.microsoft.com/kb/316317) y ["error C2872 de Error: 'Plataforma': símbolo ambiguo" mensaje de error cuando se usa el espacio de nombres Windows::Foundation::Metadata en Visual Studio 2013](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera el error C2872, ya que se realiza una referencia ambigua a una variable denominada `i`; dos variables con el mismo nombre que se encuentran dentro del ámbito:  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```