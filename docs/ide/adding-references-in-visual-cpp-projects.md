---
title: "Agregar referencias en proyectos de Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.References"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework (C++), Agregar referencias (cuadro de diálogo)"
  - "Agregar referencias (cuadro de diálogo) (C++)"
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Agregar referencias en proyectos de Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es muy común que los programas llamen a las API de otros archivos binarios como, por ejemplo, los archivos DLL, los componentes en tiempo de ejecución de Windows, los SDK de extensiones, los componentes COM y los ensamblados .NET. La forma en que el programa busca esos otros archivos binarios depende tanto del tipo de proyecto como del tipo de binario.  
  
 En un proyecto de C\+\+ nativo, si consume un componente DLL o COM nativo que no se está generando en otro proyecto de la solución, usa LoadLibrary o CoCreateInstance para especificar la ruta de acceso del archivo binario, o bien permite que el sistema la busque mediante una búsqueda en determinadas ubicaciones bien definidas.  
  
 En otros tipos de proyecto, como los de UWP o C\+\+\/CLI, o cuando el binario se genera en otro proyecto en la solución, agrega una *referencia* al ensamblado, el componente o el proyecto.   Básicamente, una referencia es un conjunto de datos que permite que el programa busque y se comunique con el binario.       Cuando se agrega una referencia, Visual Studio controla los detalles de nivel bajo. Para establecer referencias de un proyecto de C\+\+ a ensamblados de [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] \(solo en C\+\+\/CLI\), componentes COM, otros proyectos de la solución \(incluidos los proyectos compartidos\) o servicios asociados, haga clic con el botón derecho en el nodo **Referencias** en el **Explorador de soluciones** para que se muestre el **Administrador de referencias**. Lo que se muestra en el Administrador de referencias varía en función del tipo de proyecto.  
  
 En un proyecto de C\+\+ nativo \(ATL\) el concepto de *referencias* solo se aplica a otros proyectos de la solución, incluidos los proyectos compartidos, de modo que eso es todo lo que muestra en **Administrador de referencias**:  
  
 ![Administrador de referencias de Visual C&#43;&#43; &#40;proyectos ATL&#41;](../Image/Visual%20C++%20Reference%20Manager%20\(ATL%20Projects\).png "Visual C\+\+ Reference Manager \(ATL Projects\)")  
  
 En un proyecto de C\+\+\/CLI o de Plataforma universal de Windows, el concepto de referencias se aplica a más tipos de binarios además de a otros proyectos de la solución.  Todos ellos se exponen en **Administrador de referencias**:  
  
 ![Administrador de referencias de Visual C&#43;&#43; para proyectos de C&#43;&#43;&#47;CLI](../Image/Visual%20C++%20Reference%20Manager%20for%20C++/CLI%20projects.png "Visual C\+\+ Reference Manager for C\+\+\/CLI projects")  
  
## Propiedades de referencia  
 Cada tipo de referencia tiene propiedades. Para ver las propiedades, seleccione la referencia en el Explorador de soluciones y presione **Alt \+ Entrar**, o bien haga clic con el botón derecho y elija **Propiedades**. Algunas propiedades son de solo lectura y algunas pueden modificarse. Sin embargo, normalmente estas propiedades no deben modificarse de forma manual.  
  
### Propiedades de referencias de ActiveX  
 Las propiedades de referencias de ActiveX solo están disponibles para las referencias a componentes COM. Estas propiedades solo se muestran cuando se selecciona un componente COM en el panel **Referencias**. No se pueden modificar las propiedades.  
  
 **Ruta de acceso de control**  
 Muestra la ruta de acceso del directorio del control al que se hace referencia.  
  
 **GUID de control**  
 Muestra el GUID del control ActiveX.  
  
 **Versión de control**  
 Muestra la versión del control ActiveX al que se hace referencia.  
  
 **Nombre de biblioteca de tipos**  
 Muestra el nombre de la biblioteca de tipos a la que se hace referencia.  
  
 **Herramienta de contenedor**  
 Muestra la herramienta que se utiliza para compilar el ensamblado de interoperabilidad desde el control ActiveX o la biblioteca COM a los que se hace referencia.  
  
### Propiedades de la referencia de ensamblado  
 Las propiedades de referencias de ensamblados solo están disponibles para referencias a ensamblados [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] en proyectos de C\+\+\/CLI. Estas propiedades solo se muestran cuando se selecciona un ensamblado [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] en el panel **Referencias**. No se pueden modificar las propiedades.  
  
 **Ruta relativa**  
 Muestra la ruta de acceso relativa desde el directorio del proyecto hasta el ensamblado al que se hace referencia.  
  
### Propiedades de compilación  
 Las propiedades siguientes están disponibles en diversos tipos de referencia. Estas propiedades permiten especificar cómo compilar con referencias.  
  
 **Copia local**  
 Especifica si se debe copiar automáticamente el ensamblado al que se hace referencia en la ubicación de destino durante una compilación.  
  
 **Copiar ensamblados satélite locales**  
 Especifica si se deben copiar automáticamente los ensamblados satélite del ensamblado al que se hace referencia en la ubicación de destino durante una compilación. Solo se utiliza si **Copia local** es `true`.  
  
 **Salida de ensamblado de referencia**  
 Especifica que este ensamblado se usa en el proceso de compilación. Si es `true`, el ensamblado se agregará a la línea de comandos del compilador durante la compilación  
  
### Propiedades de referencia de proyecto a proyecto  
 Las siguientes propiedades definen una *referencia de proyecto a proyecto* del proyecto que está seleccionado en el panel **Referencias** a otro proyecto en la misma solución. Para obtener más información, vea [Administrar referencias en un proyecto](../Topic/Managing%20references%20in%20a%20project.md).  
  
 **Dependencias de la biblioteca de vínculos**  
 Cuando esta propiedad es **True**, el sistema de proyectos vincula dentro del proyecto dependiente los archivos .lib generados por el proyecto independiente. Por lo general, usted especificará **True**.  
  
 **Identificador del proyecto**  
 Identifica de forma única el proyecto independiente. El valor de propiedad es un GUID de sistema interno que no se puede modificar.  
  
 **Usar entradas de dependencia de biblioteca**  
 Cuando esta propiedad es **False**, el sistema de proyectos no vincula dentro del proyecto dependiente los archivos .obj de la biblioteca generada por el proyecto independiente. Por lo tanto, este valor deshabilita la vinculación incremental. Normalmente especificará **False**, porque compilar la aplicación puede tardar mucho tiempo si hay muchos proyectos independientes.  
  
### Propiedades de referencia  
 Las siguientes propiedades se encuentran en las referencias de ensamblado de .NET y COM y no se puede modificar.  
  
 **Nombre del ensamblado**  
 Muestra el nombre del ensamblado al que se hace referencia.  
  
 **Referencia cultural**  
 Muestra la referencia cultural de la referencia seleccionada.  
  
 **Descripción**  
 Muestra la descripción de la referencia seleccionada.  
  
 **Ruta de acceso completa**  
 Muestra la ruta de acceso del directorio del ensamblado al que se hace referencia.  
  
 **Identidad**  
 Para los ensamblados [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)], muestra la ruta de acceso completa. Para los componentes COM, muestra el GUID.  
  
 **Etiqueta**  
 Muestra la etiqueta de la referencia.  
  
 **Nombre**  
 Muestra el nombre de la referencia.  
  
 **Token de clave pública**  
 Muestra el token de clave pública que se utiliza para identificar el ensamblado al que se hace referencia.  
  
 **Nombre seguro**  
 `true` si el ensamblado al que se hace referencia tiene un nombre seguro. Un ensamblado con nombre seguro tiene una única versión.  
  
 **Versión**  
 Muestra la versión del ensamblado al que se hace referencia.  
  
## Vea también  
 [Páginas de propiedades](../ide/property-pages-visual-cpp.md)   
 [Cómo: Abrir páginas de propiedades del proyecto](../misc/how-to-open-project-property-pages.md)