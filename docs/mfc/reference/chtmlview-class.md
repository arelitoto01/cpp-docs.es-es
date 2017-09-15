---
title: Clase CHtmlView | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlView
- AFXHTML/CHtmlView
- AFXHTML/CHtmlView::Create
- AFXHTML/CHtmlView::CreateControlSite
- AFXHTML/CHtmlView::ExecFormsCommand
- AFXHTML/CHtmlView::ExecWB
- AFXHTML/CHtmlView::GetAddressBar
- AFXHTML/CHtmlView::GetApplication
- AFXHTML/CHtmlView::GetBusy
- AFXHTML/CHtmlView::GetContainer
- AFXHTML/CHtmlView::GetFullName
- AFXHTML/CHtmlView::GetFullScreen
- AFXHTML/CHtmlView::GetHeight
- AFXHTML/CHtmlView::GetHtmlDocument
- AFXHTML/CHtmlView::GetLeft
- AFXHTML/CHtmlView::GetLocationName
- AFXHTML/CHtmlView::GetLocationURL
- AFXHTML/CHtmlView::GetMenuBar
- AFXHTML/CHtmlView::GetOffline
- AFXHTML/CHtmlView::GetParentBrowser
- AFXHTML/CHtmlView::GetProperty
- AFXHTML/CHtmlView::GetReadyState
- AFXHTML/CHtmlView::GetRegisterAsBrowser
- AFXHTML/CHtmlView::GetRegisterAsDropTarget
- AFXHTML/CHtmlView::GetSilent
- AFXHTML/CHtmlView::GetSource
- AFXHTML/CHtmlView::GetStatusBar
- AFXHTML/CHtmlView::GetTheaterMode
- AFXHTML/CHtmlView::GetToolBar
- AFXHTML/CHtmlView::GetTop
- AFXHTML/CHtmlView::GetTopLevelContainer
- AFXHTML/CHtmlView::GetType
- AFXHTML/CHtmlView::GetVisible
- AFXHTML/CHtmlView::GetWidth
- AFXHTML/CHtmlView::GoBack
- AFXHTML/CHtmlView::GoForward
- AFXHTML/CHtmlView::GoHome
- AFXHTML/CHtmlView::GoSearch
- AFXHTML/CHtmlView::LoadFromResource
- AFXHTML/CHtmlView::Navigate
- AFXHTML/CHtmlView::Navigate2
- AFXHTML/CHtmlView::OnBeforeNavigate2
- AFXHTML/CHtmlView::OnCommandStateChange
- AFXHTML/CHtmlView::OnDocumentComplete
- AFXHTML/CHtmlView::OnDocWindowActivate
- AFXHTML/CHtmlView::OnDownloadBegin
- AFXHTML/CHtmlView::OnDownloadComplete
- AFXHTML/CHtmlView::OnEnableModeless
- AFXHTML/CHtmlView::OnFilterDataObject
- AFXHTML/CHtmlView::OnFrameWindowActivate
- AFXHTML/CHtmlView::OnFullScreen
- AFXHTML/CHtmlView::OnGetDropTarget
- AFXHTML/CHtmlView::OnGetExternal
- AFXHTML/CHtmlView::OnGetHostInfo
- AFXHTML/CHtmlView::OnGetOptionKeyPath
- AFXHTML/CHtmlView::OnHideUI
- AFXHTML/CHtmlView::OnMenuBar
- AFXHTML/CHtmlView::OnNavigateComplete2
- AFXHTML/CHtmlView::OnNavigateError
- AFXHTML/CHtmlView::OnNewWindow2
- AFXHTML/CHtmlView::OnProgressChange
- AFXHTML/CHtmlView::OnPropertyChange
- AFXHTML/CHtmlView::OnQuit
- AFXHTML/CHtmlView::OnResizeBorder
- AFXHTML/CHtmlView::OnShowContextMenu
- AFXHTML/CHtmlView::OnShowUI
- AFXHTML/CHtmlView::OnStatusBar
- AFXHTML/CHtmlView::OnStatusTextChange
- AFXHTML/CHtmlView::OnTheaterMode
- AFXHTML/CHtmlView::OnTitleChange
- AFXHTML/CHtmlView::OnToolBar
- AFXHTML/CHtmlView::OnTranslateAccelerator
- AFXHTML/CHtmlView::OnTranslateUrl
- AFXHTML/CHtmlView::OnUpdateUI
- AFXHTML/CHtmlView::OnVisible
- AFXHTML/CHtmlView::PutProperty
- AFXHTML/CHtmlView::QueryFormsCommand
- AFXHTML/CHtmlView::QueryStatusWB
- AFXHTML/CHtmlView::Refresh
- AFXHTML/CHtmlView::Refresh2
- AFXHTML/CHtmlView::SetAddressBar
- AFXHTML/CHtmlView::SetFullScreen
- AFXHTML/CHtmlView::SetHeight
- AFXHTML/CHtmlView::SetLeft
- AFXHTML/CHtmlView::SetMenuBar
- AFXHTML/CHtmlView::SetOffline
- AFXHTML/CHtmlView::SetRegisterAsBrowser
- AFXHTML/CHtmlView::SetRegisterAsDropTarget
- AFXHTML/CHtmlView::SetSilent
- AFXHTML/CHtmlView::SetStatusBar
- AFXHTML/CHtmlView::SetTheaterMode
- AFXHTML/CHtmlView::SetToolBar
- AFXHTML/CHtmlView::SetTop
- AFXHTML/CHtmlView::SetVisible
- AFXHTML/CHtmlView::SetWidth
- AFXHTML/CHtmlView::Stop
dev_langs:
- C++
helpviewer_keywords:
- browsers, MFC support for
- CHtmlView class
- WebBrowser control
- WebBrowser control, MFC support
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
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
ms.openlocfilehash: d9d96ab02a0c49a2ece12c933f5d550a46204a39
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="chtmlview-class"></a>Clase CHtmlView
Proporciona la funcionalidad del control WebBrowser en el contexto de la arquitectura de vista/documento de MFC.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CHtmlView : public CFormView  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CHtmlView::Create](#create)|Crea el control WebBrowser.|  
|[CHtmlView::CreateControlSite](#createcontrolsite)|Reemplazable usado para crear una instancia del sitio de control para hospedar un control en el formulario.|  
|[CHtmlView::ExecFormsCommand](#execformscommand)|Ejecuta el comando especificado mediante el método `IOleCommandTarget::Exec` .|  
|[CHtmlView::ExecWB](#execwb)|Ejecuta un comando.|  
|[CHtmlView::GetAddressBar](#getaddressbar)|Determina si la barra de direcciones del objeto de Internet Explorer está visible. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::GetApplication](#getapplication)|Recupera un objeto de aplicación que representa la aplicación que contiene la instancia actual de la aplicación Internet Explorer.|  
|[CHtmlView::GetBusy](#getbusy)|Recupera un valor que indica si una descarga u otra actividad sigue en curso.|  
|[CHtmlView::GetContainer](#getcontainer)|Recupera el contenedor del control WebBrowser.|  
|[CHtmlView::GetFullName](#getfullname)|Recupera el nombre completo, incluida la ruta de acceso, del recurso que se muestra en el explorador web. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::GetFullScreen](#getfullscreen)|Indica si el control WebBrowser está funcionando en modo de pantalla completa o en modo de ventana normal.|  
|[CHtmlView::GetHeight](#getheight)|Recupera el alto de la ventana principal de Internet Explorer.|  
|[CHtmlView::GetHtmlDocument](#gethtmldocument)|Recupera el documento HTML activo.|  
|[CHtmlView::GetLeft](#getleft)|Recupera la coordenada de pantalla del borde izquierdo de la ventana principal de Internet Explorer.|  
|[CHtmlView::GetLocationName](#getlocationname)|Recupera el nombre del recurso que WebBrowser muestra actualmente.|  
|[CHtmlView::GetLocationURL](#getlocationurl)|Recupera la dirección URL del recurso que WebBrowser muestra actualmente.|  
|[CHtmlView::GetMenuBar](#getmenubar)|Recupera un valor que determina si la barra de menús está visible.|  
|[CHtmlView::GetOffline](#getoffline)|Recupera un valor que determina si el control está sin conexión.|  
|[CHtmlView::GetParentBrowser](#getparentbrowser)|Recupera un puntero a la interfaz `IDispatch` . Para obtener más información, consulte [implementa la interfaz IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](#getproperty)|Recupera el valor actual de una propiedad asociada con el objeto especificado.|  
|[CHtmlView::GetReadyState](#getreadystate)|Recupera el estado listo del objeto de explorador web.|  
|[CHtmlView::GetRegisterAsBrowser](#getregisterasbrowser)|Indica si el control WebBrowser está registrado como un explorador de nivel superior para la resolución de nombres de destino.|  
|[CHtmlView::GetRegisterAsDropTarget](#getregisterasdroptarget)|Indica si el control WebBrowser está registrado como un destino para colocar para la navegación.|  
|[CHtmlView::GetSilent](#getsilent)|Indica si se pueden mostrar los cuadros de diálogo.|  
|[CHtmlView::GetSource](#getsource)|Código fuente HTML de la página web.|  
|[CHtmlView::GetStatusBar](#getstatusbar)|Indica si la barra de estado de Internet Explorer está visible. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::GetTheaterMode](#gettheatermode)|Indica si el control WebBrowser está en modo de pantalla completa.|  
|[CHtmlView::GetToolBar](#gettoolbar)|Recupera un valor que determina si la barra de herramientas está visible.|  
|[CHtmlView::GetTop](#gettop)|Recupera la coordenada de pantalla del borde superior de la ventana principal de Internet Explorer.|  
|[CHtmlView::GetTopLevelContainer](#gettoplevelcontainer)|Recupera un valor que indica si el objeto actual es el contenedor de nivel superior del control WebBrowser.|  
|[CHtmlView::GetType](#gettype)|Recupera el nombre de tipo del objeto de documento.|  
|[CHtmlView::GetVisible](#getvisible)|Recupera un valor que indica si el objeto está visible u oculto.|  
|[CHtmlView::GetWidth](#getwidth)|Recupera el ancho de la ventana principal de Internet Explorer.|  
|[CHtmlView::GoBack](#goback)|Navega al elemento anterior de la lista de historial.|  
|[CHtmlView::GoForward](#goforward)|Navega al elemento siguiente de la lista de historial.|  
|[CHtmlView::GoHome](#gohome)|Navega a la página de inicio o principal actual.|  
|[CHtmlView::GoSearch](#gosearch)|Navega a la página de búsqueda actual.|  
|[CHtmlView::LoadFromResource](#loadfromresource)|Carga un recurso en el control WebBrowser.|  
|[CHtmlView::Navigate](#navigate)|Navega al recurso identificado con una dirección URL.|  
|[CHtmlView::Navigate2](#navigate2)|Navega al recurso identificado con una dirección URL o al archivo identificado mediante una ruta de acceso completa.|  
|[CHtmlView::OnBeforeNavigate2](#onbeforenavigate2)|Se llama antes de que tenga lugar la navegación en el control WebBrowser especificado (en un elemento de ventana o conjunto de marcos)|  
|[CHtmlView::OnCommandStateChange](#oncommandstatechange)|Se llama para notificar a una aplicación que el estado habilitado de un comando de explorador web ha cambiado.|  
|[CHtmlView::OnDocumentComplete](#ondocumentcomplete)|Se llama para notificar a una aplicación que un documento alcanzó el estado `READYSTATE_COMPLETE` .|  
|[CHtmlView::OnDocWindowActivate](#ondocwindowactivate)|Invoca desde la implementación de Internet Explorer o MSHTML de [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), lo que notifica el objeto en el contexto activo cuando se activa o se desactiva la ventana de documento del contenedor.|  
|[CHtmlView::OnDownloadBegin](#ondownloadbegin)|Se llama para notificar a una aplicación que se está iniciando una operación de navegación.|  
|[CHtmlView::OnDownloadComplete](#ondownloadcomplete)|Se llama cuando una operación de navegación termina, se detiene o no se puede realizar.|  
|[CHtmlView::OnEnableModeless](#onenablemodeless)|Se llama para habilitar o deshabilitar los cuadros de diálogo no modales cuando el contenedor crea o destruye un cuadro de diálogo modal.|  
|[CHtmlView::OnFilterDataObject](#onfilterdataobject)|Internet Explorer o MSHTML lo llaman en el host para permitir que el host reemplace el objeto de datos de Internet Explorer o MSHTML.|  
|[CHtmlView::OnFrameWindowActivate](#onframewindowactivate)|Llamar desde [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) para notificar al objeto cuando el contenedor del nivel superior, ventana de marco está activada o desactivada.|  
|[CHtmlView::OnFullScreen](#onfullscreen)|Se llama cuando la propiedad FullScreen cambia.|  
|[CHtmlView::OnGetDropTarget](#ongetdroptarget)|Llama a Internet Explorer o MSHTML cuando se que se utiliza como un destino de colocación para permitir que el host proporcione una alternativa [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CHtmlView::OnGetExternal](#ongetexternal)|Internet Explorer o MSHTML lo llaman para obtener la interfaz `IDispatch` del host.|  
|[CHtmlView::OnGetHostInfo](#ongethostinfo)|Recupera las capacidades de la interfaz de usuario del host de Internet Explorer o MSHTML.|  
|[CHtmlView::OnGetOptionKeyPath](#ongetoptionkeypath)|Devuelve la clave del registro bajo la que Internet Explorer o MSHTML almacenan las preferencias del usuario.|  
|[CHtmlView::OnHideUI](#onhideui)|Se llama cuando Internet Explorer o MSHTML quita sus menús y barras de herramientas.|  
|[CHtmlView::OnMenuBar](#onmenubar)|Se llama cuando la propiedad MenuBar cambia.|  
|[CHtmlView::OnNavigateComplete2](#onnavigatecomplete2)|Se llama cuando se completa la navegación a un hipervínculo (en un elemento de ventana o conjunto de marcos)|  
|[CHtmlView::OnNavigateError](#onnavigateerror)|El marco de trabajo lo llama si la navegación a un hipervínculo no se realiza correctamente.|  
|[CHtmlView::OnNewWindow2](#onnewwindow2)|Se llama cuando se va a crear una nueva ventana para mostrar un recurso.|  
|[CHtmlView::OnProgressChange](#onprogresschange)|Se llama para notificar a una aplicación que se actualizó el progreso de una operación de descarga.|  
|[CHtmlView::OnPropertyChange](#onpropertychange)|Se llama para notificar a una aplicación que el [PutProperty](#putproperty) método ha cambiado el valor de una propiedad.|  
|[CHtmlView::OnQuit](#onquit)|Se llama para notificar a una aplicación que la aplicación Internet Explorer está preparada para cerrarse. (Se aplica a Internet Explorer solamente)|  
|[CHtmlView::OnResizeBorder](#onresizeborder)|Invoca desde la implementación de Internet Explorer o MSHTML de [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), notifica el objeto que debe cambiar el tamaño de su espacio de borde.|  
|[CHtmlView::OnShowContextMenu](#onshowcontextmenu)|Se llama desde Internet Explorer o MSHTML cuando está a punto de mostrar el menú contextual.|  
|[CHtmlView::OnShowUI](#onshowui)|Se llama antes de que Internet Explorer o MSHTML muestren sus menús y barras de herramientas.|  
|[CHtmlView::OnStatusBar](#onstatusbar)|Se llama cuando la propiedad StatusBar cambia.|  
|[CHtmlView::OnStatusTextChange](#onstatustextchange)|Se llama para notificar a una aplicación que el texto de la barra de estado asociada con el control WebBrowser ha cambiado.|  
|[CHtmlView::OnTheaterMode](#ontheatermode)|Se llama cuando la propiedad TheaterMode cambia.|  
|[CHtmlView::OnTitleChange](#ontitlechange)|Se llama para notificar a una aplicación si el título de un documento del control WebBrowser está disponible o cambia.|  
|[CHtmlView::OnToolBar](#ontoolbar)|Se llama cuando la propiedad ToolBar cambia.|  
|[CHtmlView::OnTranslateAccelerator](#ontranslateaccelerator)|Llama a Internet Explorer o MSHTML cuando [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) o [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) se llama para procesar mensajes de tecla de método abreviado de menú de cola de mensajes del contenedor.|  
|[CHtmlView::OnTranslateUrl](#ontranslateurl)|Internet Explorer o MSHTML lo llaman para ofrecer al host la oportunidad de modificar la dirección URL que se va a cargar.|  
|[CHtmlView::OnUpdateUI](#onupdateui)|Notifica al host que cambió el estado del comando.|  
|[CHtmlView::OnVisible](#onvisible)|Se llama cuando la ventana del control WebBrowser debería estar visible u oculta.|  
|[CHtmlView::PutProperty](#putproperty)|Recupera el valor actual de una propiedad asociada con el objeto especificado.|  
|[CHtmlView::QueryFormsCommand](#queryformscommand)|Consulta el estado de uno o más comandos generados por eventos de interfaz de usuario.|  
|[CHtmlView::QueryStatusWB](#querystatuswb)|Consulta el estado de un comando procesado por el control WebBrowser.|  
|[CHtmlView::Refresh](#refresh)|Vuelve a cargar la página actual.|  
|[CHtmlView::Refresh2](#refresh2)|Vuelve a cargar el archivo actual y, opcionalmente, impide que se envíe el encabezado `pragma:nocache` .|  
|[CHtmlView::SetAddressBar](#setaddressbar)|Muestra u oculta la barra de direcciones del objeto de Internet Explorer. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::SetFullScreen](#setfullscreen)|Establece un valor para determinar si el control está funcionando en modo de pantalla completa o en modo de ventana normal. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::SetHeight](#setheight)|Establece el alto de la ventana principal de Internet Explorer.|  
|[CHtmlView::SetLeft](#setleft)|Establece la posición horizontal de la ventana principal de Internet Explorer.|  
|[CHtmlView::SetMenuBar](#setmenubar)|Establece un valor para determinar si la barra de menús del control está visible. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::SetOffline](#setoffline)|Establece un valor para determinar si el control está sin conexión.|  
|[CHtmlView::SetRegisterAsBrowser](#setregisterasbrowser)|Establece un valor que indica si el control WebBrowser está registrado como un explorador de nivel superior para la resolución de nombres de destino.|  
|[CHtmlView::SetRegisterAsDropTarget](#setregisterasdroptarget)|Establece un valor que indica si el control WebBrowser está registrado como un destino para colocar para la navegación.|  
|[CHtmlView::SetSilent](#setsilent)|Establece un valor para determinar si el control mostrará cuadros de diálogo.|  
|[CHtmlView::SetStatusBar](#setstatusbar)|Establece un valor para determinar si la barra de estado de Internet Explorer está visible. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::SetTheaterMode](#settheatermode)|Establece un valor que indica si el control WebBrowser está en modo de pantalla completa.|  
|[CHtmlView::SetToolBar](#settoolbar)|Establece un valor para determinar si la barra de herramientas del control está visible. (El control WebBrowser se omite; solo Internet Explorer).|  
|[CHtmlView::SetTop](#settop)|Establece la posición vertical de la ventana principal de Internet Explorer.|  
|[CHtmlView::SetVisible](#setvisible)|Establece un valor que indica si el objeto está visible u oculto.|  
|[CHtmlView::SetWidth](#setwidth)|Establece el ancho de la ventana principal de Internet Explorer.|  
|[CHtmlView::Stop](#stop)|Detiene la apertura de un archivo.|  
  
## <a name="remarks"></a>Comentarios  
 El control WebBrowser es una ventana en la que el usuario puede examinar sitios en World Wide Web, así como carpetas en el sistema de archivos local y en una red. El control WebBrowser admite hipervínculos, navegación de localizador uniforme de recursos (URL) y mantiene una lista de historial.  
  
## <a name="using-the-chtmlview-class-in-an-mfc-application"></a>Uso de la clase CHtmlView en una aplicación MFC  
 En la aplicación de marco de trabajo MFC estándar (basada en SDI o MDI), el objeto de vista se deriva normalmente de un conjunto de clases especializado. Estas clases, todas ellas derivadas de `CView`, proporcionan funciones especializadas más allá de las que proporciona `CView`.  
  
 Al basar la clase de vista de la aplicación en `CHtmlView` se proporciona la vista con el control WebBrowser. De este modo, la aplicación se convierte de manera eficaz en un explorador web. El método preferido para crear una aplicación de estilo de explorador web es usar el Asistente para aplicaciones MFC y especificar `CHtmlView` como la clase de vista. Para obtener más información sobre la implementación y uso del control WebBrowser en aplicaciones MFC, vea [crear una aplicación estilo explorador Web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  El control ActiveX WebBrowser (y por tanto `CHtmlView`) solo está disponible para programas que se ejecutan en Windows NT 4.0 o versiones posteriores, con Internet Explorer 4.0 o posterior instalado.  
  
 `CHtmlView`está diseñado para aplicaciones que tienen acceso a la Web (o documentos HTML). La siguientes funciones miembro `CHtmlView` se aplican solo a la aplicación Internet Explorer. Estas funciones se ejecutarán correctamente en el control WebBrowser, pero no tendrán ningún efecto visible.  
  
- [GetAddressBar](#getaddressbar)  
  
- [GetFullName](#getfullname)  
  
- [GetStatusBar](#getstatusbar)  
  
- [SetAddressBar](#setaddressbar)  
  
- [SetFullScreen](#setfullscreen)  
  
- [SetMenuBar](#setmenubar)  
  
- [SetStatusBar](#setstatusbar)  
  
- [SetToolBar](#settoolbar)  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxhtml.h  
  
##  <a name="create"></a>CHtmlView::Create  
 Llame a esta función miembro para crear un control WebBrowser o un contenedor para Internet Explorer ejecutable.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszClassName`  
 Apunta a una cadena de caracteres terminada en null que los nombres de la clase de Windows. El nombre de clase puede ser cualquier nombre registrado con el [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) función global o **RegisterClass** función de Windows. Si **NULL**, utiliza el valor predeterminado predefinido [CFrameWnd](../../mfc/reference/cframewnd-class.md) atributos.  
  
 `lpszWindowName`  
 Apunta a una cadena de caracteres terminada en null que representa el nombre de la ventana.  
  
 `dwStyle`  
 Especifica los atributos de estilo de ventana. De forma predeterminada, el **WS_VISIBLE** y **WS_CHILD** establece los estilos de Windows.  
  
 `rect`  
 Una referencia a un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) estructura que especifica el tamaño y la posición de la ventana. El `rectDefault` valor permite a Windows especificar el tamaño y la posición de la nueva ventana.  
  
 `pParentWnd`  
 Puntero a la ventana primaria del control.  
  
 `nID`  
 El número de Id. de la vista. De forma predeterminada, **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Un puntero a un [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). **NULL** de forma predeterminada.  
  
##  <a name="createcontrolsite"></a>CHtmlView::CreateControlSite  
 Reemplazable usado para crear una instancia del sitio de control para hospedar un control en el formulario.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT nID,  
    REFCLSID clsid);
```  
  
### <a name="parameters"></a>Parámetros  
 `pContainer`  
 Un puntero a un [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) objeto que contiene el control.  
  
 `ppSite`  
 Un puntero a un puntero a un [COleControlSite](../../mfc/reference/colecontrolsite-class.md) objeto que proporciona el sitio para el control.  
  
 `nID`  
 El identificador del control se hospede.  
  
 `clsid`  
 El CLSID del control se aloje  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve TRUE si se ejecuta correctamente, FALSE en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Puede reemplazar esta función miembro para devolver una instancia de su propia clase de sitio del control.  
  
##  <a name="execformscommand"></a>CHtmlView::ExecFormsCommand  
 Ejecuta el comando especificado mediante el método `IOleCommandTarget::Exec` .  
  
```  
HRESULT ExecFormsCommand(
    DWORD dwCommandID,  
    VARIANT* pVarIn,  
    VARIANT* pVarOut);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwCommandID`  
 Comando que se va a ejecutar. Este comando debe pertenecer a la **CMDSETID3_Forms3** grupo.  
  
 *pVarIn*  
 Puntero a un **VARIANT** estructura que contiene los argumentos de entrada. Puede ser **NULL**.  
  
 *pVarOut*  
 Puntero a un **VARIANT** estructura para recibir el resultado del comando. Puede ser **NULL**.  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar. Para obtener una lista completa de los valores posibles, consulte [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Comentarios  
 **ExecFormsCommand** implementa el comportamiento de la [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) método.  
  
##  <a name="execwb"></a>CHtmlView::ExecWB  
 Llame a esta función miembro para ejecutar un comando en el WebBrowser o Internet Explorer.  
  
```  
void ExecWB(
    OLECMDID cmdID,  
    OLECMDEXECOPT cmdexecopt,  
    VARIANT* pvaIn,  
    VARIANT* pvaOut);
```  
  
### <a name="parameters"></a>Parámetros  
 `cmdID`  
 Comando para ejecutar.  
  
 *cmdexecopt*  
 Establecen las opciones para ejecutar el comando.  
  
 `pvaIn`  
 Una variante que se usa para especificar los argumentos de entrada de comando.  
  
 *pvaOut*  
 Una variante que se usa para especificar argumentos de salida del comando.  
  
### <a name="remarks"></a>Comentarios  
 Consulte [IWebBrowser2::ExecWB](https://msdn.microsoft.com/library/aa752117.aspx) en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getaddressbar"></a>CHtmlView::GetAddressBar  
 Llame a esta función miembro para recuperar la barra de direcciones de Internet Explorer.  
  
```  
BOOL GetAddressBar() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la barra de direcciones está visible; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="getapplication"></a>CHtmlView::GetApplication  
 Llame a esta función miembro para recuperar el objeto de automatización compatible con la aplicación que contiene el control WebBrowser.  
  
```  
LPDISPATCH GetApplication() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a la `IDispatch` interfaz del objeto de documento activo. Para obtener más información, consulte [implementa la interfaz IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getbusy"></a>CHtmlView::GetBusy  
 Llame a esta función miembro para determinar si se activa el control WebBrowser en una operación de descarga o exploración.  
  
```  
BOOL GetBusy() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el explorador web está ocupado; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getcontainer"></a>CHtmlView::GetContainer  
 Llame a esta función miembro para recuperar un objeto que se evalúa como el contenedor del explorador web.  
  
```  
LPDISPATCH GetContainer() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a la `IDispatch` interfaz del objeto de documento activo.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getfullname"></a>CHtmlView::GetFullName  
 Llame a esta función miembro para recuperar la ruta de acceso completa del archivo que se está mostrando actualmente Internet Explorer.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objeto que contiene la ruta de acceso y el nombre del archivo que se muestra actualmente. Si ninguna ruta de acceso y nombre de archivo existen, `GetFullName` devuelve una cadena vacía `CString`.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="getfullscreen"></a>CHtmlView::GetFullScreen  
 Llame a esta función miembro para determinar si el control WebBrowser está funcionando en modo de pantalla completa o en modo de ventana normal.  
  
```  
BOOL GetFullScreen() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el control WebBrowser está funcionando en modo de pantalla completa; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 En el modo de pantalla completa, se maximiza la ventana principal de Internet Explorer y se ocultan la barra de estado, la barra de herramientas, la barra de menús y la barra de título.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getheight"></a>CHtmlView::GetHeight  
 Llame a esta función miembro para recuperar el alto, en píxeles, de la ventana de marco del control WebBrowser.  
  
```  
long GetHeight() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Alto de ventana de marco de la del control en píxeles.  
  
##  <a name="gethtmldocument"></a>CHtmlView::GetHtmlDocument  
 Llame a esta función miembro para recuperar el documento HTML para el documento activo.  
  
```  
LPDISPATCH GetHtmlDocument() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a la `IDispatch` interfaz del objeto de documento activo.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getleft"></a>CHtmlView::GetLeft  
 Llame a esta función miembro para recuperar la distancia entre el borde interno izquierdo del control WebBrowser y el borde izquierdo de su contenedor.  
  
```  
long GetLeft() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La distancia del borde izquierdo, en píxeles.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getlocationname"></a>CHtmlView::GetLocationName  
 Llame a esta función miembro para obtener el nombre del recurso que se muestra en el control WebBrowser.  
  
```  
CString GetLocationName() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objeto que contiene el nombre del recurso se muestra actualmente en el control WebBrowser.  
  
### <a name="remarks"></a>Comentarios  
 Si el recurso es una página HTML en World Wide Web, el nombre es el título de la página. Si el recurso es una carpeta o archivo en el equipo local o de red, el nombre es la ruta UNC o ruta de acceso completa de la carpeta o archivo.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getlocationurl"></a>CHtmlView::GetLocationURL  
 Llame a esta función miembro para recuperar la dirección URL del recurso que se está mostrando actualmente el control WebBrowser.  
  
```  
CString GetLocationURL() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objeto que contiene la dirección URL del recurso que se muestra actualmente en el control WebBrowser.  
  
### <a name="remarks"></a>Comentarios  
 Si el recurso es una carpeta o archivo en el equipo local o de red, el nombre es la ruta UNC o ruta de acceso completa de la carpeta o archivo.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getmenubar"></a>CHtmlView::GetMenuBar  
 Llame a esta función miembro para determinar si está visible la barra de menús.  
  
```  
BOOL GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la barra de menús está visible; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getoffline"></a>CHtmlView::GetOffline  
 Llame a esta función miembro para determinar si el explorador web está funcionando sin conexión.  
  
```  
BOOL GetOffline() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el explorador web está sin conexión; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getparentbrowser"></a>CHtmlView::GetParentBrowser  
 Llame a esta función miembro para recuperar un puntero al objeto primario del control WebBrowser.  
  
```  
LPDISPATCH GetParentBrowser() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un puntero a la `IDispatch` interfaz del objeto que es el elemento primario del control WebBrowser.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getproperty"></a>CHtmlView::GetProperty  
 Llame a esta función miembro para obtener el valor de la propiedad asociada actualmente con el control.  
  
```  
BOOL GetProperty(
    LPCTSTR lpszProperty,  
    CString& strValue);  
  
COleVariant GetProperty(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszProperty`  
 Puntero a una cadena que contiene la propiedad que se va a recuperar.  
  
 `strValue`  
 Una referencia a un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objeto que recibe el valor actual de la propiedad.  
  
### <a name="return-value"></a>Valor devuelto  
 En la primera versión es distinto de cero si se completó correctamente; en caso contrario, es cero. En la segunda versión, una [COleVariant](../../mfc/reference/colevariant-class.md) objeto.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getreadystate"></a>CHtmlView::GetReadyState  
 Llame a esta función miembro para recuperar el estado del objeto WebBrowser listo.  
  
```  
READYSTATE GetReadyState() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) valor, tal como se describe en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getregisterasbrowser"></a>CHtmlView::GetRegisterAsBrowser  
 Llame a esta función miembro para determinar si el objeto WebBrowser está registrado como un explorador de nivel superior para la resolución de nombres de destino.  
  
```  
BOOL GetRegisterAsBrowser() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el explorador está registrado como un explorador de nivel superior; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getregisterasdroptarget"></a>CHtmlView::GetRegisterAsDropTarget  
 Llame a esta función miembro para determinar si el control WebBrowser se registra como un destino de colocación para la navegación.  
  
```  
BOOL GetRegisterAsDropTarget() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el explorador se registra como un destino de colocación; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getsilent"></a>CHtmlView::GetSilent  
 Llame a esta función miembro para determinar si los cuadros de diálogo se pueden mostrar en el control WebBrowser.  
  
```  
BOOL GetSilent() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si no se muestran cuadros de diálogo desde el control WebBrowser; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getsource"></a>CHtmlView::GetSource  
 Llame a esta función miembro para recuperar el código fuente HTML de la página web.  
  
```  
BOOL GetSource(CString& strRef);
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si es correcto. En caso contrario, es cero.  
  
### <a name="parameters"></a>Parámetros  
 `refString`  
 Un [CString](../../atl-mfc-shared/reference/cstringt-class.md) que contendrá el código fuente.  
  
### <a name="remarks"></a>Comentarios  
 Esta función es equivalente al comando "Ver origen" en Internet Explorer, salvo que se devuelve el código fuente en un `CString`.  
  
##  <a name="getstatusbar"></a>CHtmlView::GetStatusBar  
 Llame a esta función miembro para determinar si el control WebBrowser muestra una barra de estado.  
  
```  
BOOL GetStatusBar() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si se puede mostrar la barra de estado; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="gettheatermode"></a>CHtmlView::GetTheaterMode  
 Llame a esta función miembro para determinar si el explorador web está en modo de teatro.  
  
```  
BOOL GetTheaterMode() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el explorador web está en modo de teatro; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Cuando el explorador web está en modo de teatro, la ventana principal del explorador llena toda la pantalla, aparece una barra de herramientas con un conjunto mínimo de herramientas de exploración y la barra de estado aparece en la esquina superior derecha de la pantalla.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="gettoolbar"></a>CHtmlView::GetToolBar  
 Llame a esta función miembro para determinar si la barra de herramientas está visible.  
  
```  
int GetToolBar() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor que indica si está visible la barra de herramientas. Distinto de cero si la barra de herramientas está visible; en caso contrario, es cero.  
  
##  <a name="gettop"></a>CHtmlView::GetTop  
 Llame a esta función miembro para recuperar la coordenada de la pantalla del borde superior de la ventana principal del control WebBrowser.  
  
```  
long GetTop() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Dirección de una variable que recibe la coordenada de la pantalla del borde superior de la ventana principal.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="gettoplevelcontainer"></a>CHtmlView::GetTopLevelContainer  
 Llame a esta función miembro para determinar si Internet Explorer es el contenedor de nivel superior del control WebBrowser.  
  
```  
BOOL GetTopLevelContainer() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El contenedor es distinto de cero es el contenedor de nivel superior; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="gettype"></a>CHtmlView::GetType  
 Llame a esta función miembro para recuperar el nombre de tipo de documento activo contenido.  
  
```  
CString GetType() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objeto que contiene el nombre de tipo de documento activo contenido.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getvisible"></a>CHtmlView::GetVisible  
 Llame a esta función miembro para determinar si el objeto contenido está visible.  
  
```  
BOOL GetVisible() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el objeto es visible; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="getwidth"></a>CHtmlView::GetWidth  
 Recupera el ancho de la ventana principal de Internet Explorer.  
  
```  
long GetWidth() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 El ancho actual de la ventana, en píxeles.  
  
##  <a name="goback"></a>CHtmlView::GoBack  
 Navega hacia atrás un elemento en la lista del historial.  
  
```  
void GoBack();
```  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="goforward"></a>CHtmlView::GoForward  
 Navega hacia delante un elemento en la lista del historial.  
  
```  
void GoForward();
```  
  
##  <a name="gohome"></a>CHtmlView::GoHome  
 Navega a la página principal o de inicio actual especificada en el cuadro de diálogo Opciones de Internet de Internet Explorer o en el cuadro de diálogo Propiedades de Internet, al que se accede desde el Panel de control.  
  
```  
void GoHome();
```  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="gosearch"></a>CHtmlView::GoSearch  
 Navega hasta la actual página de búsqueda, como se especifica en el cuadro de diálogo Opciones de Internet de Internet Explorer o el cuadro de diálogo Propiedades de Internet tener acceso desde el Panel de Control.  
  
```  
void GoSearch();
```  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="loadfromresource"></a>CHtmlView::LoadFromResource  
 Llame a esta función miembro para cargar el recurso especificado en el control WebBrowser.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszResource`  
 Puntero a una cadena que contiene el nombre del recurso que se va a cargar.  
  
 `nRes`  
 Id. del búfer que contiene el nombre del recurso para cargar.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si es correcto. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="navigate"></a>CHtmlView::Navigate  
 Llame a esta función miembro para navegar hasta el recurso identificado por una dirección URL.  
  
```  
void Navigate(
    LPCTSTR URL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>Parámetros  
 *DIRECCIÓN URL*  
 Una cadena asignada por el llamador que contiene la dirección URL de destino o la ruta de acceso completa del archivo para mostrar.  
  
 `dwFlags`  
 Los indicadores de variable que especifica si se debe agregar el recurso a la lista del historial, si se lee o escribe desde la memoria caché y si desea mostrar el recurso en una nueva ventana. La variable puede ser una combinación de los valores definidos por el [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) (enumeración).  
  
 `lpszTargetFrameName`  
 Un puntero a una cadena que contiene el nombre del marco en el que se va a mostrar el recurso.  
  
 `lpszHeaders`  
 Puntero a un valor que especifica los encabezados HTTP para enviar al servidor. Estos encabezados se agregan a los encabezados de Internet Explorer de forma predeterminada. Los encabezados pueden especificar aspectos tales como la acción necesaria del servidor, el tipo de datos que se pasan al servidor o un código de estado. Este parámetro se omite si *URL* no es una dirección URL HTTP.  
  
 `lpvPostData`  
 Puntero a los datos que se envían con la transacción HTTP POST. Por ejemplo, la transacción POST se utiliza para enviar los datos recopilados por un formulario HTML. Si este parámetro no especifica ningún dato de envío, **Navigate** emite una transacción HTTP GET. Este parámetro se omite si *URL* no es una dirección URL HTTP.  
  
 `dwPostDataLen`  
 Datos que se envían con la transacción HTTP POST. Por ejemplo, la transacción POST se utiliza para enviar los datos recopilados por un formulario HTML. Si este parámetro no especifica ningún dato de envío, **Navigate** emite una transacción HTTP GET. Este parámetro se omite si *URL* no es una dirección URL HTTP.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="navigate2"></a>CHtmlView::Navigate2  
 Llame a esta función miembro para navegar al recurso identificado por una dirección URL o al archivo identificado mediante una ruta de acceso completa.  
  
```  
void Navigate2(
    LPITEMIDLIST pIDL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags,  
    CByteArray& baPostedData,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeader = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 *pIDL*  
 Un puntero a un [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) estructura.  
  
 `dwFlags`  
 Los indicadores de variable que especifica si se debe agregar el recurso a la lista del historial, si se lee o escribe desde la memoria caché y si desea mostrar el recurso en una nueva ventana. La variable puede ser una combinación de los valores definidos por el [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) (enumeración).  
  
 `lpszTargetFrameName`  
 Un puntero a una cadena que contiene el nombre del marco en el que se va a mostrar el recurso.  
  
 `lpszURL`  
 Puntero a una cadena que contiene la dirección URL.  
  
 `lpvPostData`  
 Datos que se envían con la transacción HTTP POST. Por ejemplo, la transacción POST se utiliza para enviar los datos recopilados por un formulario HTML. Si este parámetro no especifica ningún dato de envío `Navigate2` emite una transacción HTTP GET. Este parámetro se omite si *URL* no es una URL HTTP o HTTPS.  
  
 `dwPostDataLen`  
 Longitud en bytes de los datos que apunta el `lpvPostData` parámetro.  
  
 `lpszHeaders`  
 Puntero a un valor que especifica los encabezados HTTP o HTTPS para enviar al servidor. Estos encabezados se agregan a los encabezados de Internet Explorer de forma predeterminada. Los encabezados pueden especificar aspectos tales como la acción necesaria del servidor, el tipo de datos que se pasan al servidor o un código de estado. Este parámetro se omite si *URL* no es una URL HTTP o HTTPS.  
  
 `baPostedData`  
 Una referencia a un [CByteArray](../../mfc/reference/cbytearray-class.md) objeto.  
  
### <a name="remarks"></a>Comentarios  
 Esta función miembro amplía la **Navigate** función miembro mediante el soporte de exploración en carpetas especiales, como Mi PC y de escritorio que están representadas por el parámetro *pIDL*.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_MFCHtmlHttp&#7;](../../mfc/reference/codesnippet/cpp/chtmlview-class_1.cpp)]  
  
##  <a name="onbeforenavigate2"></a>CHtmlView::OnBeforeNavigate2  
 El marco de trabajo para hacer que un evento se desencadena antes de que tenga lugar un desplazamiento en el explorador web llama a esta función miembro.  
  
```  
virtual void OnBeforeNavigate2(
    LPCTSTR lpszURL,  
    DWORD nFlags,  
    LPCTSTR lpszTargetFrameName,  
    CByteArray& baPostedData,  
    LPCTSTR lpszHeaders,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszURL`  
 Puntero a una cadena que contiene la dirección URL de destino.  
  
 `nFlags`  
 Reservado para un uso futuro.  
  
 `lpszTargetFrameName`  
 Una cadena que contiene el nombre del marco en el que se va a mostrar el recurso o **NULL** si no se destina ningún marco con nombre para el recurso.  
  
 `baPostedData`  
 Una referencia a un `CByteArray` objeto que contiene los datos para enviar al servidor si se utiliza la transacción HTTP POST.  
  
 `lpszHeaders`  
 Puntero a una cadena que contiene los encabezados HTTP adicionales para enviar al servidor (sólo en la URL HTTP). Los encabezados pueden especificar aspectos tales como la acción necesaria del servidor, el tipo de datos que se pasan al servidor o un código de estado.  
  
 `pbCancel`  
 Puntero a una marca de cancelación. Una aplicación puede establecer este parámetro en distinto de cero para cancelar la operación de exploración o en cero para que pueda continuar.  
  
##  <a name="oncommandstatechange"></a>CHtmlView::OnCommandStateChange  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que ha cambiado el estado habilitado de un comando de explorador web.  
  
```  
virtual void OnCommandStateChange(
    long nCommand,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parámetros  
 *Ncomando*  
 Identificador del comando cuyo estado habilitado ha cambiado.  
  
 `bEnable`  
 Estado habilitado. Este parámetro es distinto de cero si el comando está habilitado, o cero si está deshabilitado.  
  
##  <a name="ondocumentcomplete"></a>CHtmlView::OnDocumentComplete  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que ha alcanzado un documento el `READYSTATE_COMPLETE` estado.  
  
```  
virtual void OnDocumentComplete(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszURL`  
 Un puntero a una cadena que se evalúa como la dirección URL, UNC del archivo nombre, o un PIDL (un puntero a una lista de identificador de elemento) que se navegó.  
  
### <a name="remarks"></a>Comentarios  
 No todos los fotogramas desencadenarán este evento, pero cada fotograma en el que se activa una [OnDownloadBegin](#ondownloadbegin) evento desencadenará correspondiente `OnDocumentComplete` eventos.  
  
 La dirección URL indicada por `lpszURL` puede ser diferente de la dirección URL que el explorador se ha indicado a navegar, ya que esta dirección URL es la dirección URL con formato canónico y completa. Por ejemplo, si una aplicación especifica una dirección URL de "www.microsoft.com" en una llamada a [Navigate](#navigate) o [Navigate2](#navigate2), la dirección URL pasada `OnNavigateComplete2` será "http://www.microsoft.com/". Además, si el servidor redirige el explorador a una dirección URL diferente, la dirección URL redirigida se refleja aquí.  
  
##  <a name="ondocwindowactivate"></a>CHtmlView::OnDocWindowActivate  
 Se llamada desde la implementación de Internet Explorer o MSHTML de **IOleInPlaceActiveObject::OnDocWindowActivate**, que notifica al objeto en contexto activo cuando la ventana de documento del contenedor se activa o desactiva.  
  
```  
virtual HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parámetros  
 `fActivate`  
 Indica el estado de la ventana de documento. Si este valor es distinto de cero, la ventana se activa. Si este valor es cero, la ventana se está desactivando.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnDocWindowActivate` para reaccionar ante los `OnDocWindowActivate` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="ondownloadbegin"></a>CHtmlView::OnDownloadBegin  
 Esta función miembro se llama el marco de trabajo para iniciar la descarga de un documento.  
  
```  
virtual void OnDownloadBegin();
```  
  
### <a name="remarks"></a>Comentarios  
 Este evento se desencadena poco después de la [OnBeforeNavigate2](#onbeforenavigate2) evento, a menos que se cancele la navegación. Cualquier animación o la indicación "ocupado" que debe mostrar el contenedor debe estar conectado a este evento.  
  
##  <a name="ondownloadcomplete"></a>CHtmlView::OnDownloadComplete  
 El marco de trabajo para indicar que una operación de navegación ha terminado, se ha detenido o no se pudo llama a esta función miembro.  
  
```  
virtual void OnDownloadComplete();
```  
  
##  <a name="onenablemodeless"></a>CHtmlView::OnEnableModeless  
 Se llama cuando Internet Explorer o MSHTML muestra la interfaz de usuario modal.  
  
```  
virtual HRESULT OnEnableModeless(BOOL fEnable);
```  
  
### <a name="parameters"></a>Parámetros  
 `fEnable`  
 Indica si los cuadros de diálogo no modal del host están habilitados o deshabilitados. Si este valor es distinto de cero, se habilitan los cuadros de diálogo no modal. Si este valor es cero, se deshabilitan los cuadros de diálogo no modal.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Habilita o deshabilita los cuadros de diálogo no modal cuando el contenedor se crea o destruye un cuadro de diálogo modal. Invalidar `OnEnableModeless` para reaccionar ante los `EnableModeless` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onfilterdataobject"></a>CHtmlView::OnFilterDataObject  
 Internet Explorer o MSHTML lo llaman en el host para permitir que el host reemplace el objeto de datos de Internet Explorer o MSHTML.  
  
```  
virtual HRESULT OnFilterDataObject(
    LPDATAOBJECT pDataObject,  
    LPDATAOBJECT* ppDataObject);
```  
  
### <a name="parameters"></a>Parámetros  
 `pDataObject`  
 Dirección de la [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) interfaz proporcionada por Internet Explorer o MSHTML.  
  
 *ppDataObject*  
 Dirección que recibe la `IDataObject` puntero de interfaz proporcionada por el host. El contenido de este parámetro siempre debe inicializarse a **NULL**, incluso si se produce un error en el método.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se reemplaza el objeto de datos, **S_FALSE** si no se reemplaza el objeto de datos, o un código de error definido por OLE si se produce un error.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnFilterDataObject` para reaccionar ante los `FilterDataObject` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onframewindowactivate"></a>CHtmlView::OnFrameWindowActivate  
 Llamar desde [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) para notificar al objeto cuando el contenedor del nivel superior, ventana de marco está activada o desactivada.  
  
```  
virtual HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parámetros  
 `fActivate`  
 Indica el estado de ventana de marco de nivel superior del contenedor. Si este valor es distinto de cero, la ventana se activa. Si este valor es cero, la ventana se está desactivando.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnFrameWindowActivate` para reaccionar ante los `OnFrameWindowActivate` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onfullscreen"></a>CHtmlView::OnFullScreen  
 El marco de trabajo llama a esta función miembro cuando el [pantalla completa](https://msdn.microsoft.com/library/aa752119.aspx) propiedad ha cambiado.  
  
```  
virtual void OnFullScreen(BOOL bFullScreen);
```  
  
### <a name="parameters"></a>Parámetros  
 *bFullScreen*  
 Distinto de cero si Internet Explorer está en modo de pantalla completa; en caso contrario, es cero.  
  
##  <a name="ongetdroptarget"></a>CHtmlView::OnGetDropTarget  
 Internet Explorer o MSHTML lo llaman cuando se usa como destino para colocar para permitir que el host proporcione un `IDropTarget`.  
  
```  
virtual HRESULT OnGetDropTarget(
    LPDROPTARGET pDropTarget,  
    LPDROPTARGET* ppDropTarget);
```  
  
### <a name="parameters"></a>Parámetros  
 `pDropTarget`  
 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Internet Explorer o MSHTML propone utilizar.  
  
 `ppDropTarget`  
 Dirección de la `IDropTarget` que recibe el `IDropTarget` el host desea proporcionar el puntero de interfaz.  
  
### <a name="return-value"></a>Valor devuelto  
 Consulte [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener una lista de códigos de retorno.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnGetDropTarget` para reaccionar ante los `GetDropTarget` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="ongetexternal"></a>CHtmlView::OnGetExternal  
 Internet Explorer o MSHTML lo llaman para obtener la interfaz `IDispatch` del host.  
  
```  
virtual HRESULT OnGetExternal(LPDISPATCH* lppDispatch);
```  
  
### <a name="parameters"></a>Parámetros  
 *lppDispatch*  
 Un puntero a la dirección que recibe la `IDispatch` el puntero de interfaz de la aplicación host. Si el host expone una interfaz de automatización, puede proporcionar una referencia a Internet Explorer o MSHTML mediante este parámetro. El contenido de este parámetro siempre debe inicializarse a **NULL**, incluso si se produce un error en el método.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnGetExternal` para reaccionar ante los `GetExternal` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="ongethostinfo"></a>CHtmlView::OnGetHostInfo  
 Recupera las capacidades de la interfaz de usuario del host de Internet Explorer o MSHTML.  
  
```  
virtual HRESULT OnGetHostInfo(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Parámetros  
 `pInfo`  
 Dirección de un [DOCHOSTUIINFO](https://msdn.microsoft.com/library/aa770044.aspx) estructura que recibe las capacidades de interfaz de usuario del host.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnGetHostInfo` para reaccionar ante los `GetHostInfo` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="ongetoptionkeypath"></a>CHtmlView::OnGetOptionKeyPath  
 Llame a esta función miembro para obtener la clave del registro bajo la que Internet Explorer o MSHTML almacena las preferencias del usuario.  
  
```  
virtual HRESULT OnGetOptionKeyPath(
    LPOLESTR* pchKey,  
    DWORD dwReserved);
```  
  
### <a name="parameters"></a>Parámetros  
 `pchKey`  
 Dirección de un `LPOLESTR` que recibe la cadena de la subclave de registro donde el host almacena sus opciones predeterminadas. Esta subclave se encontrarán en la clave HKEY_CURRENT_USER. Asignar esta memoria mediante [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727). La aplicación de llamada es responsable de liberar esta memoria mediante [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722). Este parámetro siempre debe inicializarse a **NULL**, incluso si se produce un error en el método.  
  
 `dwReserved`  
 Reservado para un uso futuro. No se están usando.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o **S_FALSE** en caso contrario. Si **S_FALSE**, Internet Explorer o MSHTML serán sus propias opciones de usuario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnGetOptionKeyPath` para reaccionar ante los `GetOptionKeyPath` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onhideui"></a>CHtmlView::OnHideUI  
 El marco de trabajo llama a esta función miembro cuando Internet Explorer o MSHTML quita sus menús y barras de herramientas.  
  
```  
virtual HRESULT OnHideUI();
```  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnHideUI` para reaccionar ante los `HideUI` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onmenubar"></a>CHtmlView::OnMenuBar  
 El marco de trabajo llama a esta función miembro cuando el [MenuBar](https://msdn.microsoft.com/library/aa752131.aspx) propiedad ha cambiado.  
  
```  
virtual void OnMenuBar(BOOL bMenuBar);
```  
  
### <a name="parameters"></a>Parámetros  
 *bMenuBar*  
 Es distinto de cero si la barra de menús de Internet Explorer está visible; en caso contrario, es cero.  
  
##  <a name="onnavigatecomplete2"></a>CHtmlView::OnNavigateComplete2  
 El marco de trabajo llama a esta función miembro al finalizar la navegación a un hipervínculo (en el elemento de una ventana o un conjunto de marcos).  
  
```  
virtual void OnNavigateComplete2(LPCTSTR strURL);
```  
  
### <a name="parameters"></a>Parámetros  
 *strURL*  
 Una expresión de cadena que se evalúa como la dirección URL, UNC nombre de archivo, o PIDL (un puntero a una lista de identificador de elemento) que se navegó.  
  
### <a name="remarks"></a>Comentarios  
 El parámetro de dirección URL puede ser un PIDL en el caso de una entidad de espacio de nombre de shell para el que no hay ninguna representación de dirección URL.  
  
 Tenga en cuenta que la dirección URL contenida en *strURL* puede ser diferente de la dirección URL que el explorador se ha indicado a navegar, ya que esta dirección URL es la dirección URL con formato canónico y completa. Por ejemplo, si una aplicación especifica una dirección URL de "www.microsoft.com" en una llamada a [Navigate](#navigate) o [Navigate2](#navigate2), la dirección URL pasada `OnNavigateComplete2` será "http://www.microsoft.com/". Además, si el servidor redirige el explorador a una dirección URL diferente, la dirección URL redirigida se refleja aquí.  
  
##  <a name="onnavigateerror"></a>CHtmlView::OnNavigateError  
 El marco de trabajo lo llama si la navegación a un hipervínculo no se realiza correctamente.  
  
```  
virtual void OnNavigateError(
    LPCTSTR lpszURL,  
    LPCTSTR lpszFrame,  
    DWORD dwError,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszURL`  
 La dirección URL para la que no se pudo navegación.  
  
 *lpszFrame*  
 El nombre del marco en el que el recurso está mostrada, o NULL si no se destina ningún marco con nombre para el recurso.  
  
 `dwError`  
 Un código de estado error, si está disponible. Para obtener una lista de los códigos de estado HTTP y HRESULT posibles, consulte [NavigateError códigos de estado de evento.](https://msdn.microsoft.com/library/aa768365.aspx)  
  
 `pbCancel`  
 Especifica si se debe cancelar la navegación a una página de error o cualquier otra búsqueda. Si **TRUE** (valor predeterminado), continúe con la navegación a una página de error o la búsqueda automática; si **FALSE**, cancelar la navegación a una página de error o la búsqueda automática.  
  
### <a name="remarks"></a>Comentarios  
 Invalide este método para proporcionar control de errores de exploración personalizada.  
  
 Para obtener más información, consulte [DWebBrowserEvents2::NavigateError](https://msdn.microsoft.com/library/aa768286.aspx)  
  
##  <a name="onnewwindow2"></a>CHtmlView::OnNewWindow2  
 El marco de trabajo llama a esta función miembro cuando es una nueva ventana que se crean para mostrar un recurso.  
  
```  
virtual void OnNewWindow2(
    LPDISPATCH* ppDisp,  
    BOOL* Cancel);
```  
  
### <a name="parameters"></a>Parámetros  
 `ppDisp`  
 Un puntero a un puntero de interfaz que, de manera opcional, recibe la `IDispatch` el puntero de interfaz de un nuevo objeto WebBrowser o Internet Explorer.  
  
 `Cancel`  
 Puntero a una marca de cancelación. Una aplicación puede establecer este parámetro en distinto de cero para cancelar la operación de exploración o en cero para que pueda continuar.  
  
### <a name="remarks"></a>Comentarios  
 Este evento es anterior a la creación de una nueva ventana desde el control WebBrowser.  
  
##  <a name="onprogresschange"></a>CHtmlView::OnProgressChange  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que se ha actualizado el progreso de una operación de descarga.  
  
```  
virtual void OnProgressChange(
    long nProgress,  
    long nProgressMax);
```  
  
### <a name="parameters"></a>Parámetros  
 *nProgress*  
 Cantidad de progreso total para mostrar, o -1 cuando progreso se completa.  
  
 *nProgressMax*  
 Valor máximo del curso.  
  
### <a name="remarks"></a>Comentarios  
 El contenedor puede utilizar la información proporcionada por este evento para mostrar el número de bytes descargados hasta el momento o para actualizar un indicador de progreso.  
  
##  <a name="onpropertychange"></a>CHtmlView::OnPropertyChange  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que [PutProperty](#putproperty) ha cambiado el valor de una propiedad.  
  
```  
virtual void OnPropertyChange(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszProperty`  
 Un puntero a una cadena que contiene el nombre de la propiedad.  
  
##  <a name="onquit"></a>CHtmlView::OnQuit  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que está lista para salir de la aplicación de Internet Explorer.  
  
```  
virtual void OnQuit();
```  
  
##  <a name="onresizeborder"></a>CHtmlView::OnResizeBorder  
 Invoca desde la implementación de Internet Explorer o MSHTML de [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), notifica el objeto que debe cambiar el tamaño de su espacio de borde.  
  
```  
virtual HRESULT OnResizeBorder(
    LPCRECT prcBorder,  
    LPOLEINPLACEUIWINDOW pUIWindow,  
    BOOL fFrameWindow);
```  
  
### <a name="parameters"></a>Parámetros  
 `prcBorder`  
 Nuevo rectángulo exterior para el espacio del borde.  
  
 `pUIWindow`  
 Puntero a la interfaz para el objeto de ventana de marco o documento cuyo borde se ha cambiado.  
  
 `fFrameWindow`  
 **TRUE** si la ventana de marco está llamando a [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), de lo contrario, **FALSE**.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnResizeBorder` para reaccionar ante los `ResizeBorder` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onshowcontextmenu"></a>CHtmlView::OnShowContextMenu  
 Se llama desde Internet Explorer o MSHTML cuando está a punto de mostrar el menú contextual.  
  
```  
virtual HRESULT OnShowContextMenu(
    DWORD dwID,  
    LPPOINT ppt,  
    LPUNKNOWN pcmdtReserved,  
    LPDISPATCH pdispReserved);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwID`  
 Identificador del menú contextual que aparecerá. Consulte **IDocHostUIHandler::ShowContextMenu** en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener una lista de valores.  
  
 `ppt`  
 Coordenadas de pantalla del menú.  
  
 `pcmdtReserved`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) interfaz que se usa para consultar el estado de comandos y ejecutar comandos en este objeto.  
  
 `pdispReserved`  
 Interfaz IDispatch del objeto en las coordenadas de pantalla. Esto permite a un host diferenciar objetos concretos para proporcionar un contexto más específica.  
  
### <a name="return-value"></a>Valor devuelto  
 Consulte [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener una lista de valores.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnShowContextMenu` para reaccionar ante los `ShowContextMenu` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onshowui"></a>CHtmlView::OnShowUI  
 Se llama antes de que Internet Explorer o MSHTML muestren sus menús y barras de herramientas.  
  
```  
virtual HRESULT OnShowUI(
    DWORD dwID,  
    LPOLEINPLACEACTIVEOBJECT pActiveObject,  
    LPOLECOMMANDTARGET pCommandTarget,  
    LPOLEINPLACEFRAME pFrame,  
    LPOLEINPLACEUIWINDOW pDoc);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwID`  
 Reservado para un uso futuro.  
  
 `pActiveObject`  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) interfaz del objeto activo.  
  
 `pCommandTarget`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) interfaz del objeto.  
  
 `pFrame`  
 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) interfaz del objeto. Esto es necesario para los menús y barras de herramientas.  
  
 `pDoc`  
 [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) interfaz para el objeto. Esto es necesario para las barras de herramientas.  
  
### <a name="return-value"></a>Valor devuelto  
 Consulte [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener una lista de valores.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnShowUI` para reaccionar ante los `ShowUI` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onstatusbar"></a>CHtmlView::OnStatusBar  
 El marco de trabajo llama a esta función miembro cuando el [StatusBar](https://msdn.microsoft.com/library/aa768270.aspx) propiedad ha cambiado.  
  
```  
virtual void OnStatusBar(BOOL bStatusBar);
```  
  
### <a name="parameters"></a>Parámetros  
 *bStatusBar*  
 Es distinto de cero si está visible la barra de estado de Internet Explorer o cero en caso contrario.  
  
##  <a name="onstatustextchange"></a>CHtmlView::OnStatusTextChange  
 Esta función miembro se llama el marco de trabajo para notificar a una aplicación que ha cambiado el texto de la barra de estado asociada con el control WebBrowser.  
  
```  
virtual void OnStatusTextChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszText`  
 Cadena que contiene el nuevo texto de la barra de estado.  
  
##  <a name="ontheatermode"></a>CHtmlView::OnTheaterMode  
 El marco de trabajo llama a esta función miembro cuando el [TheaterMode](https://msdn.microsoft.com/library/aa768273.aspx) propiedad ha cambiado.  
  
```  
virtual void OnTheaterMode(BOOL bTheaterMode);
```  
  
### <a name="parameters"></a>Parámetros  
 *bTheaterMode*  
 Distinto de cero si Internet Explorer está en modo de teatro; en caso contrario, es cero.  
  
##  <a name="ontitlechange"></a>CHtmlView::OnTitleChange  
 El marco de trabajo para notificar a una aplicación si el título de un documento en el control WebBrowser deja de estar disponible o cambios llama a esta función miembro.  
  
```  
virtual void OnTitleChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszText`  
 El título del documento nuevo.  
  
### <a name="remarks"></a>Comentarios  
 Para HTML, puede cambiar el título; mientras aún está descargando HTML, se establece la dirección URL del documento como el título. Después de que el título real (si existe) se analiza desde el código HTML, el título se cambia para reflejar el título real.  
  
##  <a name="ontoolbar"></a>CHtmlView::OnToolBar  
 El marco de trabajo llama a esta función miembro cuando el [barra de herramientas](https://msdn.microsoft.com/library/aa768274.aspx) propiedad ha cambiado.  
  
```  
virtual void OnToolBar(BOOL bToolBar);
```  
  
### <a name="parameters"></a>Parámetros  
 *bToolBar*  
 Es distinto de cero si está visible la barra de herramientas de Internet Explorer o cero en caso contrario.  
  
##  <a name="ontranslateaccelerator"></a>CHtmlView::OnTranslateAccelerator  
 Llama a Internet Explorer o MSHTML cuando [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) o [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) se llama para procesar mensajes de tecla de método abreviado de menú de cola de mensajes del contenedor.  
  
```  
virtual HRESULT OnTranslateAccelerator(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpMsg`  
 Señala el mensaje que deba ser traducido.  
  
 `pguidCmdGroup`  
 Identificador del grupo de comandos.  
  
 `nCmdID`  
 Identificador del comando.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o **S_FALSE** en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnTranslateAccelerator` para reaccionar ante los `TranslateAccelerator` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="ontranslateurl"></a>CHtmlView::OnTranslateUrl  
 Internet Explorer o MSHTML lo llaman para ofrecer al host la oportunidad de modificar la dirección URL que se va a cargar.  
  
```  
virtual HRESULT OnTranslateUrl(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwTranslate`  
 Reservado para un uso futuro.  
  
 `pchURLIn`  
 Dirección de una cadena proporcionada por Internet Explorer o MSHTML que representa la dirección URL que se debe traducir.  
  
 `ppchURLOut`  
 Dirección de un puntero a una cadena que recibe la dirección de la dirección URL traducida. El host asigna el búfer mediante el asignador de memoria de tareas. El contenido de este parámetro siempre debe inicializarse a **NULL**, incluso si no se traduce la dirección URL o se produce un error en el método.  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se ha traducido a la dirección URL, **S_FALSE** si la dirección URL no se ha traducido, o un código de error definido por OLE si se produjo un error.  
  
### <a name="remarks"></a>Comentarios  
 Invalidar `OnTranslateUrl` para reaccionar ante los `TranslateUrl` notificación del control de explorador Web de Microsoft. Consulte [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obtener más información.  
  
##  <a name="onupdateui"></a>CHtmlView::OnUpdateUI  
 Notifica al host que cambió el estado del comando.  
  
```  
virtual HRESULT OnUpdateUI();
```  
  
### <a name="return-value"></a>Valor devuelto  
 `S_OK`Si se realiza correctamente, o un código de error definido por OLE en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 El host debe actualizar el estado de los botones de barra de herramientas. Se llama a este método sin tener en cuenta el valor devuelto de `ShowUI`. Invalidar `OnUpdateUI` para reaccionar ante los `UpdateUI` notificación del control de explorador Web de Microsoft.  
  
##  <a name="onvisible"></a>CHtmlView::OnVisible  
 El marco de trabajo llama a esta función miembro cuando la ventana de WebBrowser se debe mostrar u ocultar.  
  
```  
virtual void OnVisible(BOOL bVisible);
```  
  
### <a name="parameters"></a>Parámetros  
 `bVisible`  
 Distinto de cero si el objeto es visible o cero en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Esto permite que la ventana de host de control de objeto se comporte de la misma manera que se comportaría la ventana de Internet Explorer.  
  
##  <a name="putproperty"></a>CHtmlView::PutProperty  
 Llame a esta función miembro para establecer la propiedad asociada a un objeto determinado.  
  
```  
void PutProperty(
    LPCTSTR lpszProperty,  
    const VARIANT& vtValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    double dValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    long lValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    LPCTSTR lpszValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    short nValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszProperty`  
 Una cadena que contiene la propiedad para establecer.  
  
 *vtValue*  
 El nuevo valor de la propiedad indicada por `lpszProperty`.  
  
 *lpszPropertyName*  
 Un puntero a una cadena que contiene el nombre de la propiedad para establecer.  
  
 *dValue*  
 Nuevo valor de la propiedad.  
  
 `lValue`  
 Nuevo valor de la propiedad.  
  
 `lpszValue`  
 Puntero a una cadena que contiene el nuevo valor de la propiedad.  
  
 `nValue`  
 Nuevo valor de la propiedad.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="queryformscommand"></a>CHtmlView::QueryFormsCommand  
 Consulta el estado de uno o más comandos generados por eventos de interfaz de usuario.  
  
```  
HRESULT QueryFormsCommand(
    DWORD dwCommandID,  
    BOOL* pbSupported,  
    BOOL* pbEnabled,  
    BOOL* pbChecked);
```  
  
### <a name="parameters"></a>Parámetros  
 `dwCommandID`  
 El identificador del comando que se va a consultar.  
  
 *pbSupported*  
 Un puntero a un **BOOL** if especificando el comando (identificado por `dwCommandID`) es compatible. Si es TRUE, se admite el comando; de lo contrario, FALSE.  
  
 `pbEnabled`  
 Un puntero a un **BOOL** if especificando el comando (identificado por `dwCommandID`) está habilitada. Si es TRUE, se admite el comando; de lo contrario, FALSE.  
  
 *pbChecked*  
 Un puntero a un **BOOL** if especificando el comando (identificado por `dwCommandID`) está activada. Si es TRUE, se admite el comando; de lo contrario, FALSE.  
  
### <a name="return-value"></a>Valor devuelto  
 Un valor `HRESULT` estándar. Para obtener una lista completa de los valores posibles, consulte [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Comentarios  
 `QueryFormsCommand`implementa el comportamiento de la [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) método.  
  
##  <a name="querystatuswb"></a>CHtmlView::QueryStatusWB  
 Llame a esta función miembro para consultar el estado de un comando.  
  
```  
OLECMDF QueryStatusWB(OLECMDID cmdID) const;  
```  
  
### <a name="parameters"></a>Parámetros  
 `cmdID`  
 El [OLECMDID](http://msdn.microsoft.com/library/windows/desktop/ms691264) valor del comando para el que el llamador necesita información de estado.  
  
### <a name="return-value"></a>Valor devuelto  
 La dirección de la [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) valor que recibe el estado del comando.  
  
### <a name="remarks"></a>Comentarios  
 `QueryStatusWB`implementa el comportamiento de la [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) método.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="refresh"></a>CHtmlView::Refresh  
 Vuelve a cargar la dirección URL o un archivo que se está mostrando actualmente el explorador web.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Comentarios  
 **Actualizar** no contiene parámetros para establecer el nivel de actualización.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="refresh2"></a>CHtmlView::Refresh2  
 Vuelve a cargar el archivo que se está mostrando actualmente Internet Explorer.  
  
```  
void Refresh2(int nLevel);
```  
  
### <a name="parameters"></a>Parámetros  
 `nLevel`  
 La dirección de la variable que especifica el nivel de actualización. Las posibles variables se definen en [RefreshConstants](https://msdn.microsoft.com/library/aa768363.aspx), en la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Comentarios  
 A diferencia de [actualizar](#refresh), `Refresh2` contiene un parámetro que especifica el nivel de actualización.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setaddressbar"></a>CHtmlView::SetAddressBar  
 Llame a esta función miembro para mostrar u ocultar la barra de direcciones del objeto de Internet Explorer.  
  
```  
void SetAddressBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero para mostrar la barra de direcciones; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="setfullscreen"></a>CHtmlView::SetFullScreen  
 Llame a esta función miembro para configurar Internet Explorer para el modo de ventana de pantalla completa o normal.  
  
```  
void SetFullScreen(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero para el modo de pantalla completa; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 En el modo de pantalla completa, se maximiza la ventana principal de Internet Explorer y se ocultan la barra de estado, la barra de herramientas, la barra de menús y la barra de título.  
  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="setheight"></a>CHtmlView::SetHeight  
 Llame a esta función miembro para establecer el alto de la ventana principal de Internet Explorer.  
  
```  
void SetHeight(long nNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewValue`  
 Alto, en píxeles, de la ventana principal.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setleft"></a>CHtmlView::SetLeft  
 Establece la posición horizontal de la ventana principal de Internet Explorer.  
  
```  
void SetLeft(long nNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewValue`  
 Coordenadas de pantalla del borde izquierdo de la ventana principal.  
  
##  <a name="setmenubar"></a>CHtmlView::SetMenuBar  
 Llame a esta función miembro para mostrar u ocultar la barra de menús de Internet Explorer.  
  
```  
void SetMenuBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero para mostrar la barra de menús; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="setoffline"></a>CHtmlView::SetOffline  
 Llame a esta función miembro para establecer un valor que indica si el control WebBrowser está funcionando en modo sin conexión.  
  
```  
void SetOffline(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero para leer desde la memoria caché local; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 En modo sin conexión, el explorador lee las páginas HTML de la memoria caché local en lugar de desde el documento de origen.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setregisterasbrowser"></a>CHtmlView::SetRegisterAsBrowser  
 Llame a esta función miembro para establecer un valor que indica si el control WebBrowser está registrado como un explorador de nivel superior para la resolución de nombres de destino.  
  
```  
void SetRegisterAsBrowser(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Determina si Internet Explorer está registrado como un explorador de nivel superior. Si es distinto de cero, el explorador web está registrado como un explorador de nivel superior; Si es cero, no es un explorador de nivel superior. El valor predeterminado es cero.  
  
### <a name="remarks"></a>Comentarios  
 Un explorador de nivel superior es el explorador en el registro como explorador predeterminado.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setregisterasdroptarget"></a>CHtmlView::SetRegisterAsDropTarget  
 Llame a esta función miembro para establecer un valor que indica si el control WebBrowser se registra como un destino de colocación para la navegación.  
  
```  
void SetRegisterAsDropTarget(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Determina si el control WebBrowser se registra como un destino de colocación para la navegación. Si es distinto de cero, el objeto está registrado como un destino de colocación; Si es cero, no es un destino de colocación.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setsilent"></a>CHtmlView::SetSilent  
 Llame a esta función miembro para establecer un valor que indica si se pueden mostrar los cuadros de diálogo.  
  
```  
void SetSilent(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Si es distinto de cero, no se mostrará cuadros de diálogo; Si es cero, se mostrará cuadros de diálogo. El valor predeterminado es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setstatusbar"></a>CHtmlView::SetStatusBar  
 Llame a esta función miembro para mostrar la barra de estado.  
  
```  
void SetStatusBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero si la barra de estado está visible; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="settheatermode"></a>CHtmlView::SetTheaterMode  
 Llame a esta función miembro para establecer un valor que indica si el control WebBrowser está en modo de teatro.  
  
```  
void SetTheaterMode(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Es distinto de cero para establecer el control WebBrowser en modo de teatro; en caso contrario, es cero. El valor predeterminado es cero.  
  
### <a name="remarks"></a>Comentarios  
 Cuando el explorador web está en modo de teatro, la ventana principal del explorador llena toda la pantalla, aparece una barra de herramientas con un conjunto mínimo de herramientas de exploración y la barra de estado aparece en la esquina superior derecha de la pantalla.  
  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="settoolbar"></a>CHtmlView::SetToolBar  
 Llame a esta función miembro para mostrar u ocultar la barra de herramientas de Internet Explorer.  
  
```  
void SetToolBar(int nNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewValue`  
 Indica si se debe mostrar la barra de herramientas. Es distinto de cero si la barra de herramientas se puede mostrar; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer. Si utiliza esta llamada con un control WebBrowser, no devolverá ningún error, pero omitirá esta llamada.  
  
##  <a name="settop"></a>CHtmlView::SetTop  
 Llame a esta función miembro para establecer la distancia entre el borde interno superior del control WebBrowser y el borde superior de su contenedor  
  
```  
void SetTop(long nNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewValue`  
 Coordenadas de pantalla del borde superior de la ventana principal.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setvisible"></a>CHtmlView::SetVisible  
 Llame a esta función miembro para establecer el estado de visibilidad del control WebBrowser.  
  
```  
void SetVisible(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `bNewValue`  
 Distinto de cero si el control es visible; en caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
##  <a name="setwidth"></a>CHtmlView::SetWidth  
 Establece el ancho de la ventana principal de Internet Explorer.  
  
```  
void SetWidth(long nNewValue);
```  
  
### <a name="parameters"></a>Parámetros  
 `nNewValue`  
 El ancho, en píxeles, de la ventana principal de Internet Explorer.  
  
##  <a name="stop"></a>CHtmlView::Stop  
 Llame a esta función miembro para cancelar cualquier navegación pendiente o descargar la operación y detener los elementos de página dinámicos, como sonidos de fondo y animación.  
  
```  
void Stop();
```  
  
### <a name="remarks"></a>Comentarios  
 Se aplica a Internet Explorer y WebBrowser.  
  
## <a name="see-also"></a>Vea también  
 [Este ejemplo de MFC](../../visual-cpp-samples.md)   
 [Clase CFormView](../../mfc/reference/cformview-class.md)   
 [Gráfico de jerarquía](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)

