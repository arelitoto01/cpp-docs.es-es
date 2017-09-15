---
title: "Personalizar el procesamiento de línea de comandos de C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: fd7217a12616fca234ed1fcd8a3c31f0b46a1ba0
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="customizing-c-command-line-processing"></a>Personalizar el procesamiento de línea de comandos de C
Si el programa no acepta argumentos de línea de comandos, puede guardar una pequeña cantidad de espacio suprimiendo el uso de la rutina de biblioteca que realiza el procesamiento de la línea de comandos. Esta rutina se denomina **_setargv**, o **_wsetargv** en el entorno de caracteres anchos, como se describe en [Expansión de argumentos comodín](../c-language/expanding-wildcard-arguments.md). Para suprimir su uso, defina una rutina que no haga nada en el archivo que contiene la función **main** y denomínela **_setargv**, o **_wsetargv** en el entorno de caracteres anchos. La llamada a **_setargv** o **_wsetargv** se satisface mediante la definición de **_setargv** o **_wsetargv** y no se carga la versión de la biblioteca.  
  
 De igual forma, si nunca accede a la tabla de entorno mediante el argumento `envp`, puede proporcionar una rutina vacía propia que se utilizará en lugar de **_setenvp** o **_wsetenvp**, la rutina de procesamiento de entorno.  
  
 Si el programa realiza llamadas a la familia de rutinas **_spawn** o **_exec** de la biblioteca en tiempo de ejecución de C, no debe suprimir la rutina de procesamiento de entorno, puesto que esta rutina se utiliza para pasar un entorno desde el proceso de generación al nuevo proceso.  
  
## <a name="see-also"></a>Vea también  
 [Función main y ejecución del programa](../c-language/main-function-and-program-execution.md)