---
title: "Advertencia del compilador (nivel 1) C4216 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4216"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4216"
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Advertencia del compilador (nivel 1) C4216
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

se ha utilizado una extensión no estándar: float long  
  
 Las extensiones de Microsoft predeterminadas \(\/Ze\) tratan **float long** como **double**.  La compatibilidad con ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) no lo hace.  Utilice **double** para mantener la compatibilidad.  El código siguiente genera el error C4216:  
  
```  
// C4216.cpp  
// compile with: /W1  
float long a;   // C4216  
  
// use the line below to resolve the warning  
// double a;  
  
int main() {  
}  
```