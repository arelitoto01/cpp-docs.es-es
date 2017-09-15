---
title: Flujos de salida | Microsoft Docs
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
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 34a37749690fc0e42ba855640d0936fd8a25842f
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="output-streams"></a>Flujos de salida
Un objeto de flujo de salida es un destino de bytes. Las tres clases de flujo de salida más importantes son `ostream`, `ofstream` y `ostringstream`.  
  
 La clase `ostream`, mediante la clase derivada `basic_ostream`, admite los objetos de secuencia predefinida:  
  
-   `cout` salida estándar  
  
-   `cerr` error estándar con almacenamiento en búfer limitado  
  
-   `clog` similar a `cerr` pero con almacenamiento en búfer completo  
  
 Los objetos rara vez se construyen desde `ostream`; normalmente se usan los objetos predefinidos. En algunos casos, puede volver a asignar objetos predefinidos después del inicio del programa. La clase `ostream`, que puede configurarse para la operación de almacenamiento o no almacenamiento en búfer, se adapta mejor a la salida del modo de texto secuencial. Todas las funciones de la clase base, `ios`, se incluyen en `ostream`. Si construye un objeto de clase `ostream`, debe especificar un objeto `streambuf` al constructor.  
  
 La clase `ofstream` admite la salida de archivo de disco. Si necesita un disco de solo salida, construya un objeto de clase `ofstream`. Puede especificar si los objetos `ofstream` aceptan datos de modo de texto o binarios al construir el objeto `ofstream` o cuando llaman a la función miembro `open` del objeto. Muchas opciones de formato y funciones de miembro se aplican a los objetos `ofstream`, y todas las funciones de las clases base `ios` y `ostream` se incluyen.  
  
 Si especifica un nombre de archivo en el constructor, ese archivo se abre automáticamente cuando el objeto se construye. De otro modo, puede usar la función miembro `open` después de invocar el constructor predeterminado.  
  
 Como la función en tiempo de ejecución `sprintf_s`, la clase `ostringstream` admite la salida a las cadenas en memoria. Para crear una cadena en memoria con el formato de secuencia de E/S, construya un objeto de clase `ostringstream`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Construir objetos de flujo de salida](../standard-library/constructing-output-stream-objects.md)  
  
 [Usar operadores de inserción y controlar el formato](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Funciones de miembro de flujo de archivos de salida](../standard-library/output-file-stream-member-functions.md)  
  
 [Efectos del almacenamiento en búfer](../standard-library/effects-of-buffering.md)  
  
 [Archivos de salida binarios](../standard-library/binary-output-files.md)  
  
 [Sobrecargar el << operador para las clases propias](../standard-library/overloading-the-output-operator-for-your-own-classes.md)  
  
 [Escribir manipuladores propios sin argumentos](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## <a name="see-also"></a>Vea también 
 [ofstream](../standard-library/basic-ofstream-class.md)   
 [ostringstream](../standard-library/basic-ostringstream-class.md)   
 [Programación con iostream](../standard-library/iostream-programming.md)

