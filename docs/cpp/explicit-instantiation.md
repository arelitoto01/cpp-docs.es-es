---
title: "Creaci&#243;n de instancias expl&#237;cita | Microsoft Docs"
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
  - "plantillas, creación de instancias"
  - "creación de instancias explícita"
  - "creación de instancias, explícita"
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Creaci&#243;n de instancias expl&#237;cita
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Puede utilizar la creación de instancias explícita para crear una instancia de una clase o una función con plantilla sin usarla realmente en el código.  Como esto es útil cuando se crean archivos de biblioteca \(.lib\) que utilizan plantillas para la distribución, las definiciones de plantillas sin instancias no se colocan en archivos objeto \(.obj\).  
  
 Este código crea explícitamente instancias de `MyStack` para las variables `int` y seis elementos:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Esta instrucción crea una instancia de `MyStack` sin reservar ningún almacenamiento para un objeto.  Se genera el código para todos los miembros.  
  
 La línea siguiente crea explícitamente instancias solo de la función miembro de constructor:  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Puede crear explícitamente instancias de plantillas de función con un argumento de tipo específico para volver a declararlas, como se muestra en el ejemplo de [Crear instancias de plantillas de función](../cpp/function-template-instantiation.md).  
  
 Puede utilizar la palabra clave `extern` para impedir la creación automática de instancias de miembros.  Por ejemplo:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 Del mismo modo, puede marcar determinados miembros como externos y no crear instancias de ellos:  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Puede utilizar la palabra clave `extern` para impedir que el compilador genere el mismo código de creación de instancias en más de un módulo de objeto.  Para crear instancias de la función de plantilla se deben utilizar los parámetros de plantilla explícitos especificados en al menos un módulo vinculado si se llama a la función; de lo contrario, se producirá un error del vinculador cuando se compile el programa.  
  
> [!NOTE]
>  La palabra clave `extern` en la especialización solo se aplica a las funciones miembro definidas fuera del cuerpo de la clase.  Las funciones definidas dentro de la declaración de clase se consideran funciones insertadas y siempre se crean instancias de ellas.  
  
## Vea también  
 [Plantillas de función](../cpp/function-templates.md)