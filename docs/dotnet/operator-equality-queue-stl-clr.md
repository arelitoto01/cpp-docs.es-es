---
title: "operator== (queue) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator== (miembro) [STL/CLR]"
ms.assetid: ad183c61-a24a-4851-aac7-2a47a1371ec2
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator== (queue) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comparación igual de la cola.  
  
## Sintaxis  
  
```  
template<typename Value,  
    typename Container>  
    bool operator==(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### Parámetros  
 left  
 Contenedor izquierdo a comparar.  
  
 right  
 Contenedor derecho a comparar.  
  
## Comentarios  
 La función de operador devuelve true solo si las secuencias controladas por `left` y `right` tienen la misma longitud y, para cada posición `i`, `left``[i] ==` `right``[i]`.  Se utiliza para probar si `left` se le igual que `right` cuando las dos colas son elemento comparado al lado de elemento.  
  
## Ejemplo  
  
```  
// cliext_queue_operator_eq.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **una d b**  
**\=\= \[de una b c\] \[una b c\] es True**  
**\=\= \[de una b c\] \[una d b\] es False**   
## Requisitos  
 cliext \<\/cola de**Encabezado:** \>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [queue](../dotnet/queue-stl-clr.md)   
 [operator\!\= \(queue\)](../dotnet/operator-inequality-queue-stl-clr.md)   
 [operator\< \(queue\)](../dotnet/operator-less-than-queue-stl-clr.md)   
 [operator\>\= \(queue\)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [operator\> \(queue\)](../dotnet/operator-greater-than-queue-stl-clr.md)   
 [operator\<\= \(queue\)](../dotnet/operator-less-or-equal-queue-stl-clr.md)