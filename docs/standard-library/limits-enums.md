---
title: Enumeraciones &lt;limits&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 519cc2c696b5dcb67fed79fd04c3e7d66e7d0ad9
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="ltlimitsgt-enums"></a>Enumeraciones &lt;limits&gt;
|||  
|-|-|  
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|  
  
##  <a name="float_denorm_style"></a>  Enumeración float_denorm_style  
 La enumeración describe los diversos métodos que puede elegir una implementación para representar un valor de punto flotante no normalizado (un valor demasiado pequeño para representarlo como un valor normalizado):  
  
```
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```  
  
### <a name="return-value"></a>Valor devuelto  
 La enumeración devuelve:  
  
- **denorm_indeterminate** si no se puede determinar en tiempo de traducción la presencia o la ausencia de formularios no normalizados.  
  
- **denorm_absent** si no hay presentes formularios no normalizados.  
  
- **denorm_present** si hay presentes formularios no normalizados.  
  
### <a name="example"></a>Ejemplo  
  Vea [numeric_limits:: has_denorm](../standard-library/numeric-limits-class.md#has_denorm) para obtener un ejemplo del acceso a los valores de esta enumeración.  
  
##  <a name="float_round_style"></a>  Enumeración float_round_style  
 La enumeración describe los diversos métodos que puede elegir una implementación para redondear un valor de punto flotante a un valor entero.  
  
```
enum float_round_style {    
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```  
  
### <a name="return-value"></a>Valor devuelto  
 La enumeración devuelve:  
  
- **round_indeterminate** si no se puede determinar el método de redondeo.  
  
- **round_toward_zero** si se redondea hacia cero.  
  
- **round_to_nearest** si se redondea al entero más próximo.  
  
- **round_toward_infinity** si se redondea para evitar el cero.  
  
- **round_toward_neg_infinity** si se redondea al entero más negativo.  
  
### <a name="example"></a>Ejemplo  
  Vea [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) para obtener un ejemplo del acceso a los valores de esta enumeración.  
  
## <a name="see-also"></a>Vea también  
 [\<limits>](../standard-library/limits.md)



