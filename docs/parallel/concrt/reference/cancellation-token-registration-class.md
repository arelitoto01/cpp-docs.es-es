---
title: cancellation_token_registration (clase) | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1dd55aff292926b930271257bda583a2f93aba92
ms.contentlocale: es-es
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration (Clase)
La clase `cancellation_token_registration` representa una notificación de devolución de llamada de un objeto `cancellation_token`. Cuando el método `register` de un objeto `cancellation_token` se usa para recibir una notificación de cuándo se produce la cancelación, se devuelve un objeto `cancellation_token_registration` como identificador a la devolución de la llamada de modo que el llamador puede solicitar que ya no se realice una devolución de llamada específica a través del uso del método `deregister`.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[cancellation_token_registration](#ctor)||  
|[~ cancellation_token_registration (destructor)](#dtor)||  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** pplcancellation_token.h  
  
 **Espacio de nombres:** simultaneidad  
  
##  <a name="dtor"></a>~ cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="ctor"></a>cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Src`  
  
##  <a name="operator_neq"></a>operador! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parámetros  
 `_Rhs`  
  
### <a name="return-value"></a>Valor devuelto  
  
##  <a name="operator_eq"></a>operador = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Src`  
  
### <a name="return-value"></a>Valor devuelto  
  
##  <a name="operator_eq_eq"></a>operador == 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parámetros  
 `_Rhs`  
  
### <a name="return-value"></a>Valor devuelto  
  
## <a name="see-also"></a>Vea también  
 [concurrency (espacio de nombres)](concurrency-namespace.md)
