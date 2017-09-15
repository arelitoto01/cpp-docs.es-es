---
title: "Comparar estructuras de datos de sincronizaci&#243;n con la API de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "estructuras de datos de sincronización, en comparación con API de Windows"
  - "event (clase), ejemplo"
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Comparar estructuras de datos de sincronizaci&#243;n con la API de Windows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En este tema se compara el comportamiento de las estructuras de datos de sincronización que proporciona el Runtime de simultaneidad con las que proporciona la API de Windows.  
  
 Las estructuras de datos de sincronización que proporciona el Runtime de simultaneidad siguen el *modelo de subprocesos cooperativo*.  En este modelo, las primitivas de sincronización ceden explícitamente sus recursos de procesamiento a otros subprocesos.  Esto lo diferencia del *modelo de subprocesos preferente*, donde los recursos de procesamiento se transfieren a otros subprocesos por medio del programador de control o el sistema operativo.  
  
## critical\_section  
 La clase [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) es similar a la estructura `CRITICAL_SECTION` de Windows, ya que solamente la pueden usar los subprocesos de un proceso.  Para obtener más información sobre las secciones críticas en la API de Windows, vea [Objetos de sección crítica](http://msdn.microsoft.com/library/windows/desktop/ms682530).  
  
## reader\_writer\_lock  
 La clase [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) es similar a los bloqueos SRW \(bloqueos finos de lector\/escritor\) de Windows.  En la tabla siguiente se explican las similitudes y las diferencias.  
  
|Característica|`reader_writer_lock`|Bloqueo SRW|  
|--------------------|--------------------------|-----------------|  
|No reentrante|Sí|Sí|  
|Puede promover un lector a un escritor \(compatibilidad de actualización\)|No|No|  
|Puede degradar un escritor a un lector \(compatibilidad de degradación\)|No|No|  
|Bloqueo de preferencia de escritura|Sí|No|  
|Acceso FIFO a escritores|Sí|No|  
  
 Para obtener más información sobre los bloqueos SRW, vea [Bloqueos SRW \(bloqueos finos de lector\/escritor\)](http://msdn.microsoft.com/library/windows/desktop/aa904937) en Platform SDK.  
  
## evento  
 La clase [concurrency::event](../../parallel/concrt/reference/event-class.md) es similar a un evento de restablecimiento manual sin nombre de Windows.  Sin embargo, un objeto `event` se comporta de forma cooperativa, en tanto que un evento de Windows se comporta con preferencia.  Para obtener más información sobre los eventos de Windows, vea [Objetos de eventos](http://msdn.microsoft.com/library/windows/desktop/ms682655).  
  
## Ejemplo  
  
### Descripción  
 Para comprender mejor la diferencia entre la clase de `event` y los eventos de Windows, considere el siguiente ejemplo.  Este ejemplo permite que el programador cree dos tareas simultáneas a lo sumo y, a continuación, llama a dos funciones similares que utilizan la clase `event` y un evento de restablecimiento manual de Windows.  Cada función crea en primer lugar varias tareas que esperan hasta que se señaliza un evento compartido.  A continuación, cada función cede el paso a las tareas en ejecución y, después, señala el evento.  Posteriormente, cada función espera por el evento señalado.  
  
### Código  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/CPP/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### Comentarios  
 Este ejemplo genera la siguiente salida de ejemplo:  
  
  **Cooperative event:**  
 **Context 0: waiting on an event.**  
 **Context 1: waiting on an event.**  
 **Context 2: waiting on an event.**  
 **Context 3: waiting on an event.**  
 **Context 4: waiting on an event.**  
 **Setting the event.**  
 **Context 5: received the event.**  
 **Context 6: received the event.**  
 **Context 7: received the event.**  
 **Context 8: received the event.**  
 **Context 9: received the event.**  
**Windows event:**  
 **Context 10: waiting on an event.**  
 **Context 11: waiting on an event.**  
 **Setting the event.**  
 **Context 12: received the event.**  
 **Context 14: waiting on an event.**  
 **Context 15: received the event.**  
 **Context 16: waiting on an event.**  
 **Context 17: received the event.**  
 **Context 18: waiting on an event.**  
 **Context 19: received the event.**  
 **Context 13: received the event.** La clase `event` se comporta de forma cooperativa, por lo que el programador puede reasignar los recursos del procesamiento a otro contexto cuando un evento está esperando para entrar en el estado señalado.  Así, la versión que utiliza la clase `event` realiza más trabajo.  En la versión que utiliza los eventos de Windows, cada tarea de espera debe entrar en el estado señalado antes de que se inicie la tarea siguiente.  
  
 Para obtener más información acerca de las tareas, vea [Paralelismo de tareas](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Vea también  
 [Estructuras de datos de sincronización](../../parallel/concrt/synchronization-data-structures.md)   
 [Objetos de sección crítica](http://msdn.microsoft.com/library/windows/desktop/ms682530)   
 [Bloqueos SRW \(bloqueos finos de lector\/escritor\)](http://msdn.microsoft.com/library/windows/desktop/aa904937)   
 [Objetos de eventos](http://msdn.microsoft.com/library/windows/desktop/ms682655)