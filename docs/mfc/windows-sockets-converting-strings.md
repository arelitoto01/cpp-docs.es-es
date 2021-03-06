---
title: 'Windows Sockets: Convertir cadenas'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: 984554c2405bf6b8ae6a522e545bcbba6ebae529
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543735"
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: Convertir cadenas

En este artículo y dos artículos complementarios explican varios problemas en la programación de Windows Sockets. Este artículo trata sobre la conversión de cadenas. Los otros temas se tratan en [Windows Sockets: bloquear](../mfc/windows-sockets-blocking.md) y [Windows Sockets: orden de bytes](../mfc/windows-sockets-byte-ordering.md).

Si usa o derivar de la clase [CAsyncSocket](../mfc/reference/casyncsocket-class.md), tendrá que administrar estos problemas por su cuenta. Si usa o derivar de la clase [CSocket](../mfc/reference/csocket-class.md), MFC administra automáticamente.

## <a name="converting-strings"></a>Convertir cadenas

Si se comunica entre las aplicaciones que usan las cadenas almacenadas en diferentes formatos de caracteres anchos, tales como los juegos de Unicode o juegos de caracteres multibyte (MBCS), o entre uno de ellos y una aplicación mediante cadenas de caracteres ANSI, debe administrar las conversiones usted mismo en `CAsyncSocket`. El `CArchive` objeto que se usa con un `CSocket` objeto administra esta conversión automáticamente a través de las capacidades de la clase [CString](../atl-mfc-shared/reference/cstringt-class.md). Para obtener más información, vea la especificación Windows Sockets, que se encuentra en el SDK de Windows.

Para obtener más información, consulte:

- [Windows Sockets: Usar la clase CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: Usar Sockets con archivos](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Nociones](../mfc/windows-sockets-background.md)

- [Windows Sockets: Sockets de flujos](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: Sockets de datagramas](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Vea también

[Windows Sockets en MFC](../mfc/windows-sockets-in-mfc.md)

