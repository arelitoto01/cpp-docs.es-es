---
title: "Constructores de movimiento y operadores de asignaci&#243;n de movimiento (C++) | Microsoft Docs"
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
  - "constructor de movimiento"
ms.assetid: e75efe0e-4b74-47a9-96ed-4e83cfc4378d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constructores de movimiento y operadores de asignaci&#243;n de movimiento (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En este tema se describe cómo escribir un *constructor de movimiento* y un operador de asignaciones de movimiento para una clase de C\+\+.  Un constructor de movimiento permite implementar semántica de movimiento, lo que puede mejorar significativamente el rendimiento de las aplicaciones.  Para obtener más información sobre la semántica de transferencia de recursos, vea [Declarador de referencia a un valor R: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Este tema se basa en la siguiente clase de C\+\+, `MemoryBlock`, que administra un búfer de memoria.  
  
```cpp  
// MemoryBlock.h  
#pragma once  
#include <iostream>  
#include <algorithm>  
  
class MemoryBlock  
{  
public:  
  
   // Simple constructor that initializes the resource.  
   explicit MemoryBlock(size_t length)  
      : _length(length)  
      , _data(new int[length])  
   {  
      std::cout << "In MemoryBlock(size_t). length = "  
                << _length << "." << std::endl;  
   }  
  
   // Destructor.  
   ~MemoryBlock()  
   {  
      std::cout << "In ~MemoryBlock(). length = "  
                << _length << ".";  
  
      if (_data != nullptr)  
      {  
         std::cout << " Deleting resource.";  
         // Delete the resource.  
         delete[] _data;  
      }  
  
      std::cout << std::endl;  
   }  
  
   // Copy constructor.  
   MemoryBlock(const MemoryBlock& other)  
      : _length(other._length)  
      , _data(new int[other._length])  
   {  
      std::cout << "In MemoryBlock(const MemoryBlock&). length = "   
                << other._length << ". Copying resource." << std::endl;  
  
      std::copy(other._data, other._data + _length, _data);  
   }  
  
   // Copy assignment operator.  
   MemoryBlock& operator=(const MemoryBlock& other)  
   {  
      std::cout << "In operator=(const MemoryBlock&). length = "   
                << other._length << ". Copying resource." << std::endl;  
  
      if (this != &other)  
      {  
         // Free the existing resource.  
         delete[] _data;  
  
         _length = other._length;  
         _data = new int[_length];  
         std::copy(other._data, other._data + _length, _data);  
      }  
      return *this;  
   }  
  
   // Retrieves the length of the data resource.  
   size_t Length() const  
   {  
      return _length;  
   }  
  
private:  
   size_t _length; // The length of the resource.  
   int* _data; // The resource.  
};  
```  
  
 Los procedimientos siguientes describen cómo escribir un constructor de movimiento y un operador de asignación de movimiento para la clase de C\+\+ de ejemplo.  
  
### Para crear un constructor de movimiento para una clase de C\+\+  
  
1.  Defina un método de constructor vacío que tome una referencia de valor R al tipo de clase como su parámetro, como se muestra en el ejemplo siguiente:  
  
    ```cpp  
    MemoryBlock(MemoryBlock&& other)  
       : _data(nullptr)  
       , _length(0)  
    {  
    }  
    ```  
  
2.  En el constructor de movimiento, asigne los miembros de datos de clase del objeto de origen al objeto que se está construyendo:  
  
    ```cpp  
    _data = other._data;  
    _length = other._length;  
    ```  
  
3.  Asigne los miembros de datos del objeto de origen a valores predeterminados.  Esto evita que el destructor libere varias veces los recursos \(tales como la memoria\):  
  
    ```cpp  
    other._data = nullptr;  
    other._length = 0;  
    ```  
  
### Para crear un operador de asignaciones de movimiento para una clase de C\+\+  
  
1.  Defina un operador de asignación vacío que tome una referencia de valor R al tipo de clase como su parámetro y devuelva una referencia al tipo de clase, como se muestra en el ejemplo siguiente:  
  
    ```cpp  
    MemoryBlock& operator=(MemoryBlock&& other)  
    {  
    }  
    ```  
  
2.  En el operador de asignación de movimiento, agregue una instrucción condicional que no realice ninguna operación si intenta asignar el objeto a sí mismo.  
  
    ```cpp  
    if (this != &other)  
    {  
    }  
    ```  
  
3.  En la instrucción condicional, libere los recursos \(tales como la memoria\) del objeto al que se asigna.  
  
     El ejemplo siguiente libera el miembro `_data` del objeto al que se asigna:  
  
    ```cpp  
    // Free the existing resource.  
    delete[] _data;  
    ```  
  
     Siga los pasos 2 y 3 del primer procedimiento para transferir los miembros de datos del objeto de origen al objeto que se construye:  
  
    ```cpp  
    // Copy the data pointer and its length from the   
    // source object.  
    _data = other._data;  
    _length = other._length;  
  
    // Release the data pointer from the source object so that  
    // the destructor does not free the memory multiple times.  
    other._data = nullptr;  
    other._length = 0;  
    ```  
  
4.  Devuelva una referencia al objeto actual, como se muestra en el ejemplo siguiente:  
  
    ```cpp  
    return *this;  
    ```  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el constructor de movimiento y el operador de asignación de movimiento completos para la clase `MemoryBlock`:  
  
