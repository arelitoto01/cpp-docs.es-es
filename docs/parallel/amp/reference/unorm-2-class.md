---
title: unorm_2 (clase) | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator+=
- amp_short_vectors/Concurrency::graphics::unnorm_2::y
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::x
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator--
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator*=
- amp_short_vectors/Concurrency::graphics::unnorm_2::xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator=
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::rg
- amp_short_vectors/Concurrency::graphics::unorm_2
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-=
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator/=
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::gr
- amp_short_vectors/Concurrency::graphics::unnorm_2::r
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::g
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator++
dev_langs:
- C++
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: 11
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
ms.openlocfilehash: 789c1fc872f478945de6444c07de069b50074a7f
ms.contentlocale: es-es
ms.lasthandoff: 03/17/2017

---
# <a name="unorm2-class"></a>unorm_2 (Clase)
Representa un vector corto de dos números normales sin signo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class unorm_2;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-typedefs"></a>Definiciones de tipos públicas  
  
|Nombre|Descripción|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[Constructor unorm_2](#ctor)|Sobrecargado. El constructor predeterminado, inicializa todos los elementos con 0.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|unorm_2:: get_X||  
|unorm_2:: get_xy||  
|unorm_2:: get_Y||  
|unorm_2:: get_yx||  
|unorm_2:: ref_g||  
|unorm_2:: ref_r||  
|unorm_2:: ref_x||  
|unorm_2:: ref_y||  
|unorm_2:: set_X||  
|unorm_2:: set_xy||  
|unorm_2:: set_y||  
|unorm_2:: set_yx||  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|unorm_2:: operator--||  
|unorm_2:: operator * =||  
|unorm_2:: operator / =||  
|unorm_2:: operator ++||  
|unorm_2:: operator +=||  
|unorm_2:: operator =||  
|unorm_2:: operator =||  
  
### <a name="public-constants"></a>Constantes públicas  
  
|Nombre|Descripción|  
|----------|-----------------|  
|Constante unorm_2::size||  
  
### <a name="public-data-members"></a>Miembros de datos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|unorm_2:: g||  
|unorm_2:: GR||  
|unorm_2:: r||  
|unorm_2:: RG||  
|unorm_2:: x||  
|unorm_2:: XY||  
|unorm_2:: y||  
|unorm_2:: YX||  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `unorm_2`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** amp_short_vectors.h  
  
 **Namespace:** Graphics  
  
##  <a name="ctor"></a>unorm_2 

 El constructor predeterminado, inicializa todos los elementos con 0.  
  
```  
unorm_2() restrict(amp,
    cpu);

 
unorm_2(
    unorm _V0,  
    unorm _V1) restrict(amp,
    cpu);

 
unorm_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
unorm_2(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_2(
    float _V) restrict(amp,
    cpu);

 
unorm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parámetros  
 `_V0`  
 El valor para inicializar el elemento 0.  
  
 `_V1`  
 El valor para inicializar el elemento 1.  
  
 `_V`  
 El valor de inicialización.  
  
 `_Other`  
 Objeto utilizado para inicializar.  
  
##  <a name="unorm_2__size"></a>tamaño 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Vea también  
 [Concurrency::graphics (espacio de nombres)](concurrency-graphics-namespace.md)
