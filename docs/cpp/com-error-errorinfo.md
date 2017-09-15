---
title: "_com_error::ErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorInfo"
  - "ErrorInfo"
  - "_com_error.ErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorInfo (método)"
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::ErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de Microsoft**  
  
 Recupera el objeto **IErrorInfo** pasado al constructor.  
  
## Sintaxis  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## Valor devuelto  
 Elemento **IErrorInfo** sin formato pasado en el constructor.  
  
## Comentarios  
 Recupera el elemento **IErrorInfo** encapsulado en un objeto `_com_error` o **NULL** si no se registra ningún elemento **IErrorInfo**.  El llamador debe llamar a **Release** en el objeto devuelto cuando termine de usarlo.  
  
 **FIN de Específicos de Microsoft**  
  
## Vea también  
 [\_com\_error \(Clase\)](../cpp/com-error-class.md)