---
title: Iteradores | Microsoft Docs
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
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: ffeaf473155d0a24bd0e1b14c4191d276bed5190
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="iterators"></a>Iteradores
Un iterador es un objeto que puede iterar sobre los elementos de un contenedor de la biblioteca estándar de C++ y proporcionar acceso a los elementos individuales. Todos los contenedores de la biblioteca estándar de C++ proporcionan los iteradores para que los algoritmos puedan tener acceso a sus elementos de manera estándar sin tener que preocuparse por el tipo de contenedor en el que están almacenados los elementos.  
  
 Puede usar iteradores de forma explícita con funciones miembro y globales, como begin() y end() y operadores como ++ y -- para desplazarse hacia delante o hacia atrás. También puede usar iteradores de forma implícita con un bucle de tipo range-for o (en algunos tipos de iterador) el operador de subíndice [].  
  
 En la biblioteca estándar de C++, el principio de una secuencia o un intervalo es el primer elemento. El final de una secuencia o un intervalo siempre se define como un elemento posterior al último elemento. Las funciones globales begin y end devuelven iteradores a un contenedor especificado. El típico bucle de iterador explícito de todos los elementos de un contenedor tiene este aspecto:  
  
```  
 
vector<int> vec{ 0,1,2,3,4 };  
for (auto it = begin(vec);

it != end(vec);

it++)  
{  // Access element using dereference operator
    cout <<*it <<" ";  
}  
```  
  
 Se puede lograr lo mismo de forma más sencilla con un bucle de tipo range-for:  
  
```  
for (auto num : vec)  
 {  // no deference operator
    cout <<num <<" ";  
 }  
```  
  
 Existen cinco categorías de iteradores. Ordenadas de menor a mayor potencia, las categorías son:  
  
- **Salida**. Un iterador de salida de `X` puede iterar hacia delante sobre una secuencia mediante el operador ++ y puede escribir un elemento una sola vez, mediante el operador *.  
  
- **Entrada**. Un iterador de entrada de `X` puede iterar hacia delante sobre una secuencia mediante el operador ++ y puede leer un elemento todas las veces que quiera, mediante el operador *. Puede comparar los iteradores de entrada mediante los operadores ++ y !=. Tras incrementar cualquier copia de un iterador de entrada, ninguna de las demás copias se puede comparar, desreferenciar o aumentar posteriormente de manera segura.  
  
- **Hacia delante**. Un iterador de entrada de `X` puede iterar hacia delante sobre una secuencia mediante el operador ++ y puede leer cualquier elemento o escribir en elementos que no sean tipo const todas las veces que quiera, mediante el operador *. Puede tener acceso a los miembros del elemento mediante el operador -> y comparar los iteradores hacia delante mediante los operadores == y! =. También puede realizar varias copias de un iterador hacia delante, cada una de las cuales puede desreferenciarse e incrementarse de forma independiente. Un iterador hacia delante que se inicializa sin hacer referencia a ningún contenedor se denomina iterador hacia delante nulo. Los iteradores hacia delante nulos siempre se comparan igual.  
  
-   Bidireccional. Un iterador bidireccional `X` puede sustituir a un iterador hacia delante. Sin embargo, también puede reducir un iterador bidireccional, como en --`X`, `X`-- o (`V` = *`X`--). Puede acceder a los miembros de elemento y comparar los iteradores bidireccionales de la misma manera que los iteradores hacia delante.  
  
- **Acceso aleatorio**. Un iterador de acceso aleatorio `X` puede sustituir a un iterador bidireccional. Con un iterador de acceso aleatorio, puede usar el operador de subíndice [] para acceder a los elementos. Puede usar los operadores +, -,+= y -= para avanzar o retroceder un número especificado de elementos y para calcular la distancia entre los iteradores. Puede comparar los iteradores bidireccionales ==, !=, \<, >, \<= y >=.  
  
 Todos los iteradores pueden asignarse o copiarse. Se supone que son objetos ligeros y a menudo se pasan y se devuelven por valor, no por referencia. Tenga en cuenta que ninguna de las operaciones descritas anteriormente puede iniciar una excepción cuando se realizan en un iterador válido.  
  
 La jerarquía de las categorías de iterador se puede resumir mostrando tres secuencias. Para el acceso de solo escritura a una secuencia, puede usar cualquiera de los siguientes:  
  
```  
output iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 La flecha derecha significa "puede reemplazarse por". Cualquier algoritmo que llama a un iterador de salida debería funcionar correctamente con un iterador hacia delante, por ejemplo, pero *no* al revés.  
  
 Para el acceso de solo lectura a una secuencia, puede usar cualquiera de los siguientes:  
  
```  
input iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 En este caso, el iterador de entrada es la categoría más débil.  
  
 Por último, para el acceso de lectura y escritura a una secuencia, puede usar cualquiera de los siguientes:  
  
```  
forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 Un puntero de objeto siempre puede servir como iterador de acceso aleatorio, por lo que puede usarse como cualquier categoría de iterador si admite el correspondiente acceso de lectura y escritura a la secuencia que designa.  
  
 Un iterador `Iterator` distinto de un puntero de objeto también debe definir los tipos de miembro que requiere la especialización `iterator_traits<Iterator>`. Tenga en cuenta que estos requisitos pueden cumplirse si se deriva `Iterator` de la clase base pública [iterator](../standard-library/iterator-struct.md).  
  
 Es importante comprender las promesas y las limitaciones de cada categoría de iterador para ver cómo los contenedores y los algoritmos usan los iteradores en la biblioteca estándar de C++.  
  
> [!NOTE]
>  Puede evitar el uso de iteradores de forma explícita mediante bucles de tipo range-for. Para obtener más información, vea [Loops (Modern C++)](http://msdn.microsoft.com/en-us/b1b2779c-750e-4576-a514-a84178eae9da) (Bucles (C++ moderno)).  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ahora ofrece iteradores comprobados e iteradores de depuración para asegurarse de que no sobrescribe los límites del contenedor. Para obtener más información, vea [Iteradores comprobados](../standard-library/checked-iterators.md) y [Compatibilidad de los iteradores de depuración](../standard-library/debug-iterator-support.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)   
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

