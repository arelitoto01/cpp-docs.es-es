---
title: "Punteros con base (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__based"
  - "__based_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__based (palabra clave) [C++]"
  - "punteros con base"
  - "punteros, con base"
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Punteros con base (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de Microsoft**  
  
 La palabra clave `__based` permite declarar punteros basados en punteros \(punteros que son desplazamientos de punteros existentes\).  
  
## Sintaxis  
  
```  
  
type __based( base ) declarator   
```  
  
## Comentarios  
 Los punteros basados en direcciones de puntero son la única forma de la palabra clave `__based` válida en compilaciones de 32 y 64 bits.  Para el compilador de 32 bits de Microsoft C\/C\+\+, un puntero basado es un desplazamiento de 32 bits desde una base de puntero de 32 bits.  Se aplica una restricción similar a los entornos de 64 bits, donde un puntero basado es un desplazamiento de 64 bits de la base de 64 bits.  
  
 Uno de los usos de los punteros basados en punteros son los identificadores persistentes que contienen punteros.  Una lista vinculada formada por punteros basados en un puntero se puede guardar en el disco y recargar en otro lugar de la memoria; los punteros seguirán siendo válidos.  Por ejemplo:  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Al puntero `vpBuffer` se le asigna la dirección de memoria asignada posteriormente en el programa.  La lista vinculada se reubica en relación con el valor de `vpBuffer`.  
  
> [!NOTE]
>  La persistencia de identificadores que contienen punteros también se consigue mediante [archivos asignados a memoria](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Cuando se desreferencia un puntero basado, la base se debe especificar explícitamente o se debe conocer implícitamente con la declaración.  
  
 Por compatibilidad con versiones anteriores, **\_based** es un sinónimo de `__based`.  
  
## Ejemplo  
 El código siguiente muestra cómo se cambia un puntero basado mediante el cambio de su base.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
  **1**  
**2**  
**10**  
**11**   
## Vea también  
 [Palabras clave de C\+\+](../cpp/keywords-cpp.md)   
 [alloc\_text](../preprocessor/alloc-text.md)