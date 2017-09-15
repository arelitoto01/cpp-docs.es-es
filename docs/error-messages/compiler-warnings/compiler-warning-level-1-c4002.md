---
title: La advertencia C4002 de compilador advertencia (nivel 1) | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 983935ef0e48f94cee3ff08186f27502ea48a7d7
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4002"></a>Advertencia del compilador (nivel 1) C4002
hay demasiados parámetros reales para la macro 'identifier'  
  
 El número de parámetros reales de la macro supera el número de parámetros formales de la definición de macro. El preprocesador obtiene los parámetros adicionales pero los omite durante la expansión de macro.  
  
 La advertencia C4002 puede aparecer al utilizar incorrectamente [Variadic Macros](../../preprocessor/variadic-macros.md).  
  
 El ejemplo siguiente genera la advertencia C4002:  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 Este error también puede generarse como resultado del trabajo de conformidad del compilador efectuado para Visual Studio. NET 2003: ya no se acepta el uso de comas adicionales en la macro.  
  
 El compilador ya no aceptará comas adicionales en una macro. Para que el código sea válido en las versiones de Visual Studio .NET 2003 y de Visual Studio .NET de Visual C++, quite las comas adicionales.  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```