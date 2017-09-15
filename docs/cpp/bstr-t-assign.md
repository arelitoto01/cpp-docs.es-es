---
title: "_bstr_t::Assign | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::Assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assign (método)"
ms.assetid: 2e209bbe-77ca-4598-86d5-6c2ea213f43c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _bstr_t::Assign
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específicos de Microsoft**  
  
 Copia `BSTR` en el objeto `BSTR` contenido en **\_**`bstr_t`.  
  
## Sintaxis  
  
```  
void Assign(  
   BSTR s  
);  
```  
  
#### Parámetros  
 `s`  
 `BSTR` que se copia en el objeto `BSTR` contenido en `_bstr_t`.  
  
## Comentarios  
 `Assign` hace una copia binaria, lo que significa que se copia toda la longitud de `BSTR`, sin importar su contenido.  
  
## Ejemplo  
  
```  
// _bstr_t_Assign.cpp  
  
#include <comdef.h>  
#include <stdio.h>  
  
int main()  
{  
    // creates a _bstr_t wrapper  
    _bstr_t bstrWrapper;   
  
    // creates BSTR and attaches to it  
    bstrWrapper = "some text";  
    wprintf_s(L"bstrWrapper = %s\n",  
              static_cast<wchar_t*>(bstrWrapper));  
  
    // bstrWrapper releases its BSTR  
    BSTR bstr = bstrWrapper.Detach();  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    // "some text"   
    wprintf_s(L"bstr = %s\n", bstr);  
  
    bstrWrapper.Attach(SysAllocString(OLESTR("SysAllocedString")));  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
  
    // assign a BSTR to our _bstr_t  
    bstrWrapper.Assign(bstr);  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
  
    // done with BSTR, do manual cleanup  
    SysFreeString(bstr);  
  
    // resuse bstr  
    bstr= SysAllocString(OLESTR("Yet another string"));  
    // two wrappers, one BSTR   
    _bstr_t bstrWrapper2 = bstrWrapper;     
  
    *bstrWrapper.GetAddress() = bstr;  
  
    // bstrWrapper and bstrWrapper2 do still point to BSTR  
    bstr = 0;     
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    wprintf_s(L"bstrWrapper2 = %s\n",   
              static_cast<wchar_t*>(bstrWrapper2));  
  
    // new value into BSTR  
    _snwprintf_s(bstrWrapper.GetBSTR(), 100, bstrWrapper.length(),  
                 L"changing BSTR");     
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    wprintf_s(L"bstrWrapper2 = %s\n",   
              static_cast<wchar_t*>(bstrWrapper2));  
}  
```  
  
  **bstrWrapper \= some text**  
**bstrWrapper \= \(null\)**  
**bstr \= some text**  
**bstrWrapper \= SysAllocedString**  
**bstrWrapper \= some text**  
**bstrWrapper \= Yet another string**  
**bstrWrapper2 \= some text**  
**bstrWrapper \= changing BSTR**  
**bstrWrapper2 \= some text**   
## FIN de Específicos de Microsoft  
  
## Vea también  
 [\_bstr\_t \(Clase\)](../cpp/bstr-t-class.md)