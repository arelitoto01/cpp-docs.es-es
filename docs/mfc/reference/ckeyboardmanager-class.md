---
title: Clase CKeyboardManager | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager class
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bbe12d2bf4af0008233df25e09f09008c402ee7f
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyboardmanager-class"></a>Clase CKeyboardManager
Administra las tablas de teclas de método abreviado de la ventana de marco principal y las ventanas de marco secundarias.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|||  
|-|-|  
|Nombre|Descripción|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Construye un objeto `CKeyboardManager`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|||  
|-|-|  
|Nombre|Descripción|  
|[CKeyboardManager::CleanUp](#cleanup)|Borra las tablas de teclas de acceso directo.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Recupera la tecla de método abreviado predeterminado para el comando especificado y la ventana.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Determina si una tecla se controla mediante la tabla de aceleradores.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Indica si un carácter imprimible.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Indica si los menús Mostrar todas las teclas de método abreviado para un comando o sólo la tecla de método abreviado de forma predeterminada.|  
|[CKeyboardManager::LoadState](#loadstate)|Carga las tablas de teclas de acceso directo desde el registro de Windows.|  
|[CKeyboardManager::ResetAll](#resetall)|Vuelve a cargar las tablas de clave de acceso directo desde el recurso de aplicación.|  
|[CKeyboardManager::SaveState](#savestate)|Guarda el acceso directo de las tablas de clave al registro de Windows.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Especifica si el marco de trabajo muestra todas las teclas de método abreviado para todos los comandos o un único método abreviado para cada comando. Este método no afecta a los comandos que tienen sólo una tecla de método abreviado.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Convierte un carácter en su registro superior.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Actualiza una tabla de la clave de acceso directo con una nueva tabla de clave de acceso directo.|  
  
## <a name="remarks"></a>Comentarios  
 Los miembros de esta clase permiten guardar y cargar las tablas de teclas de método abreviado para el registro de Windows, use una plantilla para actualizar las tablas de teclas de acceso directo y buscar la tecla de método abreviado predeterminada de un comando en una ventana de marco. Además, la `CKeyboardManager` objeto le permite controlar cómo se muestran las teclas de método abreviado para el usuario.  
  
 No debería crear un `CKeyboardManager` objeto manualmente. Se creará automáticamente por el marco de la aplicación. Sin embargo, debe llamar a [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) durante el proceso de inicialización de la aplicación. Para obtener un puntero al administrador de teclado para la aplicación, llame a [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recuperar un puntero a un `CKeyboardManager` objeto a partir de un `CWinAppEx` clase y cómo mostrar todas las teclas de método abreviado asociadas a los comandos de menú. Este fragmento de código forma parte de la [ejemplo Custom Pages](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&#5;](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 Construye un objeto `CKeyboardManager`.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Comentarios  
 En la mayoría de los casos, no es necesario crear un `CKeyboardManager` directamente. De forma predeterminada, el marco de trabajo crea uno automáticamente. Para obtener un puntero a la `CKeyboardManager`, llame a [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Si crea uno manualmente, debe inicializar con el método [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>CKeyboardManager::CleanUp  
 Libera el `CKeyboardManager` recursos y borra todas las asignaciones de teclas de método abreviado.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Comentarios  
 Para obtener más información acerca de teclas de método abreviado, vea [personalización del teclado y Mouse](../../mfc/keyboard-and-mouse-customization.md).  
  
 No es necesario llamar a esta función cuando se cierra la aplicación porque el marco de trabajo lo llama automáticamente durante la salida de la aplicación.  
  
##  <a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
 Recupera la tecla de método abreviado predeterminado para el comando especificado y la ventana.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `uiCmd`  
 Identificador del comando.  
  
 [out] `str`  
 Referencia a un objeto `CString`.  
  
 [in] `pWndFrame`  
 Puntero a una ventana de marco.  
  
 [in] `bIsDefaultFrame`  
 Especifica si la ventana de marco es la ventana de marco de forma predeterminada.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si se encuentra el acceso directo; en caso contrario, 0.  
  
### <a name="remarks"></a>Comentarios  
 Este método busca el comando especificado por `uiCmd` y recupera la tecla de método abreviado de forma predeterminada. A continuación, el método toma la cadena asociada a esta tecla de método abreviado y escribe el valor para el `str` parámetro.  
  
##  <a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
 Determina si la clave especificada se controla mediante la [CKeyboardManager clase](../../mfc/reference/ckeyboardmanager-class.md).  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parámetros  
  
|||  
|-|-|  
|Parámetro|Descripción|  
|[in] `nKey`|Clave que se va a comprobar.|  
|[in] `fVirt`|Especifica el comportamiento de la tecla de método abreviado. Para obtener una lista de valores posibles, consulte [estructura de aceleración](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Una ventana de marco. Este método determina si una tecla de método abreviado se trata en este marco.|  
|[in] `bIsDefaultFrame`|Un parámetro booleano que indica si `pWndFrame` es la ventana de marco de forma predeterminada.|  
  
### <a name="return-value"></a>Valor devuelto  
 `TRUE`Si se controla la tecla de método abreviado. `FALSE`Si no se controla la clave o si `pWndFrame` es `NULL`.  
  
### <a name="remarks"></a>Comentarios  
 Los parámetros de entrada deben coincidir con la entrada en la tabla de aceleradores tanto para `nKey` y `fVirt` para determinar si una tecla de método abreviado se controla en `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 Indica si un carácter imprimible.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parámetros  
  
|||  
|-|-|  
|Parámetro|Descripción|  
|[in] `nChar`|El carácter que comprueba este método.|  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si el carácter imprimible, cero si no lo está.  
  
### <a name="remarks"></a>Comentarios  
 Este método produce un error si una llamada a [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) se produce un error.  
  
##  <a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 Indica si los menús Mostrar todas las teclas de método abreviado asociadas a los comandos de menú o sólo las teclas de método abreviado de forma predeterminada.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si la aplicación enumera todas las teclas de método abreviado para comandos de menú; 0 si la aplicación muestra solo teclas de método abreviado de forma predeterminada.  
  
### <a name="remarks"></a>Comentarios  
 La aplicación muestra las teclas de método abreviado para los comandos de menú en la barra de menús. Utilice la función [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) para controlar si la aplicación muestra las teclas de método abreviado o simplemente las teclas de método abreviado.  
  
##  <a name="loadstate"></a>CKeyboardManager::LoadState  
 Carga las tablas de teclas de acceso directo desde el registro de Windows.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `lpszProfileName`  
 La ruta de acceso del registro donde `CKeyboardManager` se guardan los datos.  
  
 [in] `pDefaultFrame`  
 Puntero a una ventana de marco que se usará como la ventana de forma predeterminada.  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el estado se carga correctamente o 0 en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Si el `lpszProfileName` parámetro es `NULL`, este método comprueba la ubicación de registro predeterminada de `CKeyboardManager` datos. Se especifica la ubicación del registro de forma predeterminada por la [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Los datos deben escribirse previamente con el método [CKeyboardManager::SaveState](#savestate).  
  
 Si no especifica una ventana de forma predeterminada, se utilizará la ventana de marco principal de la aplicación.  
  
##  <a name="resetall"></a>CKeyboardManager::ResetAll  
 Vuelve a cargar las tablas de clave de acceso directo desde el recurso de aplicación.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Comentarios  
 Esta función borra los accesos directos que se almacenan en la `CKeyboardManager` instancia. A continuación, volverá a cargar el estado del Administrador de teclado desde el recurso de aplicación.  
  
##  <a name="savestate"></a>CKeyboardManager::SaveState  
 Guarda el acceso directo de las tablas de clave al registro de Windows.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `lpszProfileName`  
 La ruta de acceso del registro para guardar la `CKeyboardManager` estado.  
  
 [in] `pDefaultFrame`  
 Puntero a una ventana de marco que se convierte en la ventana de forma predeterminada.  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el estado del Administrador de teclado se guardó correctamente, o 0 en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 Si el `lpszProfileName` parámetro es `NULL`, escribirá este método la `CKeyboardManager` el estado de la ubicación predeterminada especificada por el [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Si especifica una ubicación, puede cargar los datos más adelante mediante el método [CKeyboardManager::LoadState](#loadstate).  
  
 Si no especifica una ventana de forma predeterminada, la ventana de marco principal se utilizará como la ventana de forma predeterminada.  
  
##  <a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 Muestra todas las teclas de método abreviado asociadas a los comandos de menú.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `bShowAll`  
 Si `true`, se mostrarán todas las teclas de método abreviado. Si `false`, se mostrará la primera tecla de método abreviado.  
  
 [in] `lpszDelimiter`  
 Una cadena para insertar entre las teclas de método abreviado. Este delimitador no tiene ningún efecto si sólo se muestra una tecla de método abreviado.  
  
### <a name="remarks"></a>Comentarios  
 De forma predeterminada, si un comando tiene más de una tecla de método abreviado asociada, se mostrará la primera tecla de método abreviado. Esta función le permite enumerar todas las teclas de método abreviado asociadas con todos los comandos.  
  
 Teclas de método abreviado se mostrará junto al comando en la barra de menús. Si se muestran las teclas de método abreviado, la cadena proporcionada por `lpszDelimiter` teclas de método abreviado individuales para separar.  
  
##  <a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 Convierte un carácter en su registro superior.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `nChar`  
 Carácter que se va a convertir.  
  
### <a name="return-value"></a>Valor devuelto  
 El carácter que es el registro superior del parámetro de entrada.  
  
##  <a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
 Actualiza una tabla de la clave de acceso directo con una nueva tabla de clave de acceso directo.  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parámetros  
 [in] `pTemplate`  
 Puntero a una plantilla de documento.  
  
 [in] `lpAccel`  
 Puntero a la nueva tecla de método abreviado.  
  
 [in] `nSize`  
 El tamaño de la nueva tabla de acceso directo.  
  
 [in] `pDefaultFrame`  
 Puntero a la ventana de marco de forma predeterminada.  
  
 [in] `hAccelNew`  
 Identificador de la nueva tabla de acceso directo.  
  
### <a name="return-value"></a>Valor devuelto  
 Distinto de cero si el método es correcto; en caso contrario, 0.  
  
### <a name="remarks"></a>Comentarios  
 Utilice esta función para reemplazar la tabla de acceso directo existente con nuevas teclas de método abreviado para varios objetos de ventana de marco. La función recibe una plantilla de documento como parámetro para obtener acceso a todos los objetos de ventana de marco conectado a la plantilla de documento determinado.  
  
## <a name="see-also"></a>Vea también  
 [Gráfico de jerarquía](../../mfc/hierarchy-chart.md)   
 [Clases](../../mfc/reference/mfc-classes.md)   
 [Clase CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Personalización del teclado y Mouse](../../mfc/keyboard-and-mouse-customization.md)



