---
title: "Advertencia del compilador (nivel 1) C4348 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4348"
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Advertencia del compilador (nivel 1) C4348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'tipo' : nueva definición de parámetro predeterminado : parámetro número  
  
 Se ha vuelto a definir un parámetro de plantilla.  
  
 El código siguiente genera el error C4348:  
  
```  
// C4348.cpp  
// compile with: /LD /W1  
template <class T=int> struct A;   // forward declaration  
  
template <class T=int> struct A { };   
// C4348, redefinition of default parameter  
// try the following line instead  
// template <class T> struct A { };  
```