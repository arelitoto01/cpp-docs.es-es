---
title: "EventSource::InvokeAll (M&#233;todo) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::InvokeAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeAll (método)"
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# EventSource::InvokeAll (M&#233;todo)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Llama a cada controlador de eventos asociado con el actual [EventSource](../windows/eventsource-class.md) objeto mediante los argumentos y tipos de argumento especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void InvokeAll();  
template <  
   typename T0  
>  
void InvokeAll(  
   T0arg0  
);  
template <  
   typename T0,  
   typename T1  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8,  
   typename T9  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8,  
   T9arg9  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `T0`  
 El tipo de argumento del controlador de evento de cero.  
  
 `T1`  
 El tipo del primer argumento de controlador de eventos.  
  
 `T2`  
 El tipo del segundo argumento del controlador de eventos.  
  
 `T3`  
 El tipo del tercer argumento de controlador de eventos.  
  
 `T4`  
 El tipo del cuarto argumento del controlador de eventos.  
  
 `T5`  
 El tipo del quinto argumento del controlador de eventos.  
  
 `T6`  
 El tipo del sexto argumento del controlador de eventos.  
  
 `T7`  
 El tipo del séptimo argumento del controlador de eventos.  
  
 `T8`  
 El tipo del octavo de argumento del controlador de eventos.  
  
 `T9`  
 El tipo del noveno argumento del controlador de eventos.  
  
 `arg0`  
 El argumento de controlador de evento de cero.  
  
 `arg1`  
 El primer argumento de controlador de eventos.  
  
 `arg2`  
 El segundo argumento de controlador de eventos.  
  
 `arg3`  
 El tercer argumento de controlador de eventos.  
  
 `arg4`  
 El cuarto argumento de controlador de eventos.  
  
 `arg5`  
 El quinto argumento de controlador de eventos.  
  
 `arg6`  
 Sexto argumento del controlador de eventos.  
  
 `arg7`  
 Séptimo argumento del controlador de eventos.  
  
 `arg8`  
 El octavo argumento de controlador de eventos.  
  
 `arg9`  
 Noveno argumento del controlador de eventos.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** event.h  
  
 **Espacio de nombres:** Microsoft::WRL
 
 ## <a name="see-also"></a>Vea también
 [EventSource (clase)](../windows/eventsource-class.md)