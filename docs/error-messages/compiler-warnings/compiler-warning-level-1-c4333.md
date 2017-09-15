---
title: "Advertencia del compilador (nivel 1) C4333 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4333"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4333"
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Advertencia del compilador (nivel 1) C4333
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operador': desplazamiento a la derecha muy grande; se perderán los datos.  
  
 Una operación de desplazamiento a la derecha ha sido demasiado grande.  Todos los bits significativos son desplazados y el resultado siempre será cero.  
  
## Ejemplo  
 El ejemplo siguiente genera el error C4333.  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```