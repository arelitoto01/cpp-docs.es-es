---
title: "Conceptos b&#225;sicos de ODBC | Microsoft Docs"
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
  - "componentes de ODBC"
  - "componentes de ODBC, componentes obligatorios"
  - "biblioteca de cursores ODBC [ODBC], componentes de ODBC"
  - "ODBC, acerca de ODBC"
  - "ODBC, componentes"
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Conceptos b&#225;sicos de ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Este tema proporciona los conceptos básicos de la conectividad abierta de bases de datos \(ODBC\):  
  
-   [Cómo trabaja ODBC con las clases de base de datos.](../../data/odbc/odbc-and-the-database-classes.md)  
  
-   [Cómo trabajan los controladores ODBC con conjuntos de registros dinámicos.](../../data/odbc/odbc-driver-requirements-for-dynasets.md)  
  
-   [Componentes de ODBC necesarios para redistribuir con las aplicaciones](../../data/odbc/redistributing-odbc-components-to-your-customers.md)  
  
 También conviene leer el tema relacionado [ODBC: Biblioteca de cursores ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Mediante las clases ODBC de MFC, como se describe en este tema, o las clases DAO de MFC se puede tener acceso a los orígenes de datos ODBC.  
  
> [!NOTE]
>  Las clases ODBC de MFC son compatibles con Unicode y multithreading.  Para obtener más información sobre la compatibilidad con multithreading, vea [Clases y subprocesos de ODBC](../../data/odbc/odbc-classes-and-threads.md)  
  
 ODBC es una interfaz de nivel de llamada que permite que las aplicaciones tengan acceso a los datos de cualquier base de datos en la que haya un controlador ODBC.  La utilización de ODBC permite crear aplicaciones de base de datos con acceso a cualquier base de datos en la que el usuario final tenga un controlador ODBC.  ODBC proporciona una API que permite que la aplicación sea independiente del sistema de administración de bases de datos \(DBMS\) de origen.  
  
 ODBC es la parte de base de datos de la Arquitectura de servicios abiertos de Microsoft Windows \(WOSA\), una interfaz que permite que las aplicaciones de escritorio basadas en Windows se conecten a varios entornos de computación sin tener que volver a crear la aplicación para cada plataforma.  
  
 A continuación se incluyen componentes de ODBC:  
  
-   API de ODBC  
  
     Biblioteca de llamadas a funciones, conjunto de códigos de error y sintaxis de [SQL](../../data/odbc/sql.md) estándar para tener acceso a los datos de los DBMS.  
  
-   Administrador de controladores ODBC  
  
     Biblioteca de vínculos dinámicos \(Odbc32.dll\) que carga controladores de bases de datos ODBC en nombre de una aplicación.  Esta DLL es transparente a la aplicación.  
  
-   Controladores de bases de datos ODBC  
  
     Biblioteca o bibliotecas DLL que procesan llamadas a funciones ODBC para DBMS específicos.  Para obtener una lista de los controladores proporcionados, vea [Lista de controladores ODBC](../../data/odbc/odbc-driver-list.md).  
  
-   [Biblioteca de cursores ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
     Biblioteca de vínculos dinámicos \(Odbccr32.dll\) que se encuentra entre el Administrador de controladores ODBC y los controladores, y que controla el desplazamiento por los datos.  
  
-   [Administrador de ODBC](../../data/odbc/odbc-administrator.md)  
  
     Herramienta utilizada para configurar un DBMS de modo que quede disponible como origen de datos de una aplicación.  
  
 Para que una aplicación sea independiente de los DBMS tiene que trabajar a través de un controlador ODBC creado específicamente para un DBMS, en lugar de trabajar directamente con el DBMS.  El controlador convierte las llamadas en comandos que el DBMS correspondiente puede utilizar, con lo que se simplifica el trabajo del desarrollador, y hace que esté disponible para una amplia gama de orígenes de datos.  
  
 Las clases de base de datos admiten cualquier origen de datos para el que se tenga un controlador ODBC.  Entre ellos se puede incluir, por ejemplo, una base de datos relacional, una base de datos de método de acceso secuencial indizado \(ISAM\), una hoja de cálculo de Microsoft Excel o un archivo de texto.  Los controladores ODBC administran las conexiones al origen de datos y se utiliza SQL para seleccionar los registros de la base de datos.  
  
 Vea [Lista de controladores ODBC](../../data/odbc/odbc-driver-list.md) para obtener una lista de los controladores ODBC incluidos en esta versión de Visual C\+\+ e información sobre cómo obtener controladores adicionales.  
  
## Vea también  
 [Conectividad abierta de bases de datos \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)