---
title: "Clases compartidas por MFC y ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clases compartidas, clases"
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Clases compartidas por MFC y ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En la tabla siguiente se enumera las clases que se comparten entre MFC y ATL.  
  
|Clase|Descripción|Archivo de encabezado|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Proporciona métodos para administrar los valores de fecha y hora asociados a un archivo.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Proporciona métodos para administrar los valores de tiempo asociados a un archivo y fecha relativa.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Representa un objeto de cadena con un búfer de caracteres fijas.|CStringT.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Proporciona compatibilidad con mapas de bits mejorada, incluida la capacidad para cargar y guardar imágenes en formatos JPEG, GIF, BMP y gráficos de red portátiles (PNG).|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Encapsula el **FECHA** tipo de datos utilizado en la automatización OLE.|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Representa un tiempo relativo, un intervalo de tiempo.|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Una clase similar a las ventanas [PUNTO](../../mfc/reference/point-structure1.md) estructura que también incluye funciones de miembro para manipular `CPoint` y **PUNTO** estructuras.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Una clase similar a una ventana [RECT](../../mfc/reference/rect-structure1.md) estructura que también incluye funciones de miembro para manipular `CRect` objetos y Windows `RECT` estructuras.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Representa un `CSimpleStringT` objeto.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Una clase similar a la estructura de TAMAÑO de Windows, que implementa una coordenada relativa o la posición.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Proporciona la limpieza de recursos automático para `GetBuffer` y `ReleaseBuffer` llama en una existente `CStringT` objeto.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Representa los datos de un objeto de cadena.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Representa un `CStringT` objeto.|CStringT.h (MFC dependiente) atlstr.h (independiente de MFC)|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Representa una fecha y hora absoluta.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Un período de tiempo, que se almacena internamente como el número de segundos en el intervalo de tiempo.|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Representa la interfaz para un `CStringT` Administrador de memoria.|atlsimpstr.h|  
  
## <a name="see-also"></a>Vea también  
 [Clases compartidas de ATL y MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)

