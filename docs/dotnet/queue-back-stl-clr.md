---
title: "queue::back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back (miembro) [STL/CLR]"
ms.assetid: 983a5c0f-0a2f-475f-932b-e7dec9eaffbb
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# queue::back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tiene acceso al último elemento.  
  
## Sintaxis  
  
```  
reference back();  
```  
  
## Comentarios  
 La función miembro devuelve una referencia al último elemento de la secuencia controlada, que no puede estar vacía.  Se utiliza para tener acceso al último elemento, cuando lo conoce existe.  
  
## Ejemplo  
  
```  
// cliext_queue_back.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**back\(\) \= c**  
 **una b x**   
## Requisitos  
 cliext \<\/cola de**Encabezado:** \>  
  
 cliext de**Espacio de nombres:**  
  
## Vea también  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::back\_item](../dotnet/queue-back-item-stl-clr.md)   
 [queue::front](../dotnet/queue-front-stl-clr.md)   
 [queue::front\_item](../dotnet/queue-front-item-stl-clr.md)