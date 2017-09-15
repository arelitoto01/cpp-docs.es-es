---
title: "Advertencia del compilador (nivel 4) C4610 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4610"
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Advertencia del compilador (nivel 4) C4610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

No se pueden crear nunca instancias de objeto 'clase'; se requiere un constructor definido por el usuario  
  
 La clase no tiene constructores definidos por el usuario o predeterminados.  No se realiza ninguna creación de instancia.  El código siguiente genera el error C4610:  
  
```  
// C4610.cpp  
// compile with: /W4  
struct A {  
   int &j;  
  
   A& A::operator=( const A& );  
};   // C4610  
  
/* use this structure definition to resolve the warning  
struct B {  
   int &k;  
  
   B(int i = 0) : k(i) {  
   }  
  
   B& B::operator=( const B& );  
} b;  
*/  
  
int main() {  
}  
```