---
title: Clase de CAtlModule | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>Clase de CAtlModule
Esta clase proporciona métodos utilizados por varias clases de módulo ATL.  
  
## <a name="syntax"></a>Sintaxis  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|El constructor.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|Destructor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Invalide este método para agregar parámetros a la asignación de reemplazo del componente de registro de ATL (registrador).|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Agrega una nueva función que se llama cuando finaliza el módulo.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Devuelve el puntero de interfaz Global.|  
|[CAtlModule::GetLockCount](#getlockcount)|Devuelve el recuento de bloqueos.|  
|[CAtlModule::Lock](#lock)|Incrementa el recuento de bloqueos.|  
|[CAtlModule::Term](#term)|Libera a todos los miembros de datos.|  
|[CAtlModule::Unlock](#unlock)|Reduce el recuento de bloqueos.|  
|[CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced)|Ejecuta la secuencia de comandos contenida en un recurso para registrar o anular el registro de un objeto especificado.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Se llama a este método `UpdateRegistryFromResourceD` para realizar la actualización del registro.|  
|[CAtlModule:: UpdateRegistryFromResourceS](#updateregistryfromresources)|Ejecuta la secuencia de comandos contenida en un recurso para registrar o anular el registro de un objeto especificado. Este método se vincula estáticamente al componente de registro de ATL.|  
  
### <a name="public-data-members"></a>Miembros de datos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Contiene el GUID del módulo actual.|  
|[CAtlModule::m_pGIT](#m_pgit)|Puntero a la tabla de interfaz Global.|  
  
## <a name="remarks"></a>Comentarios  
 Esta clase es utilizada por [CAtlDllModuleT clase](../../atl/reference/catldllmodulet-class.md), [clase CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), y [clase CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) para proporcionar compatibilidad con aplicaciones de DLL, EXE aplicaciones y servicios de Windows, respectivamente.  
  
 Para obtener más información sobre los módulos de ATL, vea [clases de módulo ATL](../../atl/atl-module-classes.md).  
  
 Esta clase reemplaza la obsoleta [CComModule (clase)](../../atl/reference/ccommodule-class.md) utilizado en versiones anteriores de ATL.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 Invalide este método para agregar parámetros a la asignación de reemplazo del componente de registro de ATL (registrador).  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parámetros  
 *pRegistrar*  
 Reservado.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o error HRESULT en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Parámetros reemplazables permiten que un cliente del registrador especificar los datos de tiempo de ejecución. Para ello, el registrador mantiene un mapa de reemplazo en el que escribe los valores asociados a los parámetros reemplazables en su secuencia de comandos. El registrador realiza estas entradas en tiempo de ejecución.  
  
 Vea el tema [utilizar parámetros reemplazables (el preprocesador del registrador)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) para obtener más detalles.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 Agrega una nueva función que se llama cuando finaliza el módulo.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 *pFunc*  
 Puntero a función que se va a agregar.  
  
 `dw`  
 Datos definidos por el usuario, se pasa a la función.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o error HRESULT en caso de error.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 El constructor.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Comentarios  
 Inicializa a los miembros de datos e inicia una sección crítica alrededor de subproceso del módulo.  
  
##  <a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 Destructor.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Comentarios  
 Libera a todos los miembros de datos.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Recupera un puntero a la tabla de interfaz Global.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `ppGIT`  
 Puntero a la variable que recibirá el puntero a la tabla de interfaz Global.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o un código de error en caso de error. Si se devuelve E_POINTER `ppGIT` es igual a NULL.  
  
### <a name="remarks"></a>Comentarios  
 Si no existe el objeto de la tabla de interfaz Global, se crea y su dirección se almacena en la variable miembro [CAtlModule::m_pGIT](#m_pgit).  
  
 En compilaciones de depuración, se producirá un error de aserción si `ppGIT` es igual a NULL, o si no se puede obtener el puntero de la tabla de interfaz Global.  
  
 Consulte [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) para obtener información sobre la tabla de interfaz Global.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 Devuelve el recuento de bloqueos.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el recuento de bloqueos. Este valor puede ser útil para el diagnóstico y depuración.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 Incrementa el recuento de bloqueos.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Incrementa el recuento de bloqueos y devuelve el valor actualizado. Este valor puede ser útil para el diagnóstico y depuración.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 Contiene el GUID del módulo actual.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 Puntero a la tabla de interfaz Global.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 Libera a todos los miembros de datos.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Comentarios  
 Libera a todos los miembros de datos. El destructor llama a este método.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 Reduce el recuento de bloqueos.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Disminuye el recuento de bloqueos y devuelve el valor actualizado. Este valor puede ser útil para el diagnóstico y depuración.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule:: UpdateRegistryFromResourceD  
 Ejecuta la secuencia de comandos contenida en un recurso para registrar o anular el registro de un objeto especificado.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszRes`  
 Un nombre de recurso.  
  
 `nResID`  
 Un identificador de recurso.  
  
 `bRegister`  
 **TRUE** si es necesario registrar el objeto; **FALSE** en caso contrario.  
  
 `pMapEntries`  
 Puntero al mapa de reemplazo almacenar valores asociados a los parámetros reemplazables de la secuencia de comandos. ATL utiliza automáticamente % MODULE %. Para usar parámetros reemplazables adicionales, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). De lo contrario, utilice la **NULL** valor predeterminado.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o error HRESULT en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Ejecuta la secuencia de comandos contenida en el recurso especificado por *lpszRes o nResID*. Si `bRegister` es **TRUE**, este método registra el objeto en el registro del sistema; de lo contrario, quita el objeto desde el registro.  
  
 Para vincular estáticamente el componente de registro de ATL (registrador), consulte [CAtlModule:: UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Este método llama a [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) y [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 Se llama a este método `UpdateRegistryFromResourceD` para realizar la actualización del registro.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `lpszRes`  
 Un nombre de recurso.  
  
 `bRegister`  
 Indica si el objeto se debe registrar.  
  
 `pMapEntries`  
 Puntero al mapa de reemplazo almacenar valores asociados a los parámetros reemplazables de la secuencia de comandos. ATL utiliza automáticamente % MODULE %. Para usar parámetros reemplazables adicionales, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). De lo contrario, utilice la **NULL** valor predeterminado.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o error HRESULT en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Este método proporciona la implementación de [CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>CAtlModule:: UpdateRegistryFromResourceS  
 Ejecuta la secuencia de comandos contenida en un recurso para registrar o anular el registro de un objeto especificado. Este método se vincula estáticamente al componente de registro de ATL.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `nResID`  
 Un identificador de recurso.  
  
 `lpszRes`  
 Un nombre de recurso.  
  
 `bRegister`  
 Indica si se debe registrar el script de recursos.  
  
 `pMapEntries`  
 Puntero al mapa de reemplazo almacenar valores asociados a los parámetros reemplazables de la secuencia de comandos. ATL utiliza automáticamente % MODULE %. Para usar parámetros reemplazables adicionales, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). De lo contrario, utilice la **NULL** valor predeterminado.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK en caso de éxito o error HRESULT en caso de error.  
  
### <a name="remarks"></a>Comentarios  
 Similar a [CAtlModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced) excepto `CAtlModule::UpdateRegistryFromResourceS` crea un vínculo estático con el componente de registro de ATL (registrador).  
  
## <a name="see-also"></a>Vea también  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Información general de la clase](../../atl/atl-class-overview.md)   
 [Clases de módulo](../../atl/atl-module-classes.md)   
 [Componente de registro (registrador)](../../atl/atl-registry-component-registrar.md)  
