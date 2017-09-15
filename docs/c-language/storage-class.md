---
title: Clase de almacenamiento | Microsoft Docs
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
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
caps.latest.revision: 8
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
ms.openlocfilehash: a3d3a3c82f88bdcd2b4c77eb23e705ced6c056ce
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---
# <a name="storage-class"></a>Clase de almacenamiento
El especificador de clase de almacenamiento en una definición de función proporciona a la función la clase de almacenamiento `extern` o **static**.  
  
## <a name="syntax"></a>Sintaxis  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* es específico de Microsoft */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*: /\* Para definiciones de función \*/  
 **extern**  
  
 **static**  
  
 Si una definición de función no incluye el elemento *storage-class-specifier*, la clase de almacenamiento utiliza `extern` de forma predeterminada. Puede declarar explícitamente una función como `extern`, pero no es necesario.  
  
 Si la declaración de una función contiene el elemento *storage-class-specifier* `extern`, el identificador tiene la misma vinculación que cualquier declaración visible del identificador con ámbito de archivo. Si no hay ninguna declaración visible con ámbito de archivo, el identificador tiene una vinculación externa. Si un identificador tiene ámbito de archivo pero ningún especificador *storage-class-specifier*, el identificador tiene una vinculación externa. Vinculación externa significa que cada instancia del identificador designa el mismo objeto o función. Vea [Duración, ámbito, visibilidad y vinculación](../c-language/lifetime-scope-visibility-and-linkage.md) para obtener más información sobre la vinculación y el ámbito de archivo.  
  
 Las declaraciones de función de ámbito de bloque con un especificador de clase de almacenamiento distinto de `extern` generan errores.  
  
 Una función con clase de almacenamiento **static** solo es visible en el archivo de código fuente en el que se define. Todas las demás funciones, se les asigne la clase de almacenamiento `extern` de forma explícita o implícita, están visibles en todos los archivos de código fuente del programa. Si se desea la clase de almacenamiento **static**, esta debe declararse en la primera aparición de una declaración (si existe) de la función, y en la definición de la función.  
  
 **Específicos de Microsoft**  
  
 Cuando las extensiones de Microsoft están habilitadas, una función declarada originalmente sin una clase de almacenamiento o con la clase de almacenamiento `extern` tiene la clase de almacenamiento **static** si la definición de función está en el mismo archivo de código fuente y si la definición especifica explícitamente la clase de almacenamiento **static**.  
  
 Al compilar con la opción del compilador /Ze, las funciones declaradas dentro de un bloque mediante la palabra clave `extern` tienen visibilidad global. Esto no es cierto cuando se compila con /Za. No debe confiar en esta característica si la portabilidad del código fuente es importante.  
  
 **FIN de Específicos de Microsoft**  
  
## <a name="see-also"></a>Vea también  
 [Definiciones de función de C](../c-language/c-function-definitions.md)