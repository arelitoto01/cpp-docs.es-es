---
title: "multiset::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare (miembro) [STL/CLR]"
ms.assetid: 962e5a3b-5841-4b44-8801-5f5349e95c8f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# multiset::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

El delegado de ordenación por dos valores de elemento.  
  
## Sintaxis  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## Comentarios  
 El tipo es un sinónimo del delegado que determina el orden de sus argumentos de valor.  
  
## Ejemplo  
  
```  
// cliext_multiset_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **comparar \(L'a, L'a\) \= False**  
**comparar \(L'a, L'b\) \= True**  
**comparar \(L'b, L'a\) \= False**   
## Requisitos  
 cliext \<o conjunto de**Encabezado:** \>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)   
 [multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)   
 [multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)