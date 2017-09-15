---
title: "C&#243;mo: Convertir un bucle OpenMP que usa el control de excepciones para usar el runtime de simultaneidad | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "control de excepciones, convertir de OpenMP a Runtime de simultaneidad"
  - "convertir de OpenMP a Runtime de simultaneidad, control de excepciones"
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C&#243;mo: Convertir un bucle OpenMP que usa el control de excepciones para usar el runtime de simultaneidad
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En este ejemplo se muestra cómo convertir un bucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) de OpenMP que realiza el control de excepciones para usar el mecanismo de control de excepciones del runtime de simultaneidad.  
  
 En OpenMP, el mismo subproceso debe detectar y controlar en la misma región una excepción que se produce en una región paralela.  Una excepción que escape de la región paralela será detectada por el controlador de excepciones no controladas, que finaliza el proceso de forma predeterminada.  
  
 En el runtime de simultaneidad, cuando se produce una excepción en el cuerpo de una función de trabajo que se pasa a un grupo de tareas como un objeto [concurrency::task\_group](../Topic/task_group%20Class.md) o [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md), o a un algoritmo paralelo como [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), el runtime almacena esa excepción y calcula las referencias en el contexto donde se espera que el grupo de tareas o el algoritmo finalice.  Para los grupos de tareas, el contexto de espera es el contexto que llama a [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) o [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md).  Para un algoritmo paralelo, el contexto que espera es el contexto que llamó a ese algoritmo.  El runtime también detiene todas las tareas activas que están en el grupo de tareas, incluidas las que se encuentran en grupos de tareas secundarios, y descarta cualquier tarea que no se haya iniciado todavía.  
  
## Ejemplo  
 En este ejemplo se muestra cómo controlar excepciones en una región `parallel` de OpenMP y en una llamada a `parallel_for`.  La función `do_work` realiza una solicitud de asignación de memoria que no tiene éxito y, por tanto, produce una excepción de tipo [std::bad\_alloc](../../standard-library/bad-alloc-class.md).  En la versión que usa OpenMP, el subproceso que produce la excepción también debe detectarla.  Es decir, cada iteración de un bucle paralelo de OpenMP debe controlar la excepción.  En la versión que usa el runtime de simultaneidad, el subproceso principal detecta una excepción producida por otro subproceso.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 Este ejemplo produce el siguiente resultado:  
  
  **Using OpenMP...**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**Using the Concurrency Runtime...**  
**An error of type 'class std::bad\_alloc' occurred.** En la versión de este ejemplo que usa OpenMP, la excepción se produce y controla en cada iteración del bucle.  En la versión que usa el runtime de simultaneidad, el runtime almacena la excepción, detiene todas las tareas activas, descarta cualquier tarea que no se haya iniciado y calcula las referencias de la excepción en el contexto que llama a `parallel_for`.  
  
 Si necesita que la versión que usa OpenMP termine después de producirse la excepción, podría usar una marca booleana para indicar a otras iteraciones del bucle que se produjo el error.  Como en el ejemplo del tema [Cómo: Convertir un bucle OpenMP que usa la cancelación para usar el runtime de simultaneidad](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), las iteraciones subsiguientes del bucle no harán nada si se establece la marca.  Por el contrario, si necesita que el bucle que usa el runtime de simultaneidad continúe después de que se produzca la excepción, controle la excepción en el cuerpo del bucle paralelo propiamente dicho.  
  
 Otros componentes del runtime de simultaneidad, como los agentes asincrónicos y las tareas ligeras, no transportan excepciones.  En su lugar, el controlador de excepciones no controladas, que de forma predeterminada finaliza el proceso, detecta las excepciones no controladas.  Para obtener más información acerca del control de excepciones, vea [Control de excepciones](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Para obtener más información sobre `parallel_for` y otros algoritmos paralelos, vea [Algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md).  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `concrt-omp-exceptions.cpp` y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-exceptions.cpp**  
  
## Vea también  
 [Migrar de OpenMP al Runtime de simultaneidad](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Control de excepciones](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md)