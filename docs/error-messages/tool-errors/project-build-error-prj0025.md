---
title: Error PRJ0025 al compilar el proyecto
ms.date: 08/27/2018
f1_keywords:
- PRJ0025
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
ms.openlocfilehash: 5cc6a042c04bc205dd3cf2242d48f2572a51885c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599694"
---
# <a name="project-build-error-prj0025"></a>Error PRJ0025 al compilar el proyecto

> Archivo por lotes '*archivo*' incluye contenido Unicode que no se puede traducir a la página de códigos ANSI del usuario.
>
> *Contenido UNICODE del archivo*

El sistema de proyectos encontró contenido Unicode en un personalizado regla de generación o evento de compilación que no se puede traducir correctamente a la página de códigos ANSI actual del usuario.

La resolución de este error consiste en actualizar el contenido de la regla de compilación o evento para que utilice ANSI o para instalar la página de códigos en el equipo y establecerla como valor predeterminado del sistema de compilación.

Para obtener más información sobre custom pasos de compilación y los eventos de compilación, consulte [Introducción a los pasos de compilación personalizada y eventos de compilación](../../ide/understanding-custom-build-steps-and-build-events.md).