---
title: Establecer las opciones del vinculador
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
ms.openlocfilehash: 5b885ad5c86bc59029fc6a3a60ccee385703ab2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508945"
---
# <a name="setting-linker-options"></a>Establecer las opciones del vinculador

Opciones del vinculador se pueden establecer dentro o fuera del entorno de desarrollo. Este tema para cada opción del vinculador analiza cómo se puede establecer en el entorno de desarrollo. Consulte [opciones del vinculador](../../build/reference/linker-options.md) para obtener una lista completa.

Al ejecutar vínculo fuera del entorno de desarrollo, puede especificar la entrada en una o más maneras:

- En el [línea de comandos](../../build/reference/linker-command-line-syntax.md)

- Uso de [archivos de comandos](../../build/reference/link-command-files.md)

- En [variables de entorno](../../build/reference/link-environment-variables.md)

Opciones de los procesos primer vínculo especificado en la variable de entorno LINK, seguido de las opciones en el orden en que se especifican en la línea de comandos y en archivos de comandos. Si se repite una opción con distintos argumentos, la última de ellas procesa tiene prioridad.

Las opciones se aplican a toda la compilación; No hay opciones pueden aplicarse a archivos de entrada concretos.

## <a name="see-also"></a>Vea también

[Referencia de compilación de C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)