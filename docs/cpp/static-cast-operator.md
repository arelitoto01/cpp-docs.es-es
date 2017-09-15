---
title: "static_cast (Operador) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "static_cast"
  - "static_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "static_cast (palabra clave) [C++]"
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# static_cast (Operador)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convierte *expression* al tipo de *type\-id,* basándose únicamente en los tipos que se encuentran en la expresión.  
  
## Sintaxis  
  
```  
static_cast <type-id> ( expression )   
```  
  
## Comentarios  
 En Standard C\+\+, no se realiza ninguna comprobación de tipo en tiempo de ejecución como ayuda para garantizar la seguridad de la conversión.  En C\+\+\/CX, se realiza una comprobación en tiempo de compilación y en tiempo de ejecución.  Para obtener más información, vea [Convertir](../Topic/Casting%20\(C++-CX\).md).  
  
 Se puede utilizar el operador `static_cast` para operaciones como convertir un puntero a una clase base en un puntero a una clase derivada.  Estas conversiones no siempre son seguras.  
  
 En general, debe utilizar `static_cast` cuando desee convertir tipos de datos numéricos como enumeraciones en valores de tipo int o valores de tipo int en flotantes, y sepa con seguridad los tipos de datos implicados en la conversión.  Las conversiones `static_cast` no son tan seguras como las conversiones `dynamic_cast`, ya que `static_cast` no realiza ninguna comprobación de tipo en tiempo de ejecución, mientras que `dynamic_cast` sí la hace.  Una conversión `dynamic_cast` a un puntero ambiguo producirá un error, mientras que `static_cast` vuelve como si no hubiera nada incorrecto; esto puede ser peligroso.  Aunque las conversiones `dynamic_cast` son más seguras, `dynamic_cast` solo funciona en punteros o referencias, y la comprobación del tipo en tiempo de ejecución supone una sobrecarga.  Para obtener más información, vea [dynamic\_cast \(Operador\)](../cpp/dynamic-cast-operator.md).  
  
 En el ejemplo siguiente, la línea `D* pd2 = static_cast<D*>(pb);` no es segura porque `D` puede tener campos y métodos que no están en `B`.  Sin embargo, la línea `B* pb2 = static_cast<B*>(pd);` es una conversión segura porque `D` siempre contiene todo `B`.  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 A diferencia de [dynamic\_cast](../cpp/dynamic-cast-operator.md), no se realiza ninguna comprobación en tiempo de ejecución en la conversión `static_cast` de `pb`.  El objeto al que apunta `pb` puede no ser un objeto de tipo `D`, en cuyo caso el uso de `*pd2` podría ser desastroso.  Por ejemplo, la llamada a una función que es miembro de la clase `D`, pero no de la clase `B`, podría producir una infracción de acceso.  
  
 Los operadores `dynamic_cast` y `static_cast` mueven un puntero en una jerarquía de clases.  Sin embargo, `static_cast` utiliza exclusivamente la información proporcionada en la instrucción de conversión y, por tanto, puede que no sea segura.  Por ejemplo:  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 Si `pb` apunta realmente un objeto de tipo `D`, `pd1` y `pd2` obtienen el mismo valor.  También obtienen el mismo valor si `pb == 0`.  
  
 Si `pb` apunta a un objeto de tipo `B` y no a toda la clase `D`, `dynamic_cast` sabe suficiente para devolver cero.  Sin embargo, `static_cast` utiliza la aserción del programador de que `pb` apunta a un objeto de tipo `D` y simplemente devuelve un puntero a ese objeto `D` supuesto.  
  
 Por tanto, `static_cast` puede hacer lo contrario de las conversiones implícitas, en cuyo caso los resultados son indefinidos.  Es el programador quien tiene que comprobar que los resultados de una conversión `static_cast` son seguros.  
  
 Este comportamiento también se aplica a los tipos distintos de los tipos de clase.  Por ejemplo, se puede utilizar `static_cast` para convertir de un tipo int a un tipo `char`.  Sin embargo, el tipo `char` resultante quizás no tenga suficientes bits para almacenar todo el valor `int`.  Una vez más, es el programador quien tiene que comprobar que los resultados de una conversión`static_cast` son seguros.  
  
 También se puede utilizar el operador `static_cast` para realizar cualquier conversión implícita, incluidas las conversiones estándar y las conversiones definidas por el usuario.  Por ejemplo:  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 El operador `static_cast` puede convertir explícitamente un valor entero en un tipo de enumeración.  Si el valor del tipo entero no está dentro del intervalo de valores de enumeración, el valor de enumeración resultante no está definido.  
  
 El operador `static_cast` convierte un valor de puntero NULL al valor de puntero NULL del tipo de destino.  
  
 El operador `static_cast` puede convertir explícitamente cualquier expresión al tipo void.  El tipo void de destino puede incluir opcionalmente el atributo `const`, `volatile` o `__unaligned`.  
  
 El operador `static_cast` no puede desechar los atributos `const`, `volatile` o `__unaligned`.  Vea [const\_cast \(Operador\)](../cpp/const-cast-operator.md) para obtener información sobre cómo quitar estos atributos.  
  
 Debido al riesgo que supone realizar conversiones no comprobadas además de reubicar un recolector de elementos no utilizados, `static_cast` solo debe utilizarse en código que sea crítico para el rendimiento cuando esté seguro de que funcionará correctamente.  Si debe utilizar `static_cast` en modo de lanzamiento, sustitúyalo con [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) en las compilaciones de depuración para asegurarse de que funciona correctamente.  
  
## Vea también  
 [Operadores de conversión](../cpp/casting-operators.md)   
 [Palabras clave de C\+\+](../cpp/keywords-cpp.md)