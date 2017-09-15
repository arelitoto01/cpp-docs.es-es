---
title: Clase CD2DBrush | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>Clase CD2DBrush
Un contenedor para ID2D1Brush.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="protected-constructors"></a>Constructores protegidos  
  
|Name|Descripción|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Construye un objeto CD2DBrush.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Destructor. Se llama cuando se destruye un objeto brush de D2D.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Conexiones existentes de la interfaz de recursos para el objeto|  
|[CD2DBrush::Destroy](#destroy)|Destruye un objeto CD2DBrush. (Invalida [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Separa la interfaz de recursos desde el objeto|  
|[CD2DBrush::Get](#get)|Interfaz de ID2D1Brush devuelve|  
|[CD2DBrush::GetOpacity](#getopacity)|Obtiene el grado de opacidad de este pincel|  
|[CD2DBrush::getTransform](#gettransform)|Obtiene la transformación actual del destino de representación|  
|[CD2DBrush::IsValid](#isvalid)|Comprueba la validez de los recursos (reemplaza [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Establece el grado de opacidad de este pincel|  
|[CD2DBrush::SetTransform](#settransform)|Aplica la transformación especificada para el destino de representación, reemplazando la transformación existente. Todas las operaciones de dibujos subsiguientes se producen en el espacio transformado|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Interfaz de ID2D1Brush devuelve|  
  
### <a name="protected-data-members"></a>Miembros de datos protegidos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Almacena un puntero a un objeto ID2D1Brush.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Propiedades del pincel.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>CD2DBrush:: ~ CD2DBrush  
 Destructor. Se llama cuando se destruye un objeto brush de D2D.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>CD2DBrush::Attach  
 Conexiones existentes de la interfaz de recursos para el objeto  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Parámetros  
 `pResource`  
 Interfaz de recursos existente. No puede ser NULL  
  
##  <a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 Construye un objeto CD2DBrush.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parámetros  
 `pParentTarget`  
 Puntero para el destino de representación.  
  
 `pBrushProperties`  
 Puntero a la opacidad y la transformación de un pincel.  
  
 `bAutoDestroy`  
 Indica que se destruirá el objeto propietario (pParentTarget).  
  
##  <a name="destroy"></a>CD2DBrush::Destroy  
 Destruye un objeto CD2DBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBrush::Detach  
 Separa la interfaz de recursos desde el objeto  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a interfaz desasociadas recursos.  
  
##  <a name="get"></a>CD2DBrush::Get  
 Interfaz de ID2D1Brush devuelve  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a una interfaz ID2D1Brush o NULL si el objeto no se ha inicializado todavía.  
  
##  <a name="getopacity"></a>CD2DBrush::GetOpacity  
 Obtiene el grado de opacidad de este pincel  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor comprendido entre 0 y 1 que indica la opacidad del pincel. Este valor es un constante multiplicador que escala linealmente el valor alfa de todos los píxeles que se rellena mediante el pincel. Los valores de opacidad se fija en el intervalo de 0 a 1 antes de que se multiplican juntos  
  
##  <a name="gettransform"></a>CD2DBrush::getTransform  
 Obtiene la transformación actual del destino de representación  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `transform`  
 Cuando se devuelve, contiene la transformación actual del destino de representación. Este parámetro se pasa sin inicializar  
  
##  <a name="isvalid"></a>CD2DBrush::IsValid  
 Comprobaciones de validez de los recursos  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 TRUE si el recurso es válido; de lo contrario, FALSE.  
  
##  <a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 Almacena un puntero a un objeto ID2D1Brush.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 Propiedades del pincel.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>CD2DBrush::operator ID2D1Brush *  
 Interfaz de ID2D1Brush devuelve  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a una interfaz ID2D1Brush o NULL si el objeto no se ha inicializado todavía.  
  
##  <a name="setopacity"></a>CD2DBrush::SetOpacity  
 Establece el grado de opacidad de este pincel  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Parámetros  
 `opacity`  
 Un valor comprendido entre 0 y 1 que indica la opacidad del pincel. Este valor es un constante multiplicador que escala linealmente el valor alfa de todos los píxeles que se rellena mediante el pincel. Los valores de opacidad se fija en el intervalo de 0 a 1 antes de que se multiplican juntos  
  
##  <a name="settransform"></a>CD2DBrush::SetTransform  
 Aplica la transformación especificada para el destino de representación, reemplazando la transformación existente. Todas las operaciones de dibujos subsiguientes se producen en el espacio transformado  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parámetros  
 `transform`  
 La transformación que se aplica en el destino de representación  
  
## <a name="see-also"></a>Vea también  
 [Clases](../../mfc/reference/mfc-classes.md)
