---
title: Usar encabezados de la biblioteca de C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 69a20e17403e755031466f269b932a4b14aa523b
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="using-c-library-headers"></a>Usar encabezados de la biblioteca de C++
Se incluye el contenido de un encabezado estándar al darle nombre en una directiva de inclusión.  
  
```  
#include <iostream>// include I/O facilities  
```  
  
 Puede incluir los encabezados estándar en cualquier orden, un encabezado estándar más de una vez o dos, o más encabezados estándar que definen la misma macro o el mismo tipo. No incluya un encabezado estándar dentro de una declaración. No defina macros que tengan los mismos nombres que las palabras clave antes de incluir un encabezado estándar.  
  
 Un encabezado de la biblioteca de C++ incluye cualquier otro encabezado de la biblioteca de C++ que necesite para definir los tipos necesarios. (Pero siempre se deben incluir explícitamente los encabezados de la biblioteca de C++ necesarios en una unidad de traducción, para no equivocarse sobre sus dependencias reales). Un encabezado estándar de C nunca incluye otro encabezado estándar. Un encabezado estándar solo declara o define las entidades descritas para él en este documento.  
  
 Cada función de la biblioteca se declara en un encabezado estándar. A diferencia de C estándar, el encabezado estándar nunca proporciona una macro de enmascaramiento con el mismo nombre que la función que enmascara la declaración de la función y consigue el mismo efecto. Para más información sobre macros de enmascaramiento, vea [Convenciones de la biblioteca de C++](../standard-library/cpp-library-conventions.md).  
  
 Todos los nombres distintos de `operator delete` y `operator new` en los encabezados de la biblioteca de C++ se definen en el espacio de nombres `std` o en un espacio de nombres anidado dentro del espacio de nombres `std`. Se hace referencia al nombre `cin`, por ejemplo, como `std::cin`. Pero tenga en cuenta que los nombres de macro no están sujetos a la calificación de espacio de nombres, por lo siempre se escribe `__STD_COMPLEX` sin un calificador de espacio de nombres.  
  
 En algunos entornos de traducción, incluir un encabezado de la biblioteca de C++ también puede elevar nombres externos declarados en el espacio de nombres `std` al espacio de nombres global, con declaraciones `using` individuales para cada uno de los nombres. De lo contrario, el encabezado *no* añade ningún nombre de biblioteca al espacio de nombres actual.  
  
 El estándar de C++ requiere que los encabezados del estándar de C declaren todos los nombres externos en el espacio de nombres `std`, y después los eleven al espacio de nombres global con declaraciones `using` individuales para cada uno de los nombres. Pero en algunos entornos de traducción los encabezados del estándar de C no incluyen ninguna declaración de espacio de nombres y declaran todos los nombres directamente en el espacio de nombres global. Por tanto, la manera más portátil de tratar con los espacios de nombres es seguir dos reglas:  
  
-   Para declarar sin dudas en el espacio de nombres `std` un nombre externo que tradicionalmente se declara en \<stdlib.h>, por ejemplo, incluya el encabezado \<cstdlib>. Tenga en cuenta que es posible que el nombre también se declare en el espacio de nombres global.  
  
-   Para declarar sin dudas en el espacio de nombres global un nombre externo declarado en \<stdlib.h>, incluya el encabezado \<stdlib.h> directamente. Tenga en cuenta que es posible que el nombre también se declare en el espacio de nombres `std`.  
  
 Por tanto, si quiere llamar a `std::abort` para que se produzca una finalización anómala, debe incluir \<cstdlib>. Si quiere llamar a `abort`, debe incluir \<stdlib.h>.  
  
 Como alternativa, puede escribir la declaración:  
  
```  
using namespace std;  
```  
  
 que añade todos los nombres de biblioteca al espacio de nombres actual. Si escribe esta declaración inmediatamente después de todas las directivas Include, se elevan los nombres al espacio de nombres global. Posteriormente, puede omitir las consideraciones de espacio de nombres en el resto de la unidad de traducción. También evita la mayoría de las diferencias entre entornos de traducción diferentes.  
  
 A menos que se indique específicamente lo contrario, no puede definir nombres en el espacio de nombres `std`, o en un espacio de nombres anidado dentro del espacio de nombres `std`, dentro del programa.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la biblioteca estándar de C++](../standard-library/cpp-standard-library-overview.md)   
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

