---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<hash_map>
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a1c256df1182c00c1b6045923ba9975f02c9bfa2
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Este encabezado está obsoleto. La alternativa es [<unordered_map>](../standard-library/unordered-map.md).  
  
 Define las clases de plantilla de contenedor hash_map y hash_multimap y sus plantillas auxiliares.  
  
 En Visual C++ .NET 2003, los miembros de los archivos de encabezado <hash_map> y <hash_set> ya no están en el espacio de nombres std, sino que se han movido al espacio de nombres stdext. Vea [stdext Namespace](../standard-library/stdext-namespace.md) (El espacio de nombres stdext) para obtener más información.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Operadores  
  
|Versión de hash_map|Versión de hash_multimap|Descripción|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#op_neq)|`operator!= (hash_multimap)`|Comprueba si el objeto hash_map o hash_multimap del lado izquierdo del operador no es igual al objeto hash_map o hash_multimap del lado derecho.|  
|[operator== (hash_map)](../standard-library/hash-map-operators.md#op_eq_eq)|`operator== (hash_multimap)`|Comprueba si el objeto hash_map o hash_multimap del lado izquierdo del operador es igual al objeto hash_map o hash_multimap del lado derecho.|  
  
### <a name="specialized-template-functions"></a>Funciones de plantilla especializadas  
  
|Versión de hash_map|Versión de hash_multimap|Descripción|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#swap)|Intercambia los elementos de dos encabezados hash_map o hash_multimap.|  
  
### <a name="classes"></a>Clases  
  
|||  
|-|-|  
|[hash_compare (Clase)](../standard-library/hash-compare-class.md)|Describe un objeto que se puede usar con cualquiera de los contenedores asociativos hash (hash_map, hash_multimap, hash_set o hash_multiset) como objeto de parámetro **Traits** predeterminado para ordenar y aplicar algoritmos hash a los elementos que contienen.|  
|[value_compare (Clase)](../standard-library/value-compare-class.md)|Proporciona un objeto de función que puede comparar los elementos de hash_map al comparar los valores de sus claves para determinar su orden relativo en hash_map.|  
|[hash_map (Clase)](../standard-library/hash-map-class.md)|Se usa para el almacenamiento y la recuperación rápida de datos de una colección en la que cada elemento es un par que tiene una clave de ordenación cuyo valor es único y un valor de datos asociado.|  
|[hash_multimap (Clase)](../standard-library/hash-multimap-class.md)|Se usa para el almacenamiento y la recuperación rápida de datos de una colección en la que cada elemento es un par que tiene una clave de ordenación cuyo valor no necesita ser único y un valor de datos asociado.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<hash_map>  
  
 **Espacio de nombres:** stdext  
  
## <a name="see-also"></a>Vea también  
 [Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)   
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)



