---
title: "C&#243;mo: Utilizar un filtro de bloque de mensaje | Microsoft Docs"
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
  - "filtros de bloques de mensajes, usar [Runtime de simultaneidad]"
  - "usar filtros de bloques de mensajes [Runtime de simultaneidad]"
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# C&#243;mo: Utilizar un filtro de bloque de mensaje
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En este documento se muestra cómo usar una función de filtro para permitir que un bloque de mensajes asincrónicos acepte o rechace un mensaje basándose en la carga de ese mensaje.  
  
 Cuando se crea un objeto de bloque de mensaje como una [Concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md), un [Concurrency:: call](../../parallel/concrt/reference/call-class.md), o un [Concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md), puede proporcionar un *filter, función* que determina si el bloque de mensajes acepta o rechaza un mensaje. Una función de filtro resulta útil para garantizar que un bloque de mensajes recibe solo ciertos valores.  
  
 Funciones de filtro son importantes porque permiten conectar los bloques de mensajes para formar *redes de flujo de datos*. En una red de flujo de datos, los bloques de mensajes controlan el flujo de datos y procesan solo los mensajes que cumplen determinados criterios. Compare esto con el modelo de flujo de control, donde el flujo de datos se regula con las estructuras de control, como instrucciones condicionales, bucles, etc.  
  
 En este documento se proporciona un ejemplo básico de cómo usar un filtro de mensajes. Para obtener ejemplos adicionales que utilizan filtros de mensajes y el modelo de flujo de datos para conectar los bloques de mensajes, consulte [Tutorial: crear un agente de flujo de datos](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) y [Tutorial: creación de una red de procesamiento de imágenes](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
## <a name="example"></a>Ejemplo  
 Considere la siguiente función, `count_primes`, que muestra el uso básico de un bloque de mensajes que no filtra los mensajes entrantes. El bloque de mensajes anexa los números primos en un [std:: vector](vector%20Class.md) objeto. La función `count_primes` envía varios números al bloque de mensajes, recibe los valores de salida del bloque de mensajes e imprime aquellos números que son primos en la consola.  
  
 [!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/CPP/how-to-use-a-message-block-filter_1.cpp)]  
  
 El objeto `transformer` procesa todos los valores de entrada; sin embargo, solo requiere los valores que son primos. Aunque la aplicación podría escribirse de forma que el remitente del mensaje envíe solo números primos, los requisitos del receptor del mensaje no se pueden conocer siempre.  
  
## <a name="example"></a>Ejemplo  
 La siguiente función, `count_primes_filter`, realiza la misma tarea que la función `count_primes`. Sin embargo, el objeto `transformer` de esta versión usa una función de filtro para aceptar únicamente los valores que son primos. La función que realiza la acción recibe solo números primos; por consiguiente, no tiene que llamar a la función `is_prime`.  
  
 Dado que el objeto `transformer` recibe solo números primos, el propio objeto `transformer` puede contener números primos. Es decir, el objeto `transformer` de este ejemplo no es necesario para agregar los números primos al objeto `vector`.  
  
 [!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/CPP/how-to-use-a-message-block-filter_2.cpp)]  
  
 El objeto `transformer` procesa ahora solo los valores que son primos. En el ejemplo anterior, el objeto `transformer` procesa todos los mensajes. Por consiguiente, en el ejemplo anterior debe recibir el mismo número de mensajes que envía. Este ejemplo usa el resultado de la [Concurrency:: Send](../Topic/send%20Function.md) función para determinar cuántos mensajes se reciben el `transformer` objeto. La función `send` devuelve `true` cuando el búfer de mensajes acepta el mensaje y `false` cuando el búfer de mensajes rechaza el mensaje. Por tanto, el número de veces que el búfer de mensajes acepta el mensaje coincide con el contador de números primos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra el ejemplo completo. En el ejemplo se llama a las funciones `count_primes` y `count_primes_filter`.  
  
 [!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/CPP/how-to-use-a-message-block-filter_3.cpp)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o péguelo en un archivo denominado `primes-filter.cpp` y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 **cl.exe/EHsc primes-filter.cpp**  
  
## <a name="robust-programming"></a>Programación sólida  
 Una función de filtro puede ser una función lambda, un puntero a función o un objeto de función. Cada función de filtro toma una de las siguientes formas:  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Para eliminar la copia innecesaria de datos, use el segundo formulario cuando tenga un tipo agregado que se transmite por valor.  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca de agentes asincrónicos](../../parallel/concrt/asynchronous-agents-library.md)   
 [Tutorial: Crear a un agente de flujo de datos](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [Tutorial: Crear una red de procesamiento de imágenes](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Clase transformer](../../parallel/concrt/reference/transformer-class.md)