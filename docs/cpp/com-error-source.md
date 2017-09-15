---
title: "_com_error::Source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Source (método)"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de Microsoft**  
  
 Llama a la función **IErrorInfo::GetSource**.  
  
## Sintaxis  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## Valor devuelto  
 Devuelve el resultado de **IErrorInfo::GetSource** para el objeto **IErrorInfo** registrado dentro del objeto `_com_error`.  El BSTR resultante se encapsula en un objeto `_bstr_t`.  Si no se registra ningún objeto **IErrorInfo**, devuelve un `_bstr_t` vacío.  
  
## Comentarios  
 Cualquier error que se produzca mientras se llama al método **IErrorInfo::GetSource** se omite.  
  
 **FIN de Específicos de Microsoft**  
  
## Vea también  
 [\_com\_error \(Clase\)](../cpp/com-error-class.md)