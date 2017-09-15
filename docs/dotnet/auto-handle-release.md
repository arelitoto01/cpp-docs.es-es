---
title: "auto_handle::release | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_handle::release"
  - "auto_handle.release"
  - "msclr.auto_handle.release"
  - "auto_handle::release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::release"
ms.assetid: d4848150-859e-4c61-a946-09d24d3d6577
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libera el objeto de administración `auto_handle` .  
  
## Sintaxis  
  
```  
_element_type ^ release();  
```  
  
## Valor devuelto  
 El objeto publicado.  
  
## Ejemplo  
  
```  
// msl_auto_handle_release.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );     
   }  
};  
  
int main()  
{  
   ClassA^ a;  
  
   // create a new scope:  
   {  
      auto_handle<ClassA> agc1 = gcnew ClassA( "first" );  
      auto_handle<ClassA> agc2 = gcnew ClassA( "second" );  
      a = agc1.release();  
   }  
   // agc1 and agc2 go out of scope here  
  
   a->PrintHello();  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **Constructor de ClassA: primero**  
**Constructor de ClassA: en segundo lugar**  
**ClassA destructor: en segundo lugar**  
**¡Hola primero de A\!**  
**done**   
## Requisitos  
 **Archivo de encabezado** \<msclr\\auto\_handle.h\>  
  
 msclr de**Namespace**  
  
## Vea también  
 [auto\_handle \(Miembros\)](../dotnet/auto-handle-members.md)   
 [auto\_handle::~auto\_handle](../dotnet/auto-handle-tilde-auto-handle.md)   
 [auto\_handle::reset](../dotnet/auto-handle-reset.md)