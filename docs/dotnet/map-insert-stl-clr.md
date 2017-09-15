---
title: "map::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert (miembro) [STL/CLR]"
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Agrega elementos.  
  
## Sintaxis  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Parámetros  
 first  
 Inicio del intervalo que se va a insertar.  
  
 last  
 Final del intervalo que se va a insertar.  
  
 right  
 Enumeración que se va a insertar.  
  
 val  
 Valor de clave que se va a insertar.  
  
 donde  
 Donde en el contenedor insertar \(sugerencia sólo\).  
  
## Comentarios  
 Cada una de las funciones miembro inserta una secuencia especificada por los operandos restantes.  
  
 La primera función miembro se esfuerza para insertar un elemento con el valor `val`, y devuelve un par de valores `X`.  Si `X.second` es true, `X.first` designa el elemento insertado recientemente; si no `X.first` designa un elemento con equivalente solicitando que ya existe y no se insertará ningún nuevo elemento.  Se utiliza para insertar un solo elemento.  
  
 La segunda función miembro inserta un elemento con el valor `val`, mediante `where` como sugerencia \(mejorar rendimiento\), y devuelve un iterador que señala el elemento insertado recientemente.  Se utiliza para insertar un solo elemento que podría estar junto a un elemento que sabe.  
  
 La tercera función miembro inserta la secuencia `[``first``,` `last``)`.  Se utiliza para insertar cero o más elementos copiado de otra secuencia.  
  
 La cuarta función miembro inserta la secuencia indicada por `right`.  Se utiliza para insertar una secuencia descrita por un enumerador.  
  
 Cada inserción de elementos lleva tiempo proporcional al logaritmo del número de elementos de la secuencia controlada.  Inserción puede aparecer en el tiempo constante amortizado, sin embargo, dada una sugerencia que señale un elemento adyacente al punto de inserción.  
  
## Ejemplo  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[un 1\] \[b 2\] \[c 3\]**  
**inserción \(L'x \[24\]\) \= \[\[X 24\] True\]**  
**inserción \(L'b \[2\]\) \= \[\[B 2\] False\]**  
 **\[un 1\] \[b 2\] \[c 3\] \[x 24\]**  
**insert\(begin\(\), L'y \[25\]\) \= \[y 25\]**  
 **\[un 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**  
 **\[un 1\] \[b 2\] \[c 3\] \[x 24\]**  
 **\[un 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**   
## Requisitos  
 cliext \<de**Encabezado:** \/asignado\>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [map](../dotnet/map-stl-clr.md)