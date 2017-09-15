---
title: "vtordisp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.vtordisp"
  - "vtordisp_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pragma (directivas), vtordisp"
  - "vtordisp (pragma)"
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# vtordisp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de C\+\+**  
  
 Controla la adición del miembro oculto de desplazamiento de construcción\/destrucción de vtordisp.  
  
## Sintaxis  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### Parámetros  
 `push`  
 Inserta el valor actual de vtordisp en la pila interna del compilador y establece el nuevo valor de vtordisp en `n`.  Si `n` no se especifica, el valor actual de vtordisp no cambia.  
  
 `pop`  
 Quita el registro superior de la pila interna del compilador y restaura el valor vtordisp al valor quitado.  
  
 `n`  
 Especifica el nuevo valor de vtordisp.  Los valores posibles son 0, 1 o 2, que se corresponden con las opciones del compilador \/vd0, \/vd1 y \/vd2.  Para obtener más información, vea [\/vd \(Deshabilitar desplazamientos de constructores\)](../build/reference/vd-disable-construction-displacements.md).  
  
 `on`  
 Equivalente a `#pragma vtordisp(1)`.  
  
 `off`  
 Equivalente a `#pragma vtordisp(0)`.  
  
## Comentarios  
 La directiva pragma de `vtordisp` solo es aplicable al código que usa bases virtuales.  Si una clase derivada reemplaza una función virtual que hereda de una clase base virtual y si un constructor o destructor para la clase derivada llama a esa función con un puntero a la clase base virtual, el compilador puede incluir campos ocultos adicionales de `vtordisp` en clases con bases virtuales.  
  
 La directiva pragma de `vtordisp` afecta al diseño de las clases que la cumplen.  Las opciones \/vd0, \/vd1 y \/vd2 especifican el mismo comportamiento para módulos completos.  Al especificar `0` o `off`, se suprimen los miembros ocultos de `vtordisp`.  Desactive `vtordisp` solamente si no existe ninguna posibilidad de que los constructores y destructores de la clase llamen a funciones virtuales en el objeto al que señala el puntero `this`.  
  
 Al especificar `1` u `on`, que es el valor predeterminado, se habilitan los miembros ocultos de `vtordisp` donde se necesitan.  
  
 Al especificar `2`, se habilitan los miembros ocultos de `vtordisp` para todas las bases virtuales con funciones virtuales. `vtordisp(2)` podría ser necesario para garantizar el funcionamiento correcto de `dynamic_cast` en un objeto parcialmente construido.  Para obtener más información, vea [Advertencia del compilador \(nivel 1\) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
 `#pragma vtordisp()`, sin argumentos, restaura el valor de vtordisp a la configuración inicial.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **Específicos de C\+\+: END**  
  
## Vea también  
 [Directives pragma y la palabra clave \_\_pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)