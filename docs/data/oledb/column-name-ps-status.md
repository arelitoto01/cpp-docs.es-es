---
title: "COLUMN_NAME_PS_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_NAME_PS_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_PS_STATUS (macro)"
ms.assetid: 134e1bfe-abfa-4b64-9159-e492f31de44b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_NAME_PS_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Representa un enlace en el conjunto de filas a la columna concreta en el conjunto de filas.  Similar a [COLUMN\_NAME](../../data/oledb/column-name.md), salvo que esta macro también toma la precisión, escala, y el estado de la columna.  
  
## Sintaxis  
  
```  
  
COLUMN_NAME_PS_STATUS(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
status )  
```  
  
#### Parámetros  
 `pszName`  
 \[in\] Un puntero al nombre de columna.  El nombre debe ser una cadena Unicode.  Esto se puede lograr poniendo una “l” delante del nombre, por ejemplo: `L"MyColumn"`.  
  
 `nPrecision`  
 \[in\] Precisión máxima de la columna que desea enlazar.  
  
 `nScale`  
 \[in\] La escala de la columna que desea enlazar.  
  
 `data`  
 \[in\] El miembro de datos correspondiente en el registro de usuario.  
  
 *status*  
 \[in\] La variable que se enlazará el estado de la columna.  
  
## Comentarios  
 Vea [COLUMN\_NAME](../../data/oledb/column-name.md) para información donde se utilizan macros de **COLUMN\_NAME\_\*** .  
  
## Requisitos  
 **Encabezado:** atldbcli.h  
  
## Vea también  
 [Macros y funciones globales para las plantillas de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_NAME](../../data/oledb/column-name.md)   
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)