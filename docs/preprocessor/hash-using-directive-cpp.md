---
title: "#using (Directiva) (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "friend_as_cpp"
  - "#using"
  - "friend_as"
  - "#using_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#using (directiva)"
  - "LIBPATH (variable de entorno)"
  - "preprocesador, directivas"
  - "using (directiva) (#using)"
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #using (Directiva) (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Importa metadatos en un programa compilado con [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Sintaxis  
  
```  
#using file [as_friend]  
```  
  
#### Parámetros  
 `file`  
 Archivo .dll, .exe, .netmodule u .obj de MSIL.  Por ejemplo,  
  
 `#using <MyComponent.dll>`  
  
 as\_friend  
 Especifica que todos los tipos de `file` son accesibles.  Para obtener más información, vea [Ensamblados de confianza \(C\+\+\)](../dotnet/friend-assemblies-cpp.md).  
  
## Comentarios  
 `file` puede ser un archivo del Lenguaje intermedio de Microsoft \(MSIL\) que importa para sus datos administrados y construcciones administradas.  Si un archivo .dll contiene un manifiesto del ensamblado, se importan todos los archivos .dll a los que se hace referencia en el manifiesto y el ensamblado que está compilando muestra *file* en los metadatos como una referencia de ensamblado.  
  
 Si `file` no contiene un ensamblado \(si `file` es un módulo\) y no piensa utilizar información de tipos del módulo de la aplicación \(ensamblado\) actual, tiene la posibilidad de indicar únicamente que el módulo forma parte el ensamblado; use [\/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  Los tipos del módulo estarán disponibles entonces para cualquier aplicación que hiciera referencia al ensamblado.  
  
 Una alternativa al uso de `#using` es la opción [\/FU](../build/reference/fu-name-forced-hash-using-file.md) del compilador.  
  
 Los ensamblados .exe pasados a `#using` deben compilarse con **\/clr:safe** o **\/clr:pure**, o con cualquiera de los demás compiladores de Visual Studio \(Visual Basic o Visual C\#, por ejemplo\).  Si se intenta importar metadatos de un ensamblado .exe compilado con **\/clr**, se producirá una excepción de carga del archivo.  
  
> [!NOTE]
>  Un componente al que se hace referencia con `#using` puede ejecutarse con una versión diferente del archivo importado en tiempo de compilación, lo que hace que una aplicación cliente proporcione resultados inesperados.  
  
 Para que el compilador reconozca un tipo de un ensamblado \(no de un módulo\), debe obligársele a que resuelva el tipo, lo que se puede conseguir por ejemplo si se define una instancia del tipo.  Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si se hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo.  
  
 Cuando se importan metadatos compilados a partir de código fuente que utilizó [\_\_declspec\(thread\)](../cpp/thread.md), la semántica de subproceso no se conserva en los metadatos.  Por ejemplo, una variable declarada con **\_\_declspec\(thread\)**, compilada en un programa compilado para Common Language Runtime de .NET Framework, e importada después mediante `#using`, carecerá de semántica **\_\_declspec\(thread\)**.  
  
 Todos los tipos importados \(tanto administrados como nativos\) en un archivo al que hace referencia `#using` están disponibles, pero el compilador trata los tipos nativos como declaraciones, no como definiciones.  
  
 Se hace referencia automáticamente a mscorlib.dll cuando se compila con **\/clr**.  
  
 La variable de entorno LIBPATH especifica los directorios en los que se busca cuando el compilador intenta resolver los nombres de archivo pasados a `#using`.  
  
 El compilador buscará las referencias en la ruta de acceso siguiente:  
  
-   Una ruta de acceso especificada en la instrucción `#using`.  
  
-   El directorio actual.  
  
-   El directorio del sistema de .NET Framework.  
  
-   Directorios agregados con la opción [\/AI](../build/reference/ai-specify-metadata-directories.md) del compilador.  
  
-   Directorios de la variable de entorno LIBPATH.  
  
## Ejemplo  
 Si compila un ensamblado \(C\) y hace referencia a un ensamblado \(B\) que a su vez hace referencia a otro ensamblado \(A\), no tendrá que hacer referencia explícitamente al ensamblado A menos que emplee explícitamente uno de los tipos de A en C.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## Ejemplo  
  
```  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};  
  
```  
  
## Ejemplo  
 En el ejemplo siguiente, no hay ningún error del compilador por no hacer referencia a using\_assembly\_A.dll porque el programa no utiliza ninguno de los tipos definidos en using\_assembly\_A.cpp.  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## Vea también  
 [Directivas de preprocesador](../preprocessor/preprocessor-directives.md)