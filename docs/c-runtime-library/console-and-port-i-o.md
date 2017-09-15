---
title: E/S de consola y de puerto | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.openlocfilehash: f252a10b0d340b6fceac2c2372cdf991764c83c4
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="console-and-port-io"></a>E/S de consola y de puerto
Estas rutinas leen y escriben en la consola o en el puerto especificado. Las rutinas de E/S de consola no son compatibles con las rutinas de la biblioteca de E/S de secuencia o de E/S de bajo nivel. No es necesario abrir ni cerrar la consola o el puerto antes de ejecutar la E/S, por lo que no hay rutinas abiertas ni cerradas en esta categoría. En los sistemas operativos Windows, el resultado de estas funciones siempre se dirige a la consola y no se puede redirigir.  
  
### <a name="console-and-port-io-routines"></a>Rutinas de E/S de consola y de puerto  
  
|Rutina|Uso|  
|-------------|---------|  
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Leer cadena de la consola|  
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Escribir datos con formato en la consola|  
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Escribir cadena en la consola|  
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Leer datos con formato de la consola|  
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Leer carácter de la consola|  
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Leer carácter de la consola y reproducirlo|  
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Leer un byte del puerto de E/S especificado|  
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Leer doble palabra del puerto de E/S especificado|  
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|Leer palabra de 2 bytes del puerto de E/S especificado|  
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Buscar pulsación de tecla en la consola; usarla antes de intentar leer de la consola|  
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Escribir un byte en el puerto de E/S especificado|  
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Escribir doble palabra en el puerto de E/S especificado|  
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Escribir palabra en el puerto de E/S especificado|  
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Escribir carácter en la consola|  
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Aplicar el método "unget" al último carácter leído de la consola, para que sea la siguiente lectura de caracteres|  
  
## <a name="see-also"></a>Vea también  
 [Entrada y salida](../c-runtime-library/input-and-output.md)   
 [Rutinas en tiempo de ejecución por categoría](../c-runtime-library/run-time-routines-by-category.md)