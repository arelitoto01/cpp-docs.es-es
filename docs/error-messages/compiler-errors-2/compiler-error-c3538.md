---
title: "Error del compilador C3538 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3538"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3538"
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Error del compilador C3538
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

en una lista de declaradores, 'auto' siempre debe deducirse como el mismo tipo  
  
 No todas las variables declaradas en una lista de declaraciones se resuelven en el mismo tipo.  
  
### Para corregir este error  
  
1.  Asegúrese de que todas las declaraciones de `auto` de la lista se deducen en el mismo tipo.  
  
## Ejemplo  
 Las instrucciones siguientes producen C3538.  Cada instrucción declara múltiples variables, pero no todos los usos de la palabra clave `auto` se deducen en el mismo tipo.  
  
```  
// C3538.cpp  
// Compile with /Zc:auto  
// C3538 expected  
int main()  
{  
// Variable x1 is a pointer to char, but y1 is a double.  
   auto * x1 = "a", y1 = 3.14;    
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.  
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;   
// Variable x2 is an int, but y2 is a double and z is a char.  
   auto x2(1), y2(0.0), z = 'a';   
// Variable a is a pointer to int, but b is a pointer to double.  
   auto *a = new auto(1), *b = new auto(2.0);   
   return 0;  
}  
```  
  
## Vea también  
 [auto \(Palabra clave\)](../../cpp/auto-keyword.md)