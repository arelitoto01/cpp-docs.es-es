---
title: "Error irrecuperable C1055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Error irrecuperable C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

límite del compilador: no hay claves  
  
 El archivo de código fuente contiene demasiados símbolos.  El compilador se ha quedado sin claves hash para la tabla de símbolos.  
  
### Se corrige mediante algunas de las siguientes posibles soluciones  
  
1.  Divida el archivo de código fuente en archivos más pequeños.  
  
2.  Elimine los archivos de encabezado innecesarios.  
  
3.  Reutilice las variables temporales y globales en vez de crear variables nuevas.