---
title: "Error del compilador C2806 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2806"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2806"
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Error del compilador C2806
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operador operador' tiene demasiados parámetros formales  
  
 Un operador sobrecargado tiene demasiados parámetros.  
  
 El código siguiente genera el error C2806:  
  
```  
// C2806.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( int, int );   // C2806 more than 1 parameter  
   X operator++ ( int );   // OK  
} ;  
```