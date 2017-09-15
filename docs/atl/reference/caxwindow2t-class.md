---
title: Clase CAxWindow2T | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: a0724b0ea8922d1f39d8cf7ccd630068c32ea3ac
ms.contentlocale: es-es
ms.lasthandoff: 02/28/2017

---
# <a name="caxwindow2t-class"></a>Clase CAxWindow2T
Esta clase proporciona métodos para manipular una ventana que hospeda un control ActiveX y también tiene compatibilidad para hospedar controles ActiveX con licencia.  
  
> [!IMPORTANT]
>  Esta clase y sus miembros no pueden utilizarse en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Parámetros  
 *TBase*  
 Clase de la que `CAxWindowT` se deriva.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Construye un objeto `CAxWindow2T`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Crea una ventana de host.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Crea un control ActiveX con licencia, lo inicializa y lo hospeda en la ventana especificada.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Crea un control ActiveX con licencia, lo inicializa, hospeda en la ventana especificada y recupera un puntero de interfaz (o punteros) del control.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Método estático que se recupera el nombre de la clase de ventana.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Asigna un `HWND` a un `CAxWindow2T` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `CAxWindow2T`Proporciona métodos para manipular una ventana que hospeda un control ActiveX. `CAxWindow2T`También tiene compatibilidad para hospedar controles ActiveX con licencia. Es el proceso de hospedaje proporcionada por " **AtlAxWinLic80**", que es ajustada por `CAxWindow2T`.  
  
 Clase `CAxWindow2` se implementa como una especialización de la `CAxWindow2T` clase. Esta especialización se declara como:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`los miembros se documentan en [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 Consulte [hospeda controles de ActiveX mediante AXHost de ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) para obtener un ejemplo que utiliza los miembros de esta clase.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlwin.h  
  
##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 Construye un objeto `CAxWindow2T`.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Parámetros  
 `hWnd`  
 Identificador de una ventana existente.  
  
##  <a name="create"></a>CAxWindow2T::Create  
 Crea una ventana de host.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>Comentarios  
 `CAxWindow2T::Create`llamadas [CWindow:: Create](../../atl/reference/cwindow-class.md#create) con el `LPCTSTR lpstrWndClass` parámetro establecido en la clase de ventana que proporciona hospedaje de controles ( **AtlAxWinLic80**).  
  
 Consulte `CWindow::Create` para obtener una descripción de los parámetros y valor devuelto.  
  
 **Nota** si se utiliza 0 como valor para el `MenuOrID` parámetro, se debe especificar como 0U (valor) para evitar un error del compilador.  
  
### <a name="example"></a>Ejemplo  
 Consulte [hospeda controles de ActiveX mediante AXHost de ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) para obtener un ejemplo que usa `CAxWindow2T::Create`.  
  
##  <a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
 Crea un control ActiveX con licencia, lo inicializa y lo hospeda en la ventana especificada.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 `bstrLicKey`  
 La clave de licencia para el control; Es NULL si la creación de un control sin licencia.  
  
### <a name="remarks"></a>Comentarios  
 Consulte [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) para obtener una descripción de los demás parámetros y valor devuelto.  
  
### <a name="example"></a>Ejemplo  
 Consulte [hospeda controles de ActiveX mediante AXHost de ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) para obtener un ejemplo que usa `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 Crea un control ActiveX con licencia, lo inicializa, hospeda en la ventana especificada y recupera un puntero de interfaz (o punteros) del control.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 `bstrLicKey`  
 La clave de licencia para el control; Es NULL si la creación de un control sin licencia.  
  
### <a name="remarks"></a>Comentarios  
 Consulte [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) para obtener una descripción de los demás parámetros y valor devuelto.  
  
### <a name="example"></a>Ejemplo  
 Consulte [hospeda controles de ActiveX mediante AXHost de ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) para obtener un ejemplo que usa `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 Recupera el nombre de la clase de ventana.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a una cadena que contiene el nombre de la clase de ventana ( **AtlAxWinLic80**) que puede hospedar controles ActiveX con licencia y sin licencia.  
  
##  <a name="operator_eq"></a>CAxWindow2T::operator =  
 Asigna un `HWND` a un `CAxWindow2T` objeto.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Parámetros  
 `hWnd`  
 Identificador de una ventana existente.  
  
## <a name="see-also"></a>Vea también  
 [Información general de la clase](../../atl/atl-class-overview.md)   
 [Preguntas más frecuentes sobre la contención de controles](../../atl/atl-control-containment-faq.md)
