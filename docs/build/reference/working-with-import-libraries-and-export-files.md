---
title: Trabajar con bibliotecas de importación y archivos de exportación
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: 71162d896ee76d99f5d47dfa670b62d456243837
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445687"
---
# <a name="working-with-import-libraries-and-export-files"></a>Trabajar con bibliotecas de importación y archivos de exportación

Puede utilizar LIB con la opción /DEF para crear una biblioteca de importación y un archivo de exportación. LINK usa la exportación de archivos para compilar un programa que contiene exportaciones (normalmente una biblioteca de vínculos dinámicos (DLL)) y utiliza la biblioteca de importación para resolver las referencias a dichas exportaciones en otros programas.

Tenga en cuenta que si crea la biblioteca de importación en un paso preliminar, antes de crear el archivo .dll, debe pasar el mismo conjunto de archivos de objeto al compilar el archivo .dll, que se pasa al compilar la biblioteca de importación.

En la mayoría de los casos, no es necesario utilizar LIB para crear la biblioteca de importación. Al vincular un programa (un archivo ejecutable o un archivo DLL) que contiene exportaciones, vínculo crea automáticamente una biblioteca de importación que se describe las exportaciones. Más adelante, cuando vincule un programa que hace referencia a dichas exportaciones, especifique la biblioteca de importación.

Sin embargo, cuando un archivo DLL exporta a un programa que importa desde, si directa o indirectamente, debe utilizar LIB para crear una de las bibliotecas de importación. Cuando LIB crea una biblioteca de importación, también crea un archivo de exportación. Debe usar el archivo de exportación al vincular a uno de los archivos DLL.

## <a name="see-also"></a>Vea también

[Referencia de LIB](../../build/reference/lib-reference.md)