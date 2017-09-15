---
title: "Sintaxis de las expresiones lambda | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "VCF1 Lambda_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expresiones lambda [C++], sintaxis"
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# Sintaxis de las expresiones lambda
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En este artículo se demuestra la sintaxis y los elementos estructurales de las expresiones lambda.  Para obtener una descripción de las expresiones lambda, vea [Expresiones lambda](../cpp/lambda-expressions-in-cpp.md).  
  
## Objetos de función frente a expresionesLambdas  
 Cuando escribe código, probablemente utiliza punteros a función y objetos de función para resolver problemas y realizar cálculos, sobre todo cuando se usan [Algoritmos de STL](../cpp/algorithms-modern-cpp.md).  Tanto los punteros a función como los objetos de función tienen ventajas y desventajas; por ejemplo, los punteros a función tienen una sobrecarga sintáctica mínima pero no conservan el estado dentro de un ámbito, y los objetos de función pueden conservar el estado pero requieren la sobrecarga sintáctica de una definición de clase.  
  
 Una expresión lambda combina las ventajas de los punteros a función y los objetos de función y evita sus desventajas.  Como los objetos de función, una expresión lambda es flexible y puede conservar el estado, pero, a diferencia de un objeto de función, su sintaxis compacta no requiere una definición de clase explícita.  Mediante expresiones lambda, se puede escribir código menos complejo y menos propenso a errores que el código para un objeto de función equivalente.  
  
 En los ejemplos siguientes se compara el uso de una expresión lambda con el uso de un objeto de función.  En el primer ejemplo se utiliza una expresión lambda para imprimir en la consola si cada elemento de un objeto `vector` es par o impar.  En el segundo ejemplo se usa un objeto de función para realizar la misma tarea.  
  
## Ejemplo 1: utilizar una expresión lambda  
 En este ejemplo se pasa una expresión lambda a la función `for_each`.  La expresión lambda imprime un resultado que indica si cada elemento de un objeto `vector` es par o impar.  
  
### Código  
  
```cpp  
// even_lambda.cpp  
// compile with: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
   // Create a vector object that contains 10 elements.  
   vector<int> v;  
   for (int i = 1; i < 10; ++i) {  
      v.push_back(i);  
   }  
  
   // Count the number of even numbers in the vector by   
   // using the for_each function and a lambda.  
   int evenCount = 0;  
   for_each(v.begin(), v.end(), [&evenCount] (int n) {  
      cout << n;  
      if (n % 2 == 0) {  
         cout << " is even " << endl;  
         ++evenCount;  
      } else {  
         cout << " is odd " << endl;  
      }  
   });  
  
   // Print the count of even numbers to the console.  
   cout << "There are " << evenCount   
        << " even numbers in the vector." << endl;  
}  
```  
  
### Salida  
  **1 es impar**  
**2 es par**  
**3 es impar**  
**4 es par**  
**5 es impar**  
**6 es par**  
**7 es impar**  
**8 es par**  
**9 es impar**  
**Hay 4 números pares en el vector.**   
### Comentarios  
 En el ejemplo, el tercer argumento de la función `for_each` es una expresión lambda.  La parte `[&evenCount]` especifica la cláusula capture de la expresión, `(int n)` especifica la lista de parámetros y la parte restante especifica el cuerpo de la expresión.  
  
## Ejemplo 2: utilizar un objeto de función  
 En ocasiones, una expresión lambda sería demasiado difícil de extender mucho más allá del ejemplo anterior.  En el ejemplo siguiente se utiliza un objeto de función en lugar de una expresión lambda, junto con la función `for_each`, para generar los mismos resultados que en el ejemplo 1.  Ambos ejemplos almacenan el recuento de números pares en un objeto `vector`.  Para mantener el estado de la operación, la clase `FunctorClass` almacena la variable `m_evenCount` por referencia como una variable miembro.  Para realizar la operación, `FunctorClass` implementa el operador de llamada a función, `operator()`.  El compilador de Visual C\+\+ genera código que es comparable en cuanto a tamaño y rendimiento al código con una expresión lambda del ejemplo 1.  Si se trata de un problema básico como el de este artículo, probablemente el diseño lambda más simple sea mejor que el diseño de objeto de función.  Sin embargo, si cree que la funcionalidad puede requerir una extensión importante en el futuro, utilice el diseño de objeto de función para que el mantenimiento del código sea más sencillo.  
  
 Para obtener más información sobre `operator()`, vea [Llamada de función](../cpp/function-call-cpp.md).  Para obtener más información sobre la función `for_each`, vea [for\_each](../Topic/for_each.md).  
  
### Código  
  
```cpp  
// even_functor.cpp  
// compile with: /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class FunctorClass  
{  
public:  
    // The required constructor for this example.  
    explicit FunctorClass(int& evenCount)  
        : m_evenCount(evenCount) { }  
  
    // The function-call operator prints whether the number is  
    // even or odd. If the number is even, this method updates  
    // the counter.  
    void operator()(int n) const {  
        cout << n;  
  
        if (n % 2 == 0) {  
            cout << " is even " << endl;  
            ++m_evenCount;  
        } else {  
            cout << " is odd " << endl;  
        }  
    }  
  
private:  
    // Default assignment operator to silence warning C4512.  
    FunctorClass& operator=(const FunctorClass&);  
  
    int& m_evenCount; // the number of even variables in the vector.  
};  
  
int main()  
{  
    // Create a vector object that contains 10 elements.  
    vector<int> v;  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
  
    // Count the number of even numbers in the vector by   
    // using the for_each function and a function object.  
    int evenCount = 0;  
    for_each(v.begin(), v.end(), FunctorClass(evenCount));  
  
    // Print the count of even numbers to the console.  
    cout << "There are " << evenCount  
        << " even numbers in the vector." << endl;  
}  
  
```  
  
## Salida  
  **1 es impar**  
**2 es par**  
**3 es impar**  
**4 es par**  
**5 es impar**  
**6 es par**  
**7 es impar**  
**8 es par**  
**9 es impar**  
**Hay 4 números pares en el vector.**   
## Vea también  
 [Expresiones lambda](../cpp/lambda-expressions-in-cpp.md)   
 [Ejemplos de expresiones lambda](../cpp/examples-of-lambda-expressions.md)   
 [generar](../Topic/generate.md)   
 [generate\_n](../Topic/generate_n.md)   
 [for\_each](../Topic/for_each.md)   
 [Especificaciones de excepciones \(throw\)](../cpp/exception-specifications-throw-cpp.md)   
 [Advertencia del compilador \(nivel 1\) C4297](../Topic/Compiler%20Warning%20\(level%201\)%20C4297.md)   
 [Modificadores específicos de Microsoft](../cpp/microsoft-specific-modifiers.md)