---
title: "Error del compilador C2273 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2273"
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Error del compilador C2273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“tipo”: no es válido como lado derecho '\-\>' de operador  
  
 Hay un tipo como operando derecho de un operador `->`.  
  
 Este error puede producirse al intentar el acceso a una conversión de tipos definida por el usuario.  Utilice la palabra clave `operator` entre \-\> y `type`.  
  
 El código siguiente genera el error C2273:  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```