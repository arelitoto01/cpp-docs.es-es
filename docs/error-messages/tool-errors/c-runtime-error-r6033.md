---
title: "R6033 del Error en tiempo de ejecuci&#243;n de C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6033 DEL"
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Error en tiempo de ejecuci&#243;n de C R6033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Intento de utilizar el código MSIL desde el ensamblado durante la inicialización del código nativo.Esto indica un error en la aplicación.Probablemente sea el resultado de llamar a una función compilada por MSIL \(\/clr\) desde un constructor nativo o desde DllMain.  
  
 Este diagnóstico indica que se ejecutaban instrucciones MSIL durante el bloqueo del cargador.  Para obtener más información, vea [Inicialización de ensamblados mixtos](../../dotnet/initialization-of-mixed-assemblies.md).