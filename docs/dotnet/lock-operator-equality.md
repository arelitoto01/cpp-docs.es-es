---
title: "lock::operator== | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "lock::operator=="
  - "msclr.lock.operator=="
  - "msclr::lock::operator=="
  - "lock.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::operator=="
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::operator==
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operador de igualdad.  
  
## Sintaxis  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### Parámetros  
 `t`  
 El objeto cuya igualdad se va a comparar.  
  
## Valor devuelto  
 Devuelve `true` si `t` es igual que el objeto de bloqueo, `false` de otra manera.  
  
## Ejemplo  
  
```  
// msl_lock_op_eq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   lock l1(o1);  
   if (l1 == o1) {  
      Console::WriteLine("Equal!");  
   }  
}  
```  
  
  **¡Igual\!**   
## Requisitos  
 **Archivo de encabezado** \<msclr\\lock.h\>  
  
 msclr de**Namespace**  
  
## Vea también  
 [lock \(Miembros\)](../dotnet/lock-members.md)   
 [lock::operator\!\=](../dotnet/lock-operator-inequality.md)