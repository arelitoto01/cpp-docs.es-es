---
title: "Error del compilador C2777 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2777"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2777"
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Error del compilador C2777
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sólo se puede especificar un método 'put' por cada propiedad  
  
 Un modificador declspec de [propiedad](../../cpp/property-cpp.md) tenía más de una propiedad `put`.  
  
 El código siguiente genera el error C2777:  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```