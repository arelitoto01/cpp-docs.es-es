---
title: "Error del compilador C3867 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3867"
ms.assetid: bc5de03f-e01a-4407-88c3-2c63f0016a1e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Error del compilador C3867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'func': falta la lista de argumentos de la llamada a la función; utilice '&func' para crear un puntero al miembro  
  
 Ha intentado tomar la dirección de una función miembro sin calificar la función miembro con su nombre de clase y el operador de dirección.  
  
 Este error también puede generarse como resultado del trabajo de conformidad del compilador efectuado para Visual C\+\+ 2005: conformidad de puntero a miembro mejorada.  El código compilado antes de Visual C\+\+ 2005 ahora generará el error C3867.  
  
## Ejemplo  
 C3867 se puede emitir desde el compilador con una solución sugerida errónea.  Siempre que sea posible, utilice la clase más derivada.  
  
 El ejemplo siguiente genera el error C3867 y muestra cómo corregirlo:  
  
```  
// C3867_1.cpp  
// compile with: /c  
struct Base {   
protected:   
   void Test() {}  
};  
  
class Derived : public Base {   
   virtual void Bar();  
};  
  
void Derived::Bar() {  
   void (Base::*p1)() = Test;   // C3867  
   &Derived::Test;   // OK  
}  
```  
  
## Ejemplo  
 El ejemplo siguiente genera el error C3867 y muestra cómo corregirlo:  
  
```  
// C3867_2.cpp  
#include<stdio.h>  
  
struct S {  
   char *func() {  
      return "message";  
   }  
};  
  
class X {  
public:  
   void f() {}  
};  
  
int main() {  
   X::f;   // C3867  
  
   // OK  
   X * myX = new X;  
   myX->f();  
  
   S s;  
   printf_s("test %s", s.func);   // C3867  
   printf_s("test %s", s.func());   // OK  
}  
```  
  
## Ejemplo  
 El ejemplo siguiente genera el error C3867 y muestra cómo corregirlo:  
  
```  
// C3867_3.cpp  
class X {  
public:  
   void mf(){}  
};  
  
int main() {  
   void (X::*pmf)() = X::mf;   // C3867  
  
   // try the following line instead  
   void (X::*pmf2)() = &X::mf;  
}  
```  
  
## Ejemplo  
 El siguiente ejemplo genera el error C3867:  
  
```  
// C3867_4.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b1;  
      b1.p = f;   // C3867  
   }  
};  
```  
  
## Ejemplo  
 El siguiente ejemplo genera el error C3867:  
  
```  
// C3867_5.cpp  
// compile with: /EHsc  
#include <iostream>  
  
class Testpm {  
public:  
   void m_func1() {  
      std::cout << m_num << "\tm_func1\n";   
    }  
  
   int m_num;  
   typedef void (Testpm::*pmfn1)();  
   void func(Testpm* p);  
};  
  
void Testpm::func(Testpm* p) {  
   pmfn1 s = m_func1;   // C3867  
   pmfn1 s2 = &Testpm::m_func1;   // OK  
   (p->*s2)();  
}  
  
int main() {  
   Testpm *pTestpm = new Testpm;  
   pTestpm->m_num = 10;  
  
   pTestpm->func(pTestpm);  
}  
```