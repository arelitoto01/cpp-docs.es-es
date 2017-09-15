---
title: "Calcular valores necesarios | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "funciones auxiliares, calcular valores necesarios"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Calcular valores necesarios
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hay dos partes esenciales de información que tiene que calcular la rutina auxiliar de carga retrasada.  Hay dos funciones inline en delayhlp.cpp que se utilizan para calcular esta información.  
  
-   La primera calcula el índice de la importación actual en las tres diferentes tablas \(tabla de direcciones de importación \(IAT\), tabla de direcciones de importación enlazadas \(BIAT\) y tabla de direcciones de importación no enlazadas \(UIAT\)\).  
  
-   La segunda cuenta el número de importaciones de una IAT válida.  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## Vea también  
 [Understanding the Helper Function](http://msdn.microsoft.com/es-es/6279c12c-d908-4967-b0b3-cabfc3e91d3d)