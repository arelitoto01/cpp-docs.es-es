---
title: "Cómo: cargar un recurso de cinta desde una aplicación MFC | Documentos de Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a943f82fc9b438a74af3673e0210612183304c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Cómo: Cargar un recurso de cinta desde una aplicación MFC
Para usar el recurso de cinta de opciones en la aplicación, modifique la aplicación para cargar el recurso de cinta de opciones.  
  
### <a name="to-load-a-ribbon-resource"></a>Para cargar un recurso de cinta de opciones  
  
1.  Declare el `Ribbon Control` objeto en el `CMainFrame` clase.  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  En `CMainFrame::OnCreate`, crear e inicializar el Control de la cinta de opciones.  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>Vea también  
 [Diseñador de la cinta de opciones (MFC)](../mfc/ribbon-designer-mfc.md)
