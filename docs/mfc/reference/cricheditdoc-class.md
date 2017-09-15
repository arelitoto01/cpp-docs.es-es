---
title: CRichEditDoc (clase) | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc (clase)
Con [CRichEditView](../../mfc/reference/cricheditview-class.md) y [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), proporciona la funcionalidad del control rich Edit. dentro del contexto de la arquitectura de vista de documento de MFC.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Se llama para realizar la limpieza del documento.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Indica si la secuencia de entrada y salida deben incluir información de formato.|  
|[CRichEditDoc::GetView](#getview)|Recupera los tokens [CRichEditView](../../mfc/reference/cricheditview-class.md) objeto.|  
  
### <a name="public-data-members"></a>Miembros de datos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CRichEditDoc:: M_brtf](#m_brtf)|Indica si la E/S de secuencia deben incluir formato.|  
  
## <a name="remarks"></a>Comentarios  
 Un "control rich edit" es una ventana en la que el usuario puede escribir y editar texto. El texto se puede asignar caracteres y el formato de párrafo y puede incluir objetos OLE incrustados. Los controles Rich edit proporcionan una interfaz de programación para dar formato al texto. Sin embargo, una aplicación debe implementar los componentes de interfaz de usuario necesarios para realizar operaciones de formato disponibles para el usuario.  
  
 `CRichEditView`mantiene el texto y la característica de formato de texto. `CRichEditDoc`mantiene la lista de elementos de cliente que están en la vista. `CRichEditCntrItem`proporciona acceso a los elementos de cliente OLE en el contenedor.  
  
 Este control común de Windows (y por tanto la [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) y las clases relacionadas) está disponible sólo para los programas que se ejecutan en versiones de Windows 95 ó 98 y Windows NT 3.51 y posteriores.  
  
 Para obtener un ejemplo del uso de un documento de edición enriquecidas en una aplicación MFC, vea el [WORDPAD](../../visual-cpp-samples.md) aplicación de ejemplo.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Llame a esta función para crear un `CRichEditCntrItem` de objetos y agregar a este documento.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Parámetros  
 *preo*  
 Puntero a un [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) estructura que describe un elemento OLE. El nuevo `CRichEditCntrItem` objeto se crea en torno a este elemento OLE. Si *preo* es **NULL**, el nuevo elemento de cliente está vacío.  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a una nueva [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objeto que se ha agregado a este documento.  
  
### <a name="remarks"></a>Comentarios  
 Esta función no realiza ninguna inicialización de OLE.  
  
 Para obtener más información, consulte el [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) estructura en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Llame a esta función para determinar el formato de texto para transmitir el contenido de la edición enriquecida.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Uno de los siguientes indicadores:  
  
- `SF_TEXT`Indica que el control rich edit no mantiene la información de formato.  
  
- `SF_RTF`Indica que el control rich edit mantener información de formato.  
  
### <a name="remarks"></a>Comentarios  
 El valor devuelto se basa en el [m_bRTF](#m_brtf) miembro de datos. Esta función devuelve `SF_RTF` si `m_bRTF` es **TRUE**; en caso contrario, `SF_TEXT`.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 Llame a esta función para obtener acceso a la [CRichEditView](../../mfc/reference/cricheditview-class.md) objeto asociado a esta `CRichEditDoc` objeto.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a la `CRichEditView` objeto asociado con el documento.  
  
### <a name="remarks"></a>Comentarios  
 El texto y la información de formato se encuentran en la `CRichEditView` objeto. La `CRichEditDoc` objeto mantiene los elementos OLE para la serialización. Debería haber sólo uno `CRichEditView` para cada `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>CRichEditDoc:: M_brtf  
 Cuando **TRUE**, indica que [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) y [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) debe almacenar las características de formato de carácter y de párrafo.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de MFC WORDPAD](../../visual-cpp-samples.md)   
 [Clase COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Gráfico de jerarquía](../../mfc/hierarchy-chart.md)   
 [CRichEditView (clase)](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem (clase)](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument (clase)](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl (clase)](../../mfc/reference/cricheditctrl-class.md)
