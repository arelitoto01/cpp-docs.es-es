---
title: /ZW (Compilación de Windows Runtime)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: 297697d215a78cbf1aefef30df53f6956c4e16b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629767"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Compilación de Windows Runtime)

Compila el código para admitir las extensiones de componente de C++ de Visual C++ / fuente c++ / CX para la creación de aplicaciones de plataforma Universal de Windows (UWP).

Cuando usas **/ZW** para compilar, especifique siempre **/EHsc** también.

## <a name="syntax"></a>Sintaxis

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Argumentos

**nostdlib**<br/>
Indica que Platform.winmd, Windows.Foundation.winmd y otros archivos de metadatos de Windows (.winmd) predeterminados no se incluyen automáticamente en la compilación, En su lugar, debe usar el [/FU (nombre #using archivo)](../../build/reference/fu-name-forced-hash-using-file.md) opción del compilador para especificar explícitamente los archivos de metadatos de Windows.

## <a name="remarks"></a>Comentarios

Al especificar el **/ZW** opción, el compilador admite estas características:

- Los archivos de metadatos necesarios, espacios de nombres, tipos de datos y funciones que la aplicación necesita para ejecutarse en el tiempo de ejecución de Windows.

- Automático: recuento de referencias de objetos de Windows Runtime y descarte de un objeto cuando su recuento de referencias llega a cero automático.

Dado que el enlazador incremental no admite los metadatos de Windows incluidos en los archivos .obj mediante la **/ZW** opción, el [/Gm (habilitar recompilación mínima)](../../build/reference/gm-enable-minimal-rebuild.md) es incompatible con la opción  **/ZW**.

Para obtener más información, consulte [referencia del lenguaje Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Requisitos

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)