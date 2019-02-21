---
title: Aplicaciones Windows universales (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: 3ffcc38dfd849c9cd5eaf9e6466d53731becdd9a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693092"
---
# <a name="universal-windows-apps-c"></a>Aplicaciones Windows universales (C++)
Las aplicaciones de la plataforma universal de Windows (UWP) representan un conjunto de principios de diseño que hacen hincapié en las interfaces de usuario simples que se centran en el contenido que se ajusta automáticamente para distintos tamañosde pantalla en diferentes dispositivos. La interfaz de usuario se crea en el marcado XAML y el código subyacente en C++ nativo. También puede crear componentes o nuevos archivos (archivos DLL) que pueden consumir las aplicaciones de UWP escritas en otros lenguajes. La superficie de API de las aplicaciones de UWP es Windows Runtime, que es una biblioteca factorizada que proporciona una amplia variedad de el S.o


> [!TIP]
> Para Windows 10, puede usar el convertidor de aplicación de puente de escritorio para empaquetar la aplicación de escritorio existente para la implementación a través de la Microsoft Store. Para obtener más información, consulte [utilizando Visual C++ en tiempo de ejecución en el proyecto Centennial](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) y [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>Las aplicaciones UWP que usan C++ / c++ / WinRT

C++ / c++ / WinRT es una nueva, encabezado basada en la biblioteca proyección del lenguaje C++ para el tiempo de ejecución de Windows que usa completamente estándar de C++, a diferencia de C++ / c++ / implementación de CX. C++ / c++ / WinRT no usa una sintaxis no estándar o extensiones de lenguaje de Microsoft y aprovecha plenamente el compilador de C++ para crear la salida altamente optimizada. Para obtener más información, consulte [C++ / c++ / WinRT](/windows/uwp/cpp-and-winrt-apis). Para obtener una introducción a C++ / c++ / WinRT y una guía de inicio rápido de código, vea [Introducción a C++ / c++ / WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>Las aplicaciones UWP que usan C++ / c++ / CX

|||
|-|-|
|[Referencia del lenguaje Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Describe el conjunto de extensiones que simplifican el uso de C++ de Windows Runtime APIs y habilitar el control de errores que se basa en excepciones.|
|[Compilar aplicaciones y bibliotecas (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Describe cómo crear bibliotecas DLL y estáticas a las que se puede tener acceso desde una aplicación o componente de C++/CX.|
|[Tutorial: Crear una UWP aplicación "Hello, World" en C / c++ / CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Un tutorial que presenta los conceptos básicos del desarrollo de aplicaciones UWP en C++ / c++ / CX. |
|[Creación de componentes de Windows Runtime en C++ / c++ / CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Describe cómo crear archivos DLL que pueden consumir otras aplicaciones para UWP y componentes.|
|[Programación de juegos de UWP](/windows/uwp/gaming/)|Describe cómo utilizar DirectX y C++ / c++ / CX para crear juegos.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Aplicaciones UWP que usan la biblioteca de plantillas C++ de Windows en tiempo de ejecución (WRL)

La biblioteca de plantillas C++ de Windows en tiempo de ejecución proporciona las interfaces de COM de bajo nivel mediante el cual puede tener acceso a código ISO C++ en tiempo de ejecución de Windows en un entorno sin excepciones. En la mayoría de los casos, se recomienda usar C++ / c++ / WinRT o C++ / c++ / CX en lugar de la biblioteca de plantillas de C++ de Windows en tiempo de ejecución para el desarrollo de aplicaciones UWP. Para obtener información acerca de la biblioteca de plantillas C++ de Windows en tiempo de ejecución, vea [biblioteca de plantillas de C++ (WRL) de Windows en tiempo de ejecución](windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Vea también

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
[Información general de la programación para Windows en C++](overview-of-windows-programming-in-cpp.md)<br/>
