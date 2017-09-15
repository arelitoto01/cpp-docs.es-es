---
title: "hash_multiset::difference_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::difference_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "difference_type (miembro) [STL/CLR]"
ms.assetid: 31e492b1-e980-4799-bab2-0dd2864428c9
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::difference_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Los tipos de una distancia firmados entre dos elementos.  
  
## Sintaxis  
  
```  
typedef int difference_type;  
```  
  
## Comentarios  
 El tipo describe un recuento de elementos posiblemente negativo.  
  
## Ejemplo  
  
```  
// cliext_hash_multiset_difference_type.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Myhash_multiset::difference_type diff = 0;   
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (Myhash_multiset::iterator it = c1.end(); it != c1.begin(); --it)   
        --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**end\(\)\- inicio \(\) \= 3**  
**begin\(\)\- final \(\) \= \-3**   
## Requisitos  
 cliext \<\/hash\_set de**Encabezado:** \>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::size\_type](../dotnet/hash-multiset-size-type-stl-clr.md)