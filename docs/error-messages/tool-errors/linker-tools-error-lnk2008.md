---
title: Error de las herramientas del vinculador LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: 97bb2be18da5d166d1d5fba42e4ec8ce1f0439fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544227"
---
# <a name="linker-tools-error-lnk2008"></a>Error de las herramientas del vinculador LNK2008

Destino de la corrección no está alineado 'symbol_name'

VÍNCULO puede encontrar un destino de la corrección en el archivo de objeto que no se ha alineado correctamente.

Este error puede deberse a producirlo personalizado una alineación (por ejemplo, #pragma [pack](../../preprocessor/pack.md)), [alinear](../../cpp/align-cpp.md) modificador, o mediante código de lenguaje de ensamblado que modifica la alineación.

Si el código no utiliza ninguno de los pasos anteriores, esto puede deberse al compilador.