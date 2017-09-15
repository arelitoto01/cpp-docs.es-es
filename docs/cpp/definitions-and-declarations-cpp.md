---
title: "Definiciones y declaraciones (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Definiciones y declaraciones (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Específicos de Microsoft  
 La interfaz DLL hace referencia a todos los elementos \(funciones y datos\) que se sabe que se van a exportar mediante algún programa del sistema, es decir, todos los elementos declarados como **dllimport** o `dllexport`.  Todas las declaraciones incluidas en la interfaz DLL deben especificar el atributo **dllimport** o `dllexport`.  Sin embargo, la definición debe especificar el atributo `dllexport`.  Por ejemplo, la definición de función siguiente genera un error del compilador:  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 Este código también genera un error:  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 Sin embargo, esta es la sintaxis correcta:  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 El uso de `dllexport` implica una definición, mientras que **dllimport** implica una declaración.  Debe utilizar la palabra clave `extern` con `dllexport` para forzar una declaración; en caso contrario, se asume una definición.  Por tanto, los siguientes ejemplos son correctos:  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
DllImport int j;        // declaration.  
```  
  
 Los ejemplos siguientes aclaran los anteriores:  
  
```  
static __declspec( dllimport ) int l; // Error; not declared extern.  
  
void func() {  
    static __declspec( dllimport ) int s;  // Error; not declared  
                                           // extern.  
    __declspec( dllimport ) int m;         // Okay; this is a   
                                           // declaration.  
    __declspec( dllexport ) int n;         // Error; implies external  
                                           // definition in local scope.  
    extern __declspec( dllimport ) int i;  // Okay; this is a  
                                           // declaration.  
    extern __declspec( dllexport ) int k;  // Okay; extern implies  
                                           // declaration.  
    __declspec( dllexport ) int x = 5;     // Error; implies external  
                                           // definition in local scope.  
}  
```  
  
## FIN de Específicos de Microsoft  
  
## Vea también  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)