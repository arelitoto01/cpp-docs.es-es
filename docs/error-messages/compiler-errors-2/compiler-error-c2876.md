---
title: "Error del compilador C2876 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2876"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2876"
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Error del compilador C2876
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'clase::símbolo': no se puede obtener acceso a todas las sobrecargas  
  
 Todas las formas sobrecargadas de una función en una clase base deben ser accesibles para la clase derivada.  
  
 El código siguiente genera el error C2876:  
  
```  
// C2876.cpp  
// compile with: /c  
class A {  
public:     
   double a(double);  
private:  
   int a(int);  
};  
  
class B : public A {  
   using A::a;   // C2876 one overload is private in base class  
};  
```