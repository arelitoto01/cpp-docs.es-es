---
title: "C&#243;mo: Usar eventos en C++/CLI | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "eventos [C++], acceso en interfaces"
ms.assetid: fbf452dc-2dd7-4322-adc0-656512d654d1
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C&#243;mo: Usar eventos en C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En este artículo se muestra cómo utilizar una interfaz que declara un evento y una función para invocar ese evento, y la clase y el controlador de eventos que implementan la interfaz.  
  
## Eventos de interfaz  
 El ejemplo de código siguiente se agrega un controlador de eventos, invoca evento\- que hace que el controlador de eventos para escribir su nombre a consola\- y quita el controlador de eventos.  
  
```  
// mcppv2_events2.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void Del(int, float);  
  
// interface that has an event and a function to invoke the event  
interface struct I {  
public:  
   event Del ^ E;  
   void fire(int, float);     
};  
  
// class that implements the interface event and function  
ref class EventSource: public I {  
public:  
   virtual event Del^ E;  
   virtual void fire(int i, float f) {  
      E(i, f);  
   }  
};  
  
// class that defines the event handler  
ref class EventReceiver {  
public:  
   void Handler(int i , float f) {  
      Console::WriteLine("EventReceiver::Handler");  
   }  
};  
  
int main () {  
   I^ es = gcnew EventSource();  
   EventReceiver^ er = gcnew EventReceiver();  
  
   // hook the handler to the event  
   es->E += gcnew Del(er, &EventReceiver::Handler);  
  
   // call the event  
   es -> fire(1, 3.14);  
  
   // unhook the handler from the event  
   es->E -= gcnew Del(er, &EventReceiver::Handler);  
}  
```  
  
 **Resultados**  
  
  **EventReceiver::Handler**   
## Métodos personalizados de descriptor de acceso  
 El ejemplo siguiente se muestra cómo definir el comportamiento de un evento cuando se agregan o quitan controladores, y cuando se provoca un evento.  
  
```  
// mcppv2_events6.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void MyDel();  
public delegate int MyDel2(int, float);  
  
ref class EventSource {  
public:  
   MyDel ^ pE;  
   MyDel2 ^ pE2;  
  
   event MyDel^ E {  
      void add(MyDel^ p) {  
         pE = static_cast<MyDel^> (Delegate::Combine(pE, p));   
         // cannot refer directly to the event  
         // E = static_cast<MyDel^> (Delegate::Combine(pE, p));   // error  
      }  
  
      void remove(MyDel^ p) {  
         pE = static_cast<MyDel^> (Delegate::Remove(pE, p));  
      }  
  
      void raise() {  
         if (pE != nullptr)  
            pE->Invoke();  
      }  
   }  // E event block  
  
   event MyDel2^ E2 {  
      void add(MyDel2^ p2) {  
         pE2 = static_cast<MyDel2^> (Delegate::Combine(pE2, p2));   
      }  
  
      void remove(MyDel2^ p2) {  
         pE2 = static_cast<MyDel2^> (Delegate::Remove(pE2, p2));  
      }  
  
      int raise(int i, float f) {  
         if (pE2 != nullptr) {  
            return pE2->Invoke(i, f);  
         }  
         return 1;  
      }  
   } // E2 event block  
};  
  
public ref struct EventReceiver {  
   void H1() {  
      Console::WriteLine("In event handler H1");  
   }  
  
   int H2(int i, float f) {  
      Console::WriteLine("In event handler H2 with args {0} and {1}", i.ToString(), f.ToString());  
      return 0;  
   }  
};  
  
int main() {  
   EventSource ^ pE = gcnew EventSource;  
   EventReceiver ^ pR = gcnew EventReceiver;  
  
   // hook event handlers  
   pE->E += gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 += gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events  
   pE->E();  
   pE->E2::raise(1, 2.2);   // call event through scope path  
  
   // unhook event handlers  
   pE->E -= gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 -= gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events, but no handlers  
   pE->E();  
   pE->E2::raise(1, 2.5);  
}  
```  
  
 **Resultados**  
  
  **En el controlador de eventos H1**  
**En el controlador de eventos H2 con args 1 y 2,2**   
## El acceso predeterminado de reemplazo en agregar, quitar, y referencia cultural descriptores de acceso  
 Este ejemplo muestra cómo reemplazar el acceso predeterminado en el agregar, quitar, y generar métodos de eventos:  
  
```  
// mcppv2_events3.cpp  
// compile with: /clr  
public delegate void f(int);  
  
public ref struct E {  
   f ^ _E;  
public:  
   void handler(int i) {  
      System::Console::WriteLine(i);  
   }  
  
   E() {  
      _E = nullptr;  
   }  
  
   event f^ Event {  
      void add(f ^ d) {  
         _E += d;  
      }  
   private:  
      void remove(f ^ d) {  
        _E -= d;  
      }  
  
   protected:  
      void raise(int i) {  
         if (_E) {  
            _E->Invoke(i);  
         }  
      }  
   }  
  
   // a member function to access all event methods  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->Event += gcnew f(pE, &E::handler);  
      pE->Event(17);   // prints 17  
      pE->Event -= gcnew f(pE, &E::handler);  
      pE->Event(17);   // no output  
   }  
};  
  
int main() {  
   E::Go();  
}  
```  
  
 **Resultados**  
  
  **17**   
## Controladores de eventos si  
 Un receptor de eventos, o cualquier otro código de cliente, puede agregar uno o más controladores a un evento.  
  
```  
// mcppv2_events4.cpp  
// compile with: /clr  
using namespace System;  
#include <stdio.h>  
  
delegate void ClickEventHandler(int, double);  
delegate void DblClickEventHandler(String^);  
  
ref class EventSource {  
public:  
   event ClickEventHandler^ OnClick;  
   event DblClickEventHandler^ OnDblClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
      OnDblClick("Started");  
   }  
};  
  
ref struct EventReceiver {  
public:  
   void Handler1(int x, double y) {  
      System::Console::Write("Click(x={0},y={1})\n", x, y);  
   };  
  
   void Handler2(String^ s) {  
      System::Console::Write("DblClick(s={0})\n", s);  
   }  
  
   void Handler3(String^ s) {  
      System::Console::WriteLine("DblClickAgain(s={0})\n", s);  
   }  
  
   void AddHandlers(EventSource^ pES) {  
      pES->OnClick +=   
         gcnew ClickEventHandler(this,&EventReceiver::Handler1);  
      pES->OnDblClick +=   
         gcnew DblClickEventHandler(this,&EventReceiver::Handler2);  
      pES->OnDblClick +=   
         gcnew DblClickEventHandler(this, &EventReceiver::Handler3);  
   }  
  
   void RemoveHandlers(EventSource^ pES) {  
      pES->OnClick -=   
         gcnew ClickEventHandler(this, &EventReceiver::Handler1);  
      pES->OnDblClick -=   
         gcnew DblClickEventHandler(this, &EventReceiver::Handler2);  
      pES->OnDblClick -=   
         gcnew DblClickEventHandler(this, &EventReceiver::Handler3);  
   }  
};  
  
int main() {  
   EventSource^ pES = gcnew EventSource;  
   EventReceiver^ pER = gcnew EventReceiver;  
  
   // add handlers  
   pER->AddHandlers(pES);  
  
   pES->FireEvents();  
  
   // remove handlers  
   pER->RemoveHandlers(pES);  
}  
```  
  
 **Resultados**  
  
  **Haga clic en \(x\=7, y\=3.14159\)**  
**DblClick \(s\=System.Char \[\]\)**  
**DblClickAgain \(s\=System.Char \[\]\)**   
## Eventos estáticos  
 El ejemplo siguiente se muestra cómo definir y utilizar eventos estáticos.  
  
```  
// mcppv2_events7.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void MyDel();  
public delegate int MyDel2(int, float);  
  
ref class EventSource {  
public:  
   static MyDel ^ psE;  
   static event MyDel2 ^ E2;   // event keyword, compiler generates add,   
                               // remove, and Invoke  
  
   static event MyDel ^ E {  
      static void add(MyDel ^ p) {  
         psE = static_cast<MyDel^> (Delegate::Combine(psE, p));  
      }  
  
      static void remove(MyDel^ p) {  
         psE = static_cast<MyDel^> (Delegate::Remove(psE, p));  
      }  
  
      static void raise() {  
         if (psE != nullptr)   //psE!=0 -> C2679, use nullptr  
            psE->Invoke();   
      }  
   }  
  
   static int Fire_E2(int i, float f) {  
      return E2(i, f);  
   }  
};  
  
public ref struct EventReceiver {  
   void H1() {  
      Console::WriteLine("In event handler H1");  
   }  
  
   int H2(int i, float f) {  
      Console::WriteLine("In event handler H2 with args {0} and {1}", i.ToString(), f.ToString());  
      return 0;  
   }  
};  
  
int main() {  
   EventSource^ pE = gcnew EventSource;  
   EventReceiver^ pR = gcnew EventReceiver;  
  
   // Called with "this"  
   // hook event handlers  
   pE->E += gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 += gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events  
   pE->E();  
   pE->Fire_E2(11, 11.11);  
  
   // unhook event handlers  
   pE->E -= gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 -= gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // Not called with "this"  
   // hook event handler  
   EventSource::E += gcnew MyDel(pR, &EventReceiver::H1);  
   EventSource::E2 += gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events  
   EventSource::E();  
   EventSource::Fire_E2(22, 22.22);  
  
   // unhook event handlers  
   EventSource::E -= gcnew MyDel(pR, &EventReceiver::H1);  
   EventSource::E2 -= gcnew MyDel2(pR, &EventReceiver::H2);  
}  
```  
  
 **Resultados**  
  
  **En el controlador de eventos H1**  
**En el controlador de eventos H2 con args 11 y 11,11**  
**En el controlador de eventos H1**  
**En el controlador de eventos H2 con args 22 y 22,22**   
## Eventos virtuales  
 Este ejemplo implementa eventos virtuales, administrados en una interfaz y la clase:  
  
```  
// mcppv2_events5.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void MyDel();  
public delegate int MyDel2(int, float);  
  
// managed class that has a virtual event  
ref class IEFace {  
public:  
   virtual event MyDel ^ E;   // declares three accessors (add, remove, and raise)  
};  
  
// managed interface that has a virtual event  
public interface struct IEFace2 {  
public:  
   event MyDel2 ^ E2;   // declares two accessors (add and remove)  
};  
  
// implement virtual events  
ref class EventSource : public IEFace, public IEFace2 {  
public:  
   virtual event MyDel2 ^ E2;  
  
   void Fire_E() {  
      E();  
   }  
  
   int Fire_E2(int i, float f) {  
      try {  
         return E2(i, f);  
      }  
      catch(System::NullReferenceException^) {  
         return 0;   // no handlers  
      }  
   }  
};  
  
// class to hold event handlers, the event receiver  
public ref struct EventReceiver {  
   // first handler  
   void H1() {  
      Console::WriteLine("In handler H1");  
   }  
  
   // second handler  
   int H2(int i, float f) {  
      Console::WriteLine("In handler H2 with args {0} and {1}", i.ToString(), f.ToString());  
      return 0;  
   }  
};  
  
int main() {  
   EventSource ^ pE = gcnew EventSource;  
   EventReceiver ^ pR = gcnew EventReceiver;  
  
   // add event handlers  
   pE->E += gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 += gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events  
   pE->Fire_E();  
   pE->Fire_E2(1, 2.2);  
  
   // remove event handlers  
   pE->E -= gcnew MyDel(pR, &EventReceiver::H1);  
   pE->E2 -= gcnew MyDel2(pR, &EventReceiver::H2);  
  
   // raise events, but no handlers; so, no effect  
   pE->Fire_E();  
   pE->Fire_E2(1, 2.5);  
}  
```  
  
 **Resultados**  
  
  **En el controlador H1**  
**En el controlador H2 con args 1 y 2,2** Un evento simple no se puede especificar para invalidar u ocultar un evento de clase base.  Debe definir las funciones del descriptor de acceso del evento, y especifique la palabra clave de `new` o de `override` en cada función de descriptor de acceso.  
  
```  
// mcppv2_events5_a.cpp  
// compile with: /clr /c  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
   virtual event Del ^E2;  
};  
  
ref struct B : A {  
   virtual event Del ^E override;   // C3797  
   virtual event Del ^E2 new;   // C3797  
};  
  
ref struct C : B {  
   virtual event Del ^E {   // OK  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
  
   virtual event Del ^E2 {   // OK  
      void raise() new {}  
      void add(Del ^) new {}  
      void remove(Del^) new {}  
   }  
};  
```  
  
## Eventos abstractos  
 El ejemplo siguiente se muestra cómo implementar un evento abstracto.  
  
```  
// mcppv2_events10.cpp  
// compile with: /clr /W1  
using namespace System;  
public delegate void Del();  
public delegate void Del2(String^ s);  
  
interface struct IEvent {  
public:  
   // in this case, no raised method is defined  
   event Del^ Event1;  
  
   event Del2^ Event2 {  
   public:  
      void add(Del2^ _d);  
      void remove(Del2^ _d);  
      void raise(String^ s);  
   }  
  
   void fire();  
};  
  
ref class EventSource: public IEvent {  
public:  
   virtual event Del^ Event1;  
   event Del2^ Event2 {  
      virtual void add(Del2^ _d) {  
         d = safe_cast<Del2^>(System::Delegate::Combine(d, _d));  
      }  
  
      virtual void remove(Del2^ _d) {  
         d = safe_cast<Del2^>(System::Delegate::Remove(d, _d));  
      }  
  
      virtual void raise(String^ s) {  
         if (d) {  
            d->Invoke(s);  
         }  
      }  
   }  
  
   virtual void fire() {  
      return Event1();  
   }  
  
private:  
   Del2^ d;  
};  
  
ref class EventReceiver {  
public:  
   void func() {  
      Console::WriteLine("hi");  
   }  
  
   void func(String^ str) {  
      Console::WriteLine(str);  
   }  
};  
  
int main () {  
   IEvent^ es = gcnew EventSource;  
   EventReceiver^ er = gcnew EventReceiver;  
   es->Event1 += gcnew Del(er, &EventReceiver::func);  
   es->Event2 += gcnew Del2(er, &EventReceiver::func);  
  
   es->fire();  
   es->Event2("hello from Event2");  
   es->Event1 -= gcnew Del(er, &EventReceiver::func);  
   es->Event2 -= gcnew Del2(er, &EventReceiver::func);  
   es->Event2("hello from Event2");  
}  
```  
  
 **Resultados**  
  
  **hi**  
**hello de Event2**   
## Provocar eventos definidos en un ensamblado diferente  
 Un evento y un controlador de eventos se pueden definir en un ensamblado, y utilizar en otro ensamblado.  
  
```  
// mcppv2_events8.cpp  
// compile with: /LD /clr  
using namespace System;  
  
public delegate void Del(String^ s);  
  
public ref class Source {  
public:  
   event Del^ Event;  
   void Fire(String^ s) {  
      Event(s);  
   }  
};  
```  
  
 Este código de cliente utiliza el evento:  
  
```  
// mcppv2_events9.cpp  
// compile with: /clr  
#using "mcppv2_events8.dll"  
using namespace System;  
  
ref class Receiver {  
public:  
   void Handler(String^ s) {  
      Console::WriteLine(s);  
   }  
};  
  
int main() {  
   Source^ src = gcnew Source;  
   Receiver^ rc1 = gcnew Receiver;  
   Receiver^ rc2 = gcnew Receiver;  
   src -> Event += gcnew Del(rc1, &Receiver::Handler);  
   src -> Event += gcnew Del(rc2, &Receiver::Handler);  
   src->Fire("hello");  
   src -> Event -= gcnew Del(rc1, &Receiver::Handler);  
   src -> Event -= gcnew Del(rc2, &Receiver::Handler);  
}  
```  
  
 **Resultados**  
  
  **hello**  
**hello**   
## Vea también  
 [event](../windows/event-cpp-component-extensions.md)