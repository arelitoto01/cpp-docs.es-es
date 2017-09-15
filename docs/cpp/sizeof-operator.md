---
title: "sizeof (Operador) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sizeof_cpp"
  - "sizeof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SIZEOF (operador)"
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# sizeof (Operador)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Genera el tamaño de su operando con respecto al tamaño de tipo `char`.  
  
> [!NOTE]
>  Para obtener más información sobre el operador `sizeof ...`, consulte [Puntos suspensivos y plantillas variádicas](../cpp/ellipses-and-variadic-templates.md).  
  
## Sintaxis  
  
```  
sizeof unary-expression sizeof  ( type-name )  
```  
  
## Comentarios  
 El resultado del operador `sizeof` es de tipo `size_t`, un tipo entero definido en el archivo de inclusión STDDEF.H.  Este operador permite no tener que especificar tamaños de datos dependientes del equipo en los programas.  
  
 El operando para `sizeof` puede ser uno de los siguientes:  
  
-   Nombre de tipo.  Para utilizar `sizeof` con un nombre de tipo, el nombre debe ir entre paréntesis.  
  
-   Una expresión.  Cuando se utiliza con una expresión, se puede especificar `sizeof` con o sin paréntesis.  La expresión no se evalúa.  
  
 Cuando el operador `sizeof` se aplica a un objeto de tipo `char`, genera 1.  Cuando el operador `sizeof` se aplica a una matriz, genera el número total de bytes de esa matriz, no el tamaño del puntero representado por el identificador de matriz.  Para obtener el tamaño del puntero representado por el identificador de matriz, páselo como parámetro a una función que utilice `sizeof`.  Por ejemplo:  
  
## Ejemplo  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## Resultados del ejemplo  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Cuando el operador `sizeof` se aplica a un tipo `class`, `struct` o `union`, el resultado es el número de bytes de un objeto de ese tipo, además del relleno que se agregue para alinear los miembros en los límites de palabra.  El resultado no corresponde necesariamente al tamaño que se calcula agregando los requisitos de almacenamiento de los miembros individuales.  La opción [\/Zp](../build/reference/zp-struct-member-alignment.md) del compilador y la directiva pragma [pack](../preprocessor/pack.md) afectan a los límites de alineación de los miembros.  
  
 El operador `sizeof` nunca genera 0, incluso para una clase vacía.  
  
 El operador `sizeof` no se puede utilizar con los operandos siguientes:  
  
-   Funciones.  \(Sin embargo, `sizeof` se puede aplicar a punteros a funciones\).  
  
-   Campos de bits.  
  
-   Clases no definidas.  
  
-   El tipo `void`.  
  
-   Matrices asignadas dinámicamente.  
  
-   Matrices externas.  
  
-   Tipos incompletos.  
  
-   Nombres entre paréntesis de tipos incompletos.  
  
 Cuando el operador `sizeof` se aplica a una referencia, el resultado es el mismo que si se hubiera aplicado `sizeof` al propio objeto.  
  
 Si una matriz sin tamaño es el último elemento de una estructura, el operador `sizeof` devuelve el tamaño de la estructura sin la matriz.  
  
 El operador `sizeof` suele utilizarse para calcular el número de elementos de una matriz mediante una expresión con este formato:  
  
```  
sizeof array / sizeof array[0]  
```  
  
## Vea también  
 [Expresiones con operadores unarios](../cpp/expressions-with-unary-operators.md)   
 [Palabras clave de C\+\+](../cpp/keywords-cpp.md)