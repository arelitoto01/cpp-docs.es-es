---
title: "priority_queue::priority_queue (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue (miembro) [STL/CLR]"
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# priority_queue::priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construye un objeto de adaptador de contenedor.  
  
## Sintaxis  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### Parámetros  
 continuado  
 Contenedor para copiar.  
  
 first  
 Inicio del intervalo que se va a insertar.  
  
 last  
 Final del intervalo que se va a insertar.  
  
 pred  
 Ordenar el predicado de la secuencia controlada.  
  
 right  
 Objeto o intervalo para insertar.  
  
## Comentarios  
 El constructor:  
  
 `priority_queue();`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación predeterminado.  Se utiliza para especificar una secuencia controlada inicial vacía, con el predicado de ordenación predeterminado.  
  
 El constructor:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 crea un contenedor ajustado que es una copia de `right.get_container()`, con el predicado de ordenación `right.value_comp()`.  Se utiliza para especificar una secuencia controlada inicial que es una copia de la secuencia controlada por el objeto de cola `right`, con el mismo predicado de ordenación.  
  
 El constructor:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 crea un contenedor ajustado que es una copia de `right->get_container()`, con el predicado de ordenación `right->value_comp()`.  Se utiliza para especificar una secuencia controlada inicial que es una copia de la secuencia controlada por el objeto de cola `*right`, con el mismo predicado de ordenación.  
  
 El constructor:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación `pred`.  Se utiliza para especificar una secuencia controlada inicial vacía, con el predicado de ordenación especificado.  
  
 El constructor:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación `pred`, después inserta todos los elementos de uso de `cont` Que consiste en especificar una secuencia controlada inicial de un contenedor existente, con el predicado de ordenación especificado.  
  
 El constructor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last);`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación predeterminado, se inserta la secuencia `[``first``,` `last``)`.  Se utiliza para especificar una secuencia controlada inicial de un eqeuence especificado, con el predicado de ordenación especificado.  
  
 El constructor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred);`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación `pred`, se inserta la secuencia `[``first``,` `last``)`.  Se utiliza para especificar una secuencia controlada inicial de un seqeuence especificado, con el predicado de ordenación especificado.  
  
 El constructor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred, container_type% cont);`  
  
 crea un contenedor ajustado vacío, con el predicado de ordenación `pred`, después inserta todos los elementos de `cont` más la secuencia `[``first``,` `last``)`.  Se utiliza para especificar una secuencia controlada inicial de un contenedor existente y un seqeuence especificado, con el predicado de ordenación especificado.  
  
## Ejemplo  
  
```  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **c a b**  
**size\(\) \= 0**  
 **b de C\+\+.**  
 **b de C\+\+.**  
 **c a b**  
 **b de C\+\+.**  
 **a b c de la b c**  
 **c a b**  
 **c a b**  
 **b de C\+\+.**   
## Requisitos  
 cliext \<\/cola de**Encabezado:** \>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)