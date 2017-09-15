---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std.<hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
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
ms.openlocfilehash: 3941ccdd426e88e93591e3e759fcf9219f79d8ab
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  Este encabezado está obsoleto. La alternativa es la [clase unordered_set](../standard-library/unordered-set.md).  
  
 Define las clases de plantilla de contenedor hash_set y hash_multiset, así como sus plantillas auxiliares.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>Comentarios  
  
### <a name="operators"></a>Operadores  
  
|Hash_set (versión)|Hash_multiset (versión)|Descripción|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Comprueba si el objeto hash_set o hash_multiset situado a la izquierda del operador no es igual que el objeto hash_set o hash_multiset situado a la derecha.|  
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Comprueba si el objeto hash_set o hash_multiset situado a la izquierda del operador es igual que el objeto hash_set o hash_multiset situado a la derecha.|  
  
### <a name="specialized-template-functions"></a>Funciones de plantilla especializadas  
  
|Hash_set (versión)|Hash_multiset (versión)|Descripción|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|Intercambia los elementos de dos encabezados hash_sets o hash_multisets.|  
  
### <a name="classes"></a>Clases  
  
|||  
|-|-|  
|[hash_compare (Clase)](../standard-library/hash-compare-class.md)|Describe un objeto que se puede usar con cualquiera de los contenedores asociativos hash (hash_map, hash_multimap, hash_set o hash_multiset) como objeto de parámetro **Traits** predeterminado para ordenar y aplicar algoritmos hash a los elementos que contienen.|  
|[hash_set (Clase)](../standard-library/hash-set-class.md)|Se usa para el almacenamiento y la recuperación de datos rápida de una colección en la que los valores de los elementos contenidos son únicos y sirven como valores de clave.|  
|[hash_multiset (Clase)](../standard-library/hash-multiset-class.md)|Se usa para el almacenamiento y la recuperación de datos rápida de una colección en la que los valores de los elementos contenidos son únicos y sirven como valores de clave.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)   
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)



