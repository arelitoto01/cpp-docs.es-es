---
title: "Nombres representativos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nombres representativos, definición"
  - "decoración de nombres [C++]"
  - "nombres [C++], representativos"
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Nombres representativos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Las funciones, los datos y los objetos de los programas C y C\+\+ se representan internamente con sus nombres representativos.  Un *nombre representativo* \(también llamado nombre decorado\) es una cadena codificada creada por el compilador durante la compilación de una definición de función, datos u objeto.  Registra las convenciones de llamada, los tipos, los parámetros de función y otra información junto con el nombre.  Esta representación, decoración, modificación o marcado del nombre, también conocida como *name mangling*, facilita que el enlazador encuentre las funciones y los objetos correctos al vincular un ejecutable.  
  
 Las convenciones de nomenclatura decorada han cambiado en varias versiones de Visual C\+\+ y también pueden ser diferentes en arquitecturas de destino distintas.  Para vincular correctamente con los archivos de origen creados con Visual C\+\+, las bibliotecas y los archivos DLL de C\+\+ y C se deben compilar con el mismo conjunto de herramientas del compilador, las mismas marcas y la misma arquitectura de destino.  
  
 **Contenido**  
  
-   [Utilizar nombres representativos](#Using)  
  
-   [Formato de un nombre representativo de C\+\+](#Format)  
  
-   [Formato de un nombre representativo de C](#FormatC)  
  
-   [Ver nombres representativos](#Viewing)  
  
-   [Ver nombres no representativos](#Undecorated)  
  
##  <a name="Using"></a> Utilizar nombres representativos  
 Normalmente, no es necesario saber el nombre representativo para escribir código que se compile y se vincule correctamente.  Los nombres representativos son un detalle de implementación interno del compilador y el enlazador.  En general, las herramientas tratan el nombre en su formato no representativo.  Sin embargo, a veces es necesario un nombre representativo cuando se especifica un nombre de función para el enlazador y otras herramientas.  Por ejemplo, para que coincida con funciones de C\+\+ sobrecargadas, miembros de espacios de nombres, constructores de clase, destructores y funciones de miembro especiales, se debe especificar el nombre representativo.  Para obtener más información sobre las marcas de opción y otras situaciones que necesitan nombres representativos, vea la documentación de las herramientas y opciones que esté usando.  
  
 Si cambia el nombre de la función, la clase, la convención de llamada, el tipo de valor devuelto o cualquier otro parámetro, también cambia el nombre representativo.  En este caso, debe obtener el nuevo nombre representativo y usarlo en lugar del nombre anterior en todos los lugares en los que se haya especificado.  
  
 La decoración de nombres también es importante cuando se vincula a código escrito en otros lenguajes de programación o con otros compiladores.  Diferentes compiladores usan convenciones de decoración de nombres distintas.  Cuando se vincula una aplicación ejecutable con el código escrito en otro idioma, se debe tener especial cuidado para que los nombres importados y exportados y las convenciones de llamada coincidan.  El código de lenguaje de ensamblado debe usar nombres representativos de Visual C\+\+ y convenciones de llamada para vincular al código fuente escrito en Visual C\+\+.  
  
##  <a name="Format"></a> Formato de un nombre representativo de C\+\+  
 El nombre representativo para una función de C\+\+ contiene la información siguiente:  
  
-   Nombre de la función.  
  
-   Clase de la que la función es miembro, si se trata de una función miembro.  Esto puede incluir la clase que contiene la clase que contiene la función y así sucesivamente.  
  
-   Espacio de nombres al que pertenece la función, si forma parte de un espacio de nombres.  
  
-   Tipos de los parámetros de las funciones.  
  
-   Convención de llamada.  
  
-   Tipo de valor devuelto de la función.  
  
 Los nombres de función y de clase están codificados en el nombre representativo.  El resto del nombre representativo es un código que tiene significado interno solo para el compilador y el enlazador.  Aquí tiene algunos ejemplos de nombres de C\+\+ representativo y no representativo.  
  
|Nombre no representativo|Nombre representativo|  
|------------------------------|---------------------------|  
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|  
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|  
  
##  <a name="FormatC"></a> Formato de un nombre representativo de C  
 El formato de decoración para una función de C depende de la convención de llamada usada en su declaración, tal como se muestra en la tabla siguiente.  Este también es el formato de decoración que se usa cuando el código de C\+\+ se declara para que contenga vinculación de `extern "C"`.  La convención de llamada predeterminada es `__cdecl`.  Tenga en cuenta que en un entorno de 64 bits, las funciones no se decoran.  
  
|Convención de llamada|Decoración|  
|---------------------------|----------------|  
|`__cdecl`|Carácter de subrayado inicial \(**\_**\)|  
|`__stdcall`|Carácter de subrayado inicial \(**\_**\) y el símbolo de arroba \(@\) al final seguido del número de bytes de la lista de parámetros en formato decimal|  
|`__fastcall`|Símbolo de arroba \(@\) al principio y al final seguidos por un número decimal que representa el número de bytes de la lista de parámetros|  
|`__vectorcall`|Dos símbolos de arroba \(@@\) al final seguidos por un número decimal de bytes de la lista de parámetros|  
  
##  <a name="Viewing"></a> Ver nombres representativos  
 Puede obtener el formato representativo del nombre de un símbolo después de compilar el archivo de origen que contiene el prototipo o la definición de la función, los datos o el objeto.  Para examinar los nombres representativos del programa, puede usar uno de los métodos siguientes:  
  
-   #### Para usar una lista para ver nombres representativos  
  
    1.  Genere una lista compilando el archivo de origen que contiene el prototipo o la definición de la función, los datos o el objeto con la opción del compilador [Tipo de archivo de lista](../../build/reference/fa-fa-listing-file.md) establecida en Ensamblado con código fuente \(**\/FAs**\).  
  
         Por ejemplo, escriba `cl /c /FAS example.cpp` en un símbolo del sistema para desarrolladores para generar un archivo de lista example.asm.  
  
    2.  En el archivo de lista resultante, busque la línea que empieza por PUBLIC y termina con un punto y coma seguido del nombre no representativo de la función o los datos.  El símbolo situado entre PUBLIC y el punto y coma es el nombre representativo.  
  
-   #### Para usar DUMPBIN para ver nombres representativos  
  
    1.  Para ver los símbolos exportados de un archivo .obj o .lib, escriba `dumpbin /symbols` `objfile` en un símbolo del sistema para desarrolladores.  
  
    2.  Para encontrar el formato representativo de un símbolo, busque el nombre no representativo entre paréntesis.  El nombre representativo está en la misma línea, después de un carácter de barra vertical \(&#124;\) y delante del nombre no representativo.  
  
##  <a name="Undecorated"></a> Ver nombres no representativos  
 Puede usar undname.exe para convertir un nombre representativo a su formato no representativo.  En este ejemplo se muestra cómo funciona:  
  
```  
C:\>undname ?func1@a@@AAEXH@Z  
Microsoft (R) C++ Name Undecorator  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
Undecoration of :- "?func1@a@@AAEXH@Z"  
is :- "private: void __thiscall a::func1(int)"  
  
```  
  
## Vea también  
 [Herramientas de compilación de C\/C\+\+](../../build/reference/c-cpp-build-tools.md)   
 [Usar extern para especificar la vinculación](../../cpp/using-extern-to-specify-linkage.md)