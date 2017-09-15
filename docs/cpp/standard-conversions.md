---
title: "Conversiones est&#225;ndar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversiones, estándar"
  - "valores L"
  - "conversiones estándar, categorías de"
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversiones est&#225;ndar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

El lenguaje C\+\+ define conversiones entre sus tipos fundamentales.  También define conversiones para tipos derivados de puntero, referencia y puntero a miembro.  Estas conversiones se denominan "conversiones estándar". \(Para más información sobre los tipos, los tipos estándar y los tipos derivados, vea [Tipos](http://msdn.microsoft.com/es-es/6882ee83-ea32-4373-8d57-c3efbbc15af0)\).  
  
 Esta sección trata las conversiones estándar siguientes:  
  
-   [Promociones de enteros](../misc/integral-promotions.md)  
  
-   [Conversiones de enteros](../misc/integral-conversions.md)  
  
-   [Conversiones de punto flotante](../misc/floating-conversions.md)  
  
-   [Conversiones de punto flotante y de enteros](../misc/floating-and-integral-conversions.md)  
  
-   [Conversiones aritméticas](../misc/arithmetic-conversions.md)  
  
-   [Conversiones de puntero](../misc/pointer-conversions-cpp.md)  
  
-   [Conversiones de referencia](../misc/reference-conversions.md)  
  
-   [Conversiones de puntero a miembro](../misc/pointer-to-member-conversions.md)  
  
    > [!NOTE]
    >  Los tipos definidos por el usuario pueden especificar sus propias conversiones.  La conversión de tipos definidos por el usuario se trata en [Constructores](../cpp/constructors-cpp.md) y [Conversiones](../cpp/user-defined-type-conversions-cpp.md).  
  
 El código siguiente provoca conversiones \(en este ejemplo, promociones de enteros\):  
  
```  
long  lnum1, lnum2;  
int   inum;  
  
// inum promoted to type long prior to assignment.  
lnum1 = inum;  
  
// inum promoted to type long prior to multiplication.  
lnum2 = inum * lnum2;  
```  
  
> [!NOTE]
>  El resultado de una conversión solo es un valor L si genera un tipo de referencia.  Por ejemplo, una conversión definida por el usuario declarada como  
  
```  
operator int&()  
```  
  
> [!NOTE]
>  devuelve una referencia y es un valor L.  Sin embargo, una conversión declarada como  
  
```  
operator int()  
```  
  
> [!NOTE]
>  devuelve un objeto y no es un valor L.  
  
## Promociones de enteros  
 Los objetos de un tipo entero se pueden convertir a otro tipo entero más amplio \(es decir, un tipo que puede representar un conjunto de valores más grande\).  Este tipo de ampliación de conversión se denomina "promoción de entero". Con la promoción de entero, puede utilizar lo siguiente en una expresión dondequiera que otro tipo entero se pueda utilizar:  
  
-   Objetos, literales y constantes de tipo `char` y `short int`  
  
-   Tipos de enumeración  
  
-   Campos de bits `int`  
  
-   Enumeradores  
  
 Las promociones de C\+\+ tienen la cualidad de "conservación de valores". Es decir, se garantiza que el valor después de la promoción es igual que el valor antes de la promoción.  En promociones que conservan los valores, los objetos de tipos enteros más cortos \(tales como campos de bits u objetos de tipo `char`\) se promueven al tipo `int` si `int` puede representar el intervalo completo del tipo original.  Si `int` no puede representar el intervalo completo de valores, el objeto se promueve al tipo `unsigned int`.  Aunque esta estrategia es la misma que la utilizada por ANSI C, las conversiones que poseen la cualidad de conservación de valores no conservan el "tipo signed\/unsigned" del objeto.  
  
 Las promociones que poseen la cualidad de conservación de valores y las promociones que conservan el tipo signed\/unsigned generan normalmente los mismos resultados.  Sin embargo, pueden generar resultados diferentes si el objeto que se promueve es uno de los siguientes:  
  
-   Un operando de **\/**, `%`, `/=`, `%=`, **\<**, **\<\=**, **\>** o **\>\=**  
  
     Estos operadores dependen del signo para determinar el resultado.  Por consiguiente, las promociones que poseen la cualidad de conservación de valores y que conservan el tipo signed\/unsigned generan resultados diferentes cuando se aplican a estos operandos.  
  
-   El operando izquierdo de **\>\>** o **\>\>\=**  
  
     Estos operadores tratan las cantidades signed y unsigned de forma diferente cuando realizan una operación de desplazamiento.  En el caso de cantidades signed, el desplazamiento de una cantidad a la derecha hace que el bit de signo se propague a las posiciones de bits desocupadas.  En el caso de cantidades unsigned, las posiciones de bits desocupadas se rellenan con ceros.  
  
-   Un argumento a una función sobrecargada o un operando de un operador sobrecargado que depende de la condición signed\/unsigned de dicho operando para la coincidencia de argumentos.  \(Vea [Operadores sobrecargados](../cpp/operator-overloading.md) para obtener más información sobre la definición de operadores sobrecargados\).  
  
## Conversiones de enteros  
 Las conversiones de enteros se realizan entre tipos enteros.  Los tipos enteros son `char`, `int` y **long** \(y las versiones **short**, **signed** y `unsigned` de estos tipos\).  
  
 **De con signo a sin signo**  
  
 Los objetos de tipos enteros con signo se pueden convertir en los tipos sin signo correspondientes.  Cuando se produce esta conversión, el patrón de bits real no cambia, pero sí la interpretación de los datos.  Considere este código:  
  
```  
// conve__pluslang_Converting_Signed_to_Unsigned.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main()  
{  
    short  i = -3;  
    unsigned short u;  
  
    cout << (u = i) << "\n";  
}  
// Output: 65533  
  
```  
  
 En el ejemplo anterior, se define `signed short`, `i` y se inicializa en un número negativo.  La expresión `(u = i)` hace que `i` se convierta en un número **short sin signo** antes de la asignación a `u`.  
  
 **De con signo a sin signo**  
  
 Los objetos de tipos enteros sin signo se pueden convertir en los tipos con signo correspondientes.  Sin embargo, este tipo de conversión puede producir una interpretación incorrecta de los datos si el valor del objeto sin signo está fuera del intervalo que puede representar el tipo con signo, como se muestra en el ejemplo siguiente:  
  
```  
// conve__pluslang_Converting_Unsigned_to_Signed.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main()  
{  
 short  i;  
 unsigned short u = 65533;  
  
 cout << (i = u) << "\n";  
}  
//Output: -3  
```  
  
 En el ejemplo anterior, `u` es un objeto entero `unsigned` **short** que se debe convertir en una cantidad con signo para evaluar la expresión `(i = u)`.  Como su valor no se puede representar correctamente en `signed short`, los datos se interpretan de forma incorrecta como se muestra.  
  
## Conversiones de punto flotante  
 Un objeto de tipo flotante se puede convertir de forma segura en un tipo flotante más preciso; es decir, la conversión no provoca ninguna pérdida de significado.  Por ejemplo, las conversiones de **float** a **double** o de **double** a `long double` son seguras, y el valor no cambia.  
  
 Un objeto de tipo flotante se puede convertir en un tipo menos preciso, si se encuentra en un intervalo representable por ese tipo.  \(Vea [Límites de punto flotante](../cpp/floating-limits.md) para conocer los intervalos de tipos de punto flotante\). Si el valor original no se puede representar con exactitud, se puede convertir en el siguiente valor representable mayor o menor.  Si no existe dicho valor, el resultado es indefinido.  Considere el ejemplo siguiente:  
  
```  
cout << (float)1E300 << endl;  
```  
  
 El valor máximo que se puede representar mediante el tipo **float** es 3,402823466E38, un número mucho menor que 1E300.  Por tanto, el número se convierte a infinito y el resultado es 1.\#INF.  
  
## Conversiones entre tipos integrales y de punto flotante  
 Algunas expresiones pueden producir la conversión de objetos de tipo flotante a tipos enteros, o viceversa.  Cuando un objeto de tipo entero se convierte a un tipo flotante y el valor original no se puede representar correcta, el resultado es el siguiente valor más alto o más bajo que se puede representar.  
  
 Cuando un objeto de tipo flotante se convierte en un tipo entero, se trunca la parte fraccionaria.  No se realiza ningún redondeo en el proceso de conversión.  El truncamiento significa que un número como 1,3 se convierte en 1, y –1,3 se convierte en –1.  
  
## Conversiones aritméticas  
 Muchos operadores binarios \(descritos en [Expresiones con operadores binarios](../cpp/expressions-with-binary-operators.md)\) originan la conversión de operandos y producen resultados de la misma forma.  La manera en que estos operadores producen conversiones se denomina “conversiones aritméticas usuales”. Las conversiones aritméticas de operandos de diferentes tipos nativos se realizan como se muestra en la tabla siguiente.  Los tipos typedef se comportan de acuerdo con sus tipos nativos subyacentes.  
  
### Condiciones para la conversión de tipos  
  
|Condiciones satisfechas|Conversión|  
|-----------------------------|----------------|  
|Uno de los operandos es de tipo **long double**.|El otro operando se convierte al tipo **long double**.|  
|La condición anterior no se satisface y uno de los operandos es de tipo **double**.|El otro operando se convierte al tipo **double**.|  
|Las condiciones anteriores no se satisfacen y uno de los operandos es de tipo **float**.|El otro operando se convierte al tipo **float**.|  
|Las condiciones anteriores no se satisfacen \(ninguno de los operandos es de tipo flotante\).|Las promociones de entero se realizan en los operandos de la forma siguiente:<br /><br /> -   Si alguno de los operandos es de tipo `unsigned` **long**, el otro operando se convierte al tipo `unsigned long`.<br />-   Si no se satisface la condición anterior y alguno de los operandos es de tipo **long** y el otro de tipo `unsigned` `int`, ambos operandos se convierten al tipo `unsigned long`.<br />-   Si las dos condiciones anteriores no se cumplen y alguno de los operandos es de tipo **long**, el otro operando se convierte al tipo **long**.<br />-   Si las tres condiciones anteriores no se cumplen y alguno de los operandos es de tipo `unsigned int`, el otro operando se convierte al tipo `unsigned int`.<br />-   Si no se cumple ninguna de las condiciones anteriores, ambos operandos se convierten al tipo `int`.|  
  
 En el código siguiente se muestran las reglas de conversión descritas en la tabla:  
  
```  
// arithmetic_conversions.cpp  
double dVal;  
float fVal;  
int iVal;  
unsigned long ulVal;  
  
int main() {  
   // iVal converted to unsigned long  
   // result of multiplication converted to double  
   dVal = iVal * ulVal;  
  
   // ulVal converted to float  
   // result of addition converted to double  
   dVal = ulVal + fVal;  
}  
```  
  
 La primera instrucción del ejemplo anterior muestra la multiplicación de dos tipos enteros, `iVal` y `ulVal`.  La condición satisfecha es que ninguno de los operandos es de tipo flotante y un operando es de tipo `unsigned int`.  Por tanto, el otro operando, `iVal`, se convierte al tipo `unsigned int`.  El resultado se asigna a `dVal`.  La condición satisfecha es que un operando es de tipo **double**; por consiguiente, el resultado `unsigned int` de la multiplicación se convierte al tipo **double**.  
  
 La segunda instrucción del ejemplo anterior muestra la suma de un **float** y un tipo entero, `fVal` y `ulVal`.  La variable `ulVal` se convierte al tipo **float** \(la tercera condición de la tabla\).  El resultado de la suma se convierte al tipo **double** \(la segunda condición de la tabla\) y se asigna a `dVal`.  
  
## Conversiones de puntero  
 Los punteros se pueden convertir durante la asignación, inicialización, comparación y en otras expresiones.  
  
### De puntero a clases  
 Hay dos casos en los que un puntero a una clase se puede convertir en un puntero a una clase base.  
  
 El primer caso es cuando la clase base especificada es accesible y la conversión es inequívoca.  \(Vea [Múltiples clases base](../cpp/multiple-base-classes.md) para obtener más información sobre las referencias de clase base ambigua\).  
  
 Si una clase base es accesible depende del tipo de herencia utilizada en la derivación.  Considere la herencia que se muestra en la siguiente ilustración.  
  
 ![Gráfico de herencia que muestra la accesibilidad a la clase base](../cpp/media/vc38xa1.png "vc38XA1")  
Gráfico de herencia para ilustrar la accesibilidad de clase base  
  
 En la tabla siguiente se muestra la accesibilidad de la clase base para la situación que se muestra en la ilustración.  
  
### Accesibilidad de la clase base  
  
|Tipo de función|Derivación|Conversión de<br /><br /> B\* a A\* legal|  
|---------------------|----------------|---------------------------------------|  
|Función externa \(no de ámbito de clase\)|Privado|No|  
||Protegido|No|  
||Público|Sí|  
|Función miembro B \(en ámbito B\)|Privado|Sí|  
||Protegido|Sí|  
||Público|Sí|  
|Función miembro C \(en ámbito C\)|Privado|No|  
||Protegido|Sí|  
||Público|Sí|  
  
 El segundo caso en el que un puntero a una clase se puede convertir a un puntero a una clase base es cuando se utiliza una conversión de tipos explícita.  \(Vea [Expresiones con conversiones de tipo explícitas](http://msdn.microsoft.com/es-es/060ad6b4-9592-4f3e-8509-a20ac84a85ae) para obtener más información sobre las conversiones de tipo explícitas\).  
  
 El resultado de tal conversión es un puntero al “subobjeto”, la parte del objeto que la clase base describe completamente.  
  
 En el código siguiente se definen dos clases, `A` y `B`, donde `B` se deriva de `A`.  \(Para obtener más información sobre la herencia, vea [Clases derivadas](../cpp/inheritance-cpp.md)\). A continuación, define `bObject`, un objeto de tipo `B` y dos punteros \(`pA` y `pB`\) que apuntan al objeto.  
  
```  
// conve__pluslang_Pointers_to_Classes.cpp  
// C2039 expected  
class A  
{  
public:  
    int AComponent;  
    int AMemberFunc();  
};  
  
class B : public A  
{  
public:  
    int BComponent;  
    int BMemberFunc();  
};  
int main()  
{  
   B bObject;  
   A *pA = &bObject;  
   B *pB = &bObject;  
  
   pA->AMemberFunc();   // OK in class A  
   pB->AMemberFunc();   // OK: inherited from class A  
   pA->BMemberFunc();   // Error: not in class A  
}  
```  
  
 El puntero `pA` es de tipo `A *`, los que se puede interpretar como “puntero a un objeto de tipo `A`”. Los miembros de `bObject` `(`como `BComponent` y `BMemberFunc`\) son únicos para tipo `B` y, por consiguiente, inaccesibles mediante `pA`.  El puntero `pA` solo permite el acceso a esas características \(funciones de miembro y datos\) del objeto que se definen en la clase `A`.  
  
### De puntero a función  
 Un puntero a una función puede convertirse al tipo **void \***, si el tipo **void \*** es lo bastante grande para contener ese puntero.  
  
### De puntero a void  
 Los punteros a tipo `void` se pueden convertir a punteros a cualquier otro tipo, pero solo con una conversión de tipo explícita \(a diferencia de C\).  \(Vea [Expresiones con conversiones de tipo explícitas](http://msdn.microsoft.com/es-es/060ad6b4-9592-4f3e-8509-a20ac84a85ae) para obtener más información sobre conversiones de tipo\). Un puntero a cualquier tipo se puede convertir implícitamente en un puntero a tipo `void`. Un puntero a un objeto incompleto de un tipo se puede convertir a un puntero a `void` \(implícitamente\) y viceversa \(explícitamente\).  El resultado de dicha conversión es igual al valor del puntero original.  Un objeto se considera incompleto si se declara, pero no hay suficiente información disponible para determinar su tamaño o clase base.  
  
 Un puntero a cualquier objeto que no sea **const** o `volatile` se puede convertir implícitamente en un puntero de tipo **void \***.  
  
### punteros const y volatile  
 C\+\+ no proporciona una conversión estándar de un tipo **const** o `volatile` a un tipo que no es **const** o `volatile`.  Sin embargo, se puede especificar cualquier tipo de conversión mediante conversiones de tipos explícitas \(incluidas las conversiones que no son seguras\).  
  
> [!NOTE]
>  Los punteros a miembros de C\+\+, excepto los punteros a miembros estáticos, son diferentes de los punteros normales y no tienen las mismas conversiones estándar.  Los punteros a miembros estáticos son punteros normales y tienen las mismas conversiones que los punteros normales.  \(Para más información, vea [\(NOTINBUILD\) Directly Derived Types](http://msdn.microsoft.com/es-es/d2d611d1-dbff-4fb4-9858-e1572544f5c3)\).  
  
### conversiones de puntero nulo  
 Una expresión constante entera que se evalúa como cero, o una conversión de expresión a un tipo de puntero, se convierte a un puntero denominado “puntero null”. Está garantizado que este puntero será diferente de un puntero a cualquier objeto o función válido \(a excepción de punteros a objetos basados, que pueden tener el mismo desplazamiento y seguir señalando a objetos diferentes\).  
  
 En C\+\+11, debe preferirse el tipo [nullptr](../cpp/nullptr.md) al puntero nulo de estilo C.  
  
### Conversiones de expresiones de puntero  
 Cualquier expresión con un tipo de matriz se puede convertir a un puntero del mismo tipo.  El resultado de la conversión es un puntero al primer elemento de matriz.  El ejemplo siguiente muestra este tipo de conversión:  
  
```  
char szPath[_MAX_PATH]; // Array of type char.  
char *pszPath = szPath; // Equals &szPath[0].  
```  
  
 Una expresión que da lugar a una función que devuelve un tipo determinado se convierte a un puntero a una función que devuelve ese tipo, excepto cuando:  
  
-   La expresión se usa como operando para el operador address\-of \(**&**\).  
  
-   La expresión se utiliza como operando para el operador de llamada a función.  
  
## Conversiones de referencia  
 Una referencia a una clase se puede convertir en una referencia a una clase base en los casos siguientes:  
  
-   La clase base especificada es accesible \(como se define en [Punteros a clases](../misc/pointers-to-classes.md)\).  
  
-   La conversión no es ambigua.  \(Vea [Múltiples clases base](../cpp/multiple-base-classes.md) para obtener más información sobre las referencias de clase base ambigua\).  
  
 El resultado de la conversión es un puntero al subobjeto que representa la clase base.  
  
## Puntero a miembro  
 Los punteros a miembros de clase se pueden convertir durante la asignación, la inicialización, la comparación y otras expresiones.  En esta sección se describen las siguientes conversiones de puntero a miembro:  
  
## Puntero a miembro de clase base  
 Un puntero a un miembro de una clase base se puede convertir en un puntero a un miembro de una clase derivada de esa clase base cuando se cumplen las condiciones siguientes:  
  
-   Se tiene acceso a la conversión inversa, desde el puntero a la clase derivada al puntero de la clase base.  
  
-   La clase derivada no hereda virtualmente de la clase base.  
  
 Cuando el operando izquierdo es un puntero a miembro, el operando derecho debe ser un tipo de puntero a miembro o una expresión constante que se evalúe como 0.  Esta asignación solo es válida en los casos siguientes:  
  
-   El operando derecho es un puntero a un miembro de la misma clase que el operando izquierdo.  
  
-   El operando izquierdo es un puntero a un miembro de una clase que se ha derivado de forma pública e inequívoca de la clase del operando derecho.  
  
## Conversiones de constantes integrales  
 Una expresión constante entera que se evalúa como cero se convierte a un puntero denominado "puntero null". Está garantizado que este puntero será diferente de un puntero a cualquier objeto o función válido \(a excepción de punteros a objetos basados, que pueden tener el mismo desplazamiento y seguir señalando a objetos diferentes\).  
  
 El código siguiente muestra la definición de un puntero al miembro `i` en la clase `A`.  El puntero, `pai`, se inicializa en 0, que es el puntero null.  
  
```  
// conve__pluslang_Integral_Constant_Expressions.cpp  
class A  
{  
public:  
 int i;  
};  
  
int A::*pai = 0;  
  
int main()  
{  
}  
```  
  
## Vea también  
 [Referencia de lenguaje C\+\+](../cpp/cpp-language-reference.md)