---
title: "multimap::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase (miembro) [STL/CLR]"
ms.assetid: 94623cfc-4464-44a6-afd4-90a36828ac2b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quita los elementos en las posiciones especificadas.  
  
## Sintaxis  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### Parámetros  
 first  
 Inicio del intervalo que se va a borrar.  
  
 clave  
 Valor de clave que se va a borrar.  
  
 last  
 Final del intervalo que se va a borrar.  
  
 donde  
 Elemento que se va a borrar.  
  
## Comentarios  
 La primera función miembro quita el elemento de la secuencia controlada designada por a `where`, y devuelve un iterador que señala el primer elemento que permanece más allá del elemento quitado, o [multimap::end](../dotnet/multimap-end-stl-clr.md)`()` si no existe ese elemento.  Se utiliza para quitar un solo elemento.  
  
 La segunda función miembro quita elementos de la secuencia controlada en el intervalo `[``first``,` `last``)`, y devuelve un iterador que señala el primer elemento que permanece más allá de cualquier elemento quitado, o `end()` si no existe ningún elemento.  Se utiliza para quitar elementos cero o más contiguo.  
  
 La tercera función miembro quita cualquier elemento de la secuencia controlada cuya clave tiene equivalente de ordenación a `key`, y devuelve el número de elementos eliminados.  Se utiliza para quitar y para contar todos los elementos que coinciden con una clave especificada.  
  
 Cada borradura de elemento lleva tiempo proporcional al logaritmo del número de elementos de la secuencia controlada.  
  
## Ejemplo  
  
```  
// cliext_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    cliext::multimap<wchar_t, int> c1;   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **\[un 1\] \[b 2\] \[c 3\]**  
**erase\(begin\(\)\) \= \[b 2\]**  
 **\[b 2\] \[c 3\] \[d 4\] \[e 5\]**  
**erase\(begin\(\), end\(\)\-1\) \= \[e 5\]**  
**size\(\) \= 1**  
**desactivada \(L'x\) \= 0**  
**desactivada \(L'e\) \= 1**   
## Requisitos  
 cliext \<de**Encabezado:** \/asignado\>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::clear](../dotnet/multimap-clear-stl-clr.md)