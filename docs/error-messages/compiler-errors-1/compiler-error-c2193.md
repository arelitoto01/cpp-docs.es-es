---
title: "Error del compilador C2193 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2193"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2193"
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Error del compilador C2193
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificador' : ya está en un segmento  
  
 Se ha colocado una función en dos segmentos diferentes usando las pragmas `alloc_text` y `code_seg`.  
  
 El código siguiente genera el error C2193:  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```