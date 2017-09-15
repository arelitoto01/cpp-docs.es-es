---
title: "Error del compilador C2599 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2599"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2599"
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Error del compilador C2599
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum' : no se permite la declaración adelantada de un tipo Enum  
  
 El compilador ya no admite la declaración adelantada de una enumeración administrada.  
  
 No se permite la declaración adelantada de un tipo enum mediante [\/Za](../../build/reference/za-ze-disable-language-extensions.md).  
  
 El código siguiente genera el error C2599:  
  
```  
// C2599.cpp  
// compile with: /clr /c  
enum class Status;   // C2599  
  
enum class Status2 { stop2, hold2, go2};   
  
ref struct MyStruct {  
   // Delete the following line to resolve.  
   Status m_status;  
  
   Status2 m_status2;   // OK  
};  
  
enum class Status { stop, hold, go };  
```