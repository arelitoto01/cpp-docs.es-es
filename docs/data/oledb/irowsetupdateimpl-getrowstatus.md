---
title: "IRowsetUpdateImpl::GetRowStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetUpdateImpl.GetRowStatus"
  - "IRowsetUpdateImpl::GetRowStatus"
  - "IRowsetUpdateImpl.GetRowStatus"
  - "ATL::IRowsetUpdateImpl::GetRowStatus"
  - "GetRowStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowStatus (método)"
ms.assetid: ce57e8be-5891-44d9-b3c5-59ffd3913678
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::GetRowStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Devuelve el estado de filas especificadas.  
  
## Sintaxis  
  
```  
  
      STDMETHOD ( GetRowStatus )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBPENDINGSTATUS rgPendingStatus[]   
);  
```  
  
#### Parámetros  
 `hReserved`  
 \[in\] Corresponde a `hChapter` el parámetro en [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx).  
  
 Para otros parámetros, vea [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx) en *la referencia del*programador.  
  
## Requisitos  
 **Header:** atldb.h  
  
## Vea también  
 [IRowsetUpdateImpl \(Clase\)](../../data/oledb/irowsetupdateimpl-class.md)