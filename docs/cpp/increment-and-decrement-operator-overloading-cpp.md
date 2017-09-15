---
title: "Sobrecarga de operadores de incremento y decremento (C++) | Microsoft Docs"
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
helpviewer_keywords: 
  - "operadores de decremento"
  - "operadores de decremento, tipos de"
  - "operadores de incremento"
  - "operadores de incremento, tipos de"
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sobrecarga de operadores de incremento y decremento (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Los operadores de incremento y decremento pertenecen a una categoría especial porque hay dos variantes de cada uno de ellos:  
  
-   Preincremento y postincremento  
  
-   Predecremento y postdecremento  
  
 Cuando escriba funciones de operador sobrecargadas, puede resultarle útil implementar versiones distintas para las versiones de prefijo y de postfijo de estos operadores.  Para distinguirlas, se aplica la regla siguiente: la forma de prefijo del operador se declara exactamente del mismo modo que cualquier otro operador unario; la forma de postfijo acepta un argumento adicional de tipo `int`.  
  
> [!NOTE]
>  Cuando se especifica un operador sobrecargado para la forma del operador de incremento o decremento, el argumento adicional debe ser de tipo `int`; la especificación de cualquier otro tipo genera un error.  
  
 En el ejemplo siguiente se muestra cómo definir operadores de incremento y decremento de prefijo y de postfijo para la clase `Point`:  
  
```  
// increment_and_decrement1.cpp  
class Point  
{  
public:  
   // Declare prefix and postfix increment operators.  
   Point& operator++();       // Prefix increment operator.  
   Point operator++(int);     // Postfix increment operator.  
  
   // Declare prefix and postfix decrement operators.  
   Point& operator--();       // Prefix decrement operator.  
   Point operator--(int);     // Postfix decrement operator.  
  
   // Define default constructor.  
   Point() { _x = _y = 0; }  
  
   // Define accessor functions.  
   int x() { return _x; }  
   int y() { return _y; }  
private:  
   int _x, _y;  
};  
  
// Define prefix increment operator.  
Point& Point::operator++()  
{  
   _x++;  
   _y++;  
   return *this;  
}  
  
// Define postfix increment operator.  
Point Point::operator++(int)  
{  
   Point temp = *this;  
   ++*this;  
   return temp;  
}  
  
// Define prefix decrement operator.  
Point& Point::operator--()  
{  
   _x--;  
   _y--;  
   return *this;  
}  
  
// Define postfix decrement operator.  
Point Point::operator--(int)  
{  
   Point temp = *this;  
   --*this;  
   return temp;  
}  
int main()  
{  
}  
```  
  
 Pueden definirse los mismos operadores en el ámbito de archivo \(global\) mediante los siguientes encabezados de función:  
  
```  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 El argumento de tipo `int` que designa la forma de postfijo del operador de incremento o decremento no suele utilizarse para pasar argumentos.  Normalmente contiene el valor 0.  Sin embargo, se puede utilizar del modo siguiente:  
  
```  
// increment_and_decrement2.cpp  
class Int  
{  
public:  
    Int &operator++( int n );  
private:  
    int _i;  
};  
  
Int& Int::operator++( int n )  
{  
    if( n != 0 )    // Handle case where an argument is passed.  
        _i += n;  
    else  
        _i++;       // Handle case where no argument is passed.  
    return *this;  
}  
int main()  
{  
   Int i;  
   i.operator++( 25 ); // Increment by 25.  
}  
```  
  
 No hay ninguna sintaxis para usar los operadores de incremento y decremento para pasar estos valores que no sea la invocación explícita, como se muestra en el código anterior.  Una manera más sencilla de implementar esta funcionalidad es sobrecargar el operador de suma\/asignación \(`+=`\).  
  
## Vea también  
 [Sobrecarga de operadores](../cpp/operator-overloading.md)