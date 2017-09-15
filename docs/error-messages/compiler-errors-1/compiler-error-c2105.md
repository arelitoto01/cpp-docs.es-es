---
title: "Error del compilador C2105 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2105"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2105"
ms.assetid: 19b7f7bc-a9da-4d23-8193-005b6d09274f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Error del compilador C2105
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operador' necesita el valor L  
  
 El operador debe tener como operando un valor L \(valor a la izquierda\).  
  
 El código siguiente genera el error C2105:  
  
```  
// C2105.cpp  
int main() {  
   unsigned char * p1 = 0;  
   unsigned int * p2 = (unsigned int *)p1;  
   p2++;  
  
   unsigned int * p = 0;  
   p++;   // ok  
  
   p2 = (unsigned int *)p1;  
   ((unsigned int *)p1)++;   // C2105  
}  
```  
  
 El código siguiente genera el error C2105:  
  
```  
// C2105b.cpp  
int main() {  
   int a[10] = {0};  
   int b[10] = {0};  
   ++(a , b);   // C2105  
  
   // OK  
   ++(a[0] , b[0]);  
   ++a[0];  
}  
```