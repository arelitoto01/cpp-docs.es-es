---
title: "Operador de identificador de objeto (^) (Extensiones de componentes de C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "^ identificador a un objeto [C++]"
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Operador de identificador de objeto (^) (Extensiones de componentes de C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

El *declarador del identificador* \(`^`, acento circunflejo\) modifica el tipo [specifier](../cpp/overview-of-declarators.md) para indicar que el objeto declarado debe eliminarse automáticamente cuando el sistema determina que el objeto ya no es accesible.  
  
## Acceso al objeto declarado  
 Una variable que se declara con el declarador de identificador se comporta como un puntero al objeto.  Sin embargo, la variable apunta al objeto completo, no puede apuntar a un miembro del objeto y no admite la aritmética con punteros.  Utilice el operador de direccionamiento indirecto \(`*`\) para tener acceso al objeto y el operador de acceso de miembro de flecha \(`->`\) para tener acceso a un miembro del objeto.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 El compilador utiliza el mecanismo de *recuento de referencias* de COM para determinar si el objeto ya no se usa y se puede eliminar.  Esto es posible debido a que un objeto que se deriva de una interfaz de Windows en tiempo de ejecución es, en realidad, un objeto COM.  El recuento de referencias se incrementa cuando se crea o se copia el objeto y se reduce cuando el objeto se establece en null o queda fuera de ámbito.  Si el recuento de referencias llega a cero, el objeto se elimina de inmediato y de manera automática.  
  
 La ventaja del declarador del identificador es que, en COM, debe administrar de manera explícita el recuento de referencias para un objeto, lo cual es un proceso tedioso que puede dar lugar a errores.  Es decir, para aumentar y disminuir el recuento de referencias, debe invocar los métodos AddRef\(\) y Release\(\) del objeto.  Sin embargo, si declara un objeto con el declarador de identificador, el compilador de Visual C\+\+ genera código que ajusta de manera automática el recuento de referencias.  
  
 Para obtener información sobre cómo crear instancias de un objeto, vea [ref new](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
## Requisitos  
 Opción del compilador: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 El sistema utiliza el mecanismo del *recolector de elementos no utilizados* de CLR para determinar si el objeto ya no se utiliza y se puede eliminar.  Common Language Runtime mantiene un montón donde asigna objetos y usa las referencias administradas \(variables\) del programa para indicar la ubicación de objetos en el montón.  Cuando un objeto ya no se usa, se libera la memoria que ocupaba en el montón.  De manera periódica, el recolector de elementos no utilizados compacta el montón para mejorar el uso de la memoria liberada.  Al compactar el montón, se pueden mover sus objetos, lo que invalida las ubicaciones que usan las referencias administradas.  Sin embargo, el recolector de elementos no utilizados reconoce la ubicación de todas las referencias administradas y las actualiza automáticamente para indicar la ubicación actual de los objetos en el montón.  
  
 Dado que los punteros de C\+\+ nativo \(`*`\) y las referencias \(`&`\) no son referencias administradas, el recolector de elementos no utilizados no puede actualizar de manera automática las direcciones a las que apuntan.  Para solucionar este problema, utilice el declarador de identificador para especificar una variable que el recolector de elementos no utilizados reconozca y pueda actualizar automáticamente.  
  
 En Visual C\+\+ 2002 y Visual C\+\+ 2003, se utiliza `__gc *` para declarar un objeto del montón administrado.  `^` reemplaza a `__gc *` en la nueva sintaxis.  
  
 Para obtener más información, vea [Cómo: Declarar controladores en tipos nativos](../dotnet/how-to-declare-handles-in-native-types.md).  
  
### Ejemplos  
 **Ejemplo**  
  
 En este ejemplo se muestra cómo crear una instancia de un tipo de referencia en el montón administrado.  En este ejemplo se muestra también que puede inicializar un identificador con otro, lo que da a lugar a dos referencias al mismo objeto en el montón de recolección de elementos no utilizados administrado.  Observe que la asignación de [nullptr](../windows/nullptr-cpp-component-extensions.md) a un identificador no marca el objeto para la recolección de elementos no utilizados.  
  
```  
// mcppv2_handle.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   MyClass() : i(){}  
   int i;  
   void Test() {  
      i++;  
      System::Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass->Test();  
  
   MyClass ^ p_MyClass2;  
   p_MyClass2 = p_MyClass;  
  
   p_MyClass = nullptr;  
   p_MyClass2->Test();     
}  
```  
  
 **Resultados**  
  
 **1**   
**2** **Ejemplo**  
  
 En el ejemplo siguiente se muestra cómo declarar un identificador para un objeto del montón administrado, donde el tipo de objeto es un tipo de valor de conversión boxing.  En el ejemplo también se muestra cómo obtener el tipo de valor del objeto al que se ha aplicado la conversión boxing.  
  
```  
// mcppv2_handle_2.cpp  
// compile with: /clr  
using namespace System;  
  
void Test(Object^ o) {  
   Int32^ i = dynamic_cast<Int32^>(o);  
  
   if(i)  
      Console::WriteLine(i);  
   else  
      Console::WriteLine("Not a boxed int");  
}  
  
int main() {  
   String^ str = "test";  
   Test(str);  
  
   int n = 100;  
   Test(n);  
}  
```  
  
 **Resultados**  
  
  **No es un entero al que se ha aplicado una conversión boxing**  
 **100** **Ejemplo**  
  
 En este ejemplo se muestra que la expresión común de C\+\+ de usar un puntero void\* para apuntar a un objeto arbitrario se reemplaza por Object^, que puede contener un identificador para cualquier clase de referencia.  También se muestra que todos los tipos, como matrices y delegados, pueden convertirse en un identificador de objeto.  
  
```  
// mcppv2_handle_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
public delegate void MyDel();  
ref class MyClass {  
public:  
   void Test() {}  
};  
  
void Test(Object ^ x) {  
   Console::WriteLine("Type is {0}", x->GetType());  
}  
  
int main() {  
   // handle to Object can hold any ref type  
   Object ^ h_MyClass = gcnew MyClass;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(gcnew MyClass);  
  
   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);  
   Test(arr);  
  
   Int32 ^ bi = 1;  
   Test(bi);  
  
   MyClass ^ h_MyClass2 = gcnew MyClass;  
  
   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);  
   Test(DelInst);  
}  
```  
  
 **Resultados**  
  
  **El tipo es System.Collections.ArrayList**  
 **El tipo es System.Int32**  
 **El tipo es MyDel** **Ejemplo**  
  
 En este ejemplo se muestra que se puede deshacer la referencia de un identificador y se puede tener acceso a un miembro mediante un identificador sin referencia.  
  
```  
// mcppv2_handle_4.cpp  
// compile with: /clr  
using namespace System;  
value struct DataCollection {  
private:  
   int Size;  
   array<String^>^ x;  
  
public:  
   DataCollection(int i) : Size(i) {  
      x = gcnew array<String^>(Size);  
      for (int i = 0 ; i < Size ; i++)  
         x[i] = i.ToString();  
   }  
  
   void f(int Item) {  
      if (Item >= Size)  
      {  
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);  
         return;  
      }  
      else  
         System::Console::WriteLine("Array value: {0}", x[Item]);  
   }  
};  
  
void f(DataCollection y, int Item) {  
   y.f(Item);  
}  
  
int main() {  
   DataCollection ^ a = gcnew DataCollection(10);  
   f(*a, 7);   // dereference a handle, return handle's object  
   (*a).f(11);   // access member via dereferenced handle  
}  
```  
  
 **Resultados**  
  
  **Valor de matriz: 7**  
 **No se puede obtener acceso al elemento de matriz 11; el tamaño es 10** **Ejemplo**  
  
 En este ejemplo se muestra que no se puede enlazar una referencia nativa \(`&`\) a un miembro `int` de un tipo administrado, ya que `int` se podría almacenar en el montón de recolección de elementos no utilizados y las referencias nativas no realizan un seguimiento del movimiento de objetos en el montón administrado.  La solución es utilizar una variable local o cambiar `&` a `%`, convirtiéndola en una referencia de seguimiento.  
  
```  
// mcppv2_handle_5.cpp  
// compile with: /clr  
ref struct A {  
   void Test(unsigned int &){}  
   void Test2(unsigned int %){}  
   unsigned int i;  
};  
  
int main() {  
   A a;  
   a.i = 9;  
   a.Test(a.i);   // C2664  
   a.Test2(a.i);   // OK  
  
   unsigned int j = 0;  
   a.Test(j);   // OK  
}  
```  
  
### Requisitos  
 Opción del compilador: **\/clr**  
  
## Vea también  
 [Extensiones de componentes para plataformas de tiempo de ejecución](../windows/component-extensions-for-runtime-platforms.md)   
 [Operador de referencia de seguimiento](../windows/tracking-reference-operator-cpp-component-extensions.md)