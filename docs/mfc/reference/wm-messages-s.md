---
title: 'Mensajes WM_: S | Documentos de Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_SIZE
- ON_WM_SETFOCUS
- ON_WM_SIZING
- ON_WM_SYSCHAR
- ON_WM_SETTINGCHANGE
- ON_WM_SYSDEADCHAR
- ON_WM_SHOWWINDOW
- ON_WM_STYLECHANGING
- ON_WM_SYSCOMMAND
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCOLORCHANGE
- ON_WM_SETCURSOR
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSKEYUP
- ON_WM_SYSKEYDOWN
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
caps.latest.revision: 14
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
ms.openlocfilehash: 339b03be41187ad0249ae38d36d4640401247a83
ms.contentlocale: es-es
ms.lasthandoff: 02/24/2017

---
# <a name="wm-messages-s"></a>WM_ Messages: S
Las siguientes entradas de mapa que se corresponden con los prototipos de función.  
  
|Entrada de asignación|Prototipo de función|  
|---------------|------------------------|  
|(DE ON_WM_SETCURSOR)|afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, UINT, UINT);|  
|(DE ON_WM_SETFOCUS)|afx_msg void [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|  
|(DE ON_WM_SETTINGCHANGE)|afx_msg void [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags, LPCTSTR lpszSection);|  
|(DE ON_WM_SHOWWINDOW)|afx_msg void [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(BOOL, UINT);|  
|(DE ON_WM_SIZE)|afx_msg void [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, int, int);|  
|(DE ON_WM_SIZECLIPBOARD)|afx_msg void [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, identificador);|  
|(DE ON_WM_SIZING)|afx_msg void [OnDestroy](../../mfc/reference/cwnd-class.md#onsizing)(UINT, LPRECT);|  
|(DE ON_WM_SPOOLERSTATUS)|afx_msg void [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)(UINT, UINT);|  
|(DE ON_WM_STYLECHANGED)|afx_msg void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(int, LPSTYLESTRUCT);|  
|(DE ON_WM_STYLECHANGING)|afx_msg void [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(int, LPSTYLESTRUCT);|  
|(DE ON_WM_SYSCHAR)|afx_msg void [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)(UINT, UINT, UINT);|  
|(DE ON_WM_SYSCOLORCHANGE)|afx_msg void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|  
|(DE ON_WM_SYSCOMMAND)|afx_msg void [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, LONG);|  
|(DE ON_WM_SYSDEADCHAR)|afx_msg void [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)(UINT, UINT, UINT);|  
|(DE ON_WM_SYSKEYDOWN)|afx_msg void [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)(UINT, UINT, UINT);|  
|(DE ON_WM_SYSKEYUP)|afx_msg void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)(UINT, UINT, UINT);|  
  
## <a name="see-also"></a>Vea también  
 [Mapas de mensajes](../../mfc/reference/message-maps-mfc.md)   
 [Controladores de mensajes WM_](../../mfc/reference/handlers-for-wm-messages.md)