```cpp  
// Move constructor.  
MemoryBlock(MemoryBlock&& other)  
   : _data(nullptr)  
   , _length(0)  
{  
   std::cout << "In MemoryBlock(MemoryBlock&&). length = "   
             << other._length << ". Moving resource." << std::endl;  
  
   // Copy the data pointer and its length from the   
   // source object.  
   _data = other._data;  
   _length = other._length;  
  
   // Release the data pointer from the source object so that  
   // the destructor does not free the memory multiple times.  
   other._data = nullptr;  
   other._length = 0;  
}  
  
// Move assignment operator.  
MemoryBlock& operator=(MemoryBlock&& other)  
{  
   std::cout << "In operator=(MemoryBlock&&). length = "   
             << other._length << "." << std::endl;  
  
   if (this != &other)  
   {  
      // Free the existing resource.  
      delete[] _data;  
  
      // Copy the data pointer and its length from the   
      // source object.  
      _data = other._data;  
      _length = other._length;  
  
      // Release the data pointer from the source object so that  
      // the destructor does not free the memory multiple times.  
      other._data = nullptr;  
      other._length = 0;  
   }  
   return *this;  
}  
```  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo la semántica de transferencia de recursos puede mejorar el rendimiento de las aplicaciones.  El ejemplo agrega dos elementos a un objeto vectorial y después inserta un nuevo elemento entre los dos existentes.  En [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], la clase `vector` usa semántica de transferencia de recursos para realizar la operación de inserción eficazmente moviendo los elementos del vector en lugar de copiarlos.  
  
```cpp  
// rvalue-references-move-semantics.cpp  
// compile with: /EHsc  
#include "MemoryBlock.h"  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
   // Create a vector object and add a few elements to it.  
   vector<MemoryBlock> v;  
   v.push_back(MemoryBlock(25));  
   v.push_back(MemoryBlock(75));  
  
   // Insert a new element into the second position of the vector.  
   v.insert(v.begin() + 1, MemoryBlock(50));  
}  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
In MemoryBlock(size_t). length = 25.  
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(size_t). length = 75.  
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(MemoryBlock&&). length = 75. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(size_t). length = 50.  
In MemoryBlock(MemoryBlock&&). length = 50. Moving resource.  
In MemoryBlock(MemoryBlock&&). length = 50. Moving resource.  
In operator=(MemoryBlock&&). length = 75.  
In operator=(MemoryBlock&&). length = 50.  
In ~MemoryBlock(). length = 0.  
In ~MemoryBlock(). length = 0.  
In ~MemoryBlock(). length = 25. Deleting resource.  
In ~MemoryBlock(). length = 50. Deleting resource.  
In ~MemoryBlock(). length = 75. Deleting resource.  
```  
  
 Antes de [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], este ejemplo genera la siguiente salida:  
  
```  
In MemoryBlock(size_t). length = 25.  
In MemoryBlock(const MemoryBlock&). length = 25. Copying resource.  
In ~MemoryBlock(). length = 25. Deleting resource.  
In MemoryBlock(size_t). length = 75.  
In MemoryBlock(const MemoryBlock&). length = 25. Copying resource.  
In ~MemoryBlock(). length = 25. Deleting resource.  
In MemoryBlock(const MemoryBlock&). length = 75. Copying resource.  
In ~MemoryBlock(). length = 75. Deleting resource.  
In MemoryBlock(size_t). length = 50.  
In MemoryBlock(const MemoryBlock&). length = 50. Copying resource.  
In MemoryBlock(const MemoryBlock&). length = 50. Copying resource.  
In operator=(const MemoryBlock&). length = 75. Copying resource.  
In operator=(const MemoryBlock&). length = 50. Copying resource.  
In ~MemoryBlock(). length = 50. Deleting resource.  
In ~MemoryBlock(). length = 50. Deleting resource.  
In ~MemoryBlock(). length = 25. Deleting resource.  
In ~MemoryBlock(). length = 50. Deleting resource.  
In ~MemoryBlock(). length = 75. Deleting resource.  
```  
  
 La versión de este ejemplo que usa semántica de movimiento de recursos es más eficiente que la versión que no la usa, porque realiza menos operaciones de copia, asignación de memoria y desasignación de memoria.  
  
## Programación eficaz  
 Para evitar pérdidas de recursos, libere siempre los recursos \(tales como memoria, identificadores de archivos y sockets\) en el operador de asignación de movimiento.  
  
 Para evitar la destrucción irrecuperable de recursos, administre correctamente la autoasignación en el operador de asignación de movimiento.  
  
 Si proporciona tanto un constructor de movimiento como un operador de asignación de movimiento para la clase, puede eliminar código redundante escribiendo el constructor de movimiento para llamar al operador de asignación de movimiento.  En el ejemplo siguiente se muestra una versión revisada del constructor de movimiento que llama al operador de asignación de movimiento:  
  
```  
// Move constructor.  
MemoryBlock(MemoryBlock&& other)  
   : _data(nullptr)  
   , _length(0)  
{  
   *this = std::move(other);  
}  
```  
  
 La función [std::move](../Topic/move.md) conserva la propiedad rvalue del parámetro `other`.  
  
## Vea también  
 [Declarador de referencia a un valor R: &&](../cpp/rvalue-reference-declarator-amp-amp.md)   
 [\<utility\> move](http://msdn.microsoft.com/es-es/abef7e85-9dd6-4724-85da-d7f7fe95dca9)