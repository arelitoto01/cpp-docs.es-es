---
title: "Error del compilador C2913 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2913"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2913"
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Error del compilador C2913
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

especialización explícita; 'declaración' no es una especialización de una plantilla de clase  
  
 No se puede especializar una clase que no es de plantilla.  
  
 El código siguiente genera el error C2913:  
  
```  
// C2913.cpp  
// compile with: /c  
class X{};  
template <class T> class Y{};  
  
template<> class X<int> {};   // C2913  
template<> class Y<int> {};  
```