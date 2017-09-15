---
title: packaged_task (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3ca8c4c008daa02af2bba0df8468bea3c063c28a
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="packagedtask-class"></a>packaged_task (Clase)
Describe un *proveedor asincrónico* que es un contenedor de llamadas cuya signatura de llamada es `Ty(ArgTypes...)`. Su *estado asincrónico asociado* contiene una copia del objeto al que se puede llamar, además del resultado posible.  
  
## <a name="syntax"></a>Sintaxis  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[packaged_task](#packaged_task)|Construye un objeto `packaged_task`.|  
|[packaged_task::~packaged_task (Destructor)](#dtorpackaged_task_destructor)|Destruye un objeto `packaged_task`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[get_future](#get_future)|Devuelve un objeto [future](../standard-library/future-class.md) que tiene el mismo estado asincrónico asociado.|  
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|Llama al objeto que se puede llamar que está almacenado en el estado asincrónico asociado y almacena el valor devuelto de forma atómica.|  
|[reset](#reset)|Reemplaza el estado asincrónico asociado.|  
|[swap](#swap)|Intercambia el estado asincrónico asociado con el de un objeto especificado.|  
|[válido](#valid)|Especifica si el objeto tiene un estado asincrónico asociado.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[packaged_task::operator=](#op_eq)|Transfiere un estado asincrónico asociado de un objeto especificado.|  
|[packaged_task::operator()](#op_call)|Llama al objeto que se puede llamar que está almacenado en el estado asincrónico asociado, almacena el valor devuelto de forma atómica y establece el estado en *Listo*.|  
|[packaged_task::operator bool](#op_bool)|Especifica si el objeto tiene un estado asincrónico asociado.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<futura >  
  
 **Espacio de nombres:** std  
  
##  <a name="get_future"></a> packaged_task::get_future  
 Devuelve un objeto de tipo `future<Ty>` que tiene el mismo *estado asincrónico asociado*.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Comentarios  
 Si el objeto `packaged_task` no tiene un estado asincrónico asociado, este método produce un [future_error](../standard-library/future-error-class.md) que tiene un código de error de `no_state`.  
  
 Si ya se ha llamado a este método para un objeto `packaged_task` que tiene el mismo estado asincrónico asociado, el método produce un `future_error` que tiene un código de error de `future_already_retrieved`.  
  
##  <a name="make_ready_at_thread_exit"></a> packaged_task::make_ready_at_thread_exit  
 Llama al objeto que se puede llamar que está almacenado en el *estado asincrónico asociado* y almacena el valor devuelto de forma atómica.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Comentarios  
 Si el objeto `packaged_task` no tiene un estado asincrónico asociado, este método produce un [future_error](../standard-library/future-error-class.md) que tiene un código de error de `no_state`.  
  
 Si ya se ha llamado a este método o a [make_ready_at_thread_exit](#make_ready_at_thread_exit) para un objeto `packaged_task` que tiene el mismo estado asincrónico asociado, el método produce un `future_error` que tiene un código de error de `promise_already_satisfied`.  
  
 De otro modo, este operador llama a `INVOKE(fn, args..., Ty)`, donde *fn* es el objeto que se puede llamar que está almacenado en el estado asincrónico asociado. Cualquier valor devuelto se almacena de forma atómica como el resultado devuelto del estado asincrónico asociado.  
  
 A diferencia de [packaged_task::operator()](#op_call), el estado asincrónico asociado no se establece en `ready` hasta que no se hayan destruido todos los objetos locales de subprocesos del subproceso de llamada. Normalmente, los subprocesos que están bloqueados en el estado asincrónico asociado no se desbloquean hasta que no se sale del subproceso de llamada.  
  
##  <a name="op_eq"></a> packaged_task::operator=  
 Transfiere el *estado asincrónico asociado* de un objeto especificado.  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>Parámetros  
 `Right`  
 Objeto `packaged_task`.  
  
### <a name="return-value"></a>Valor devuelto  
 `*this`  
  
### <a name="remarks"></a>Comentarios  
 Después de la operación, `Right` ya no tiene un estado asincrónico asociado.  
  
##  <a name="op_call"></a> packaged_task::operator()  
 Llama al objeto que se puede llamar que está almacenado en el *estado asincrónico asociado*, almacena el valor devuelto de forma atómica y establece el estado en *Listo*.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Comentarios  
 Si el objeto `packaged_task` no tiene un estado asincrónico asociado, este método produce un [future_error](../standard-library/future-error-class.md) que tiene un código de error de `no_state`.  
  
 Si ya se ha llamado a este método o a [make_ready_at_thread_exit](#make_ready_at_thread_exit) para un objeto `packaged_task` que tiene el mismo estado asincrónico asociado, el método produce un `future_error` que tiene un código de error de `promise_already_satisfied`.  
  
 De otro modo, este operador llama a `INVOKE(fn, args..., Ty)`, donde *fn* es el objeto que se puede llamar que está almacenado en el estado asincrónico asociado. Cualquier valor devuelto se almacena de forma atómica como el resultado devuelto del estado asincrónico asociado, y el estado se establece en Listo. Como resultado, se desbloquean todos los subprocesos bloqueados en el estado asincrónico asociado.  
  
##  <a name="op_bool"></a> packaged_task::operator bool  
 Especifica si el objeto tiene `associated asynchronous state`.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es `true` si el objeto tiene un estado asincrónico asociado; de lo contrario, es `false`.  
  
##  <a name="packaged_task"></a> packaged_task::packaged_task (Constructor)  
 Construye un objeto `packaged_task`.  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>Parámetros  
 `Right`  
 Objeto `packaged_task`.  
  
 `alloc`  
 Asignador de memoria. Para obtener más información, vea [\<allocators>](../standard-library/allocators-header.md).  
  
 `fn`  
 Objeto de función.  
  
### <a name="remarks"></a>Comentarios  
 El primer constructor crea un objeto `packaged_task` que no tiene ningún *estado asincrónico asociado*.  
  
 El segundo constructor crea un objeto `packaged_task` y transfiere el estado asincrónico asociado de `Right`. Después de la operación, `Right` ya no tiene un estado asincrónico asociado.  
  
 El tercer constructor crea un objeto `packaged_task` que tiene una copia de `fn` almacenada en su estado asincrónico asociado.  
  
 El cuarto constructor crea un objeto `packaged_task` que tiene una copia de `fn` almacenada en su estado asincrónico asociado y utiliza `alloc` para la asignación de memoria.  
  
##  <a name="dtorpackaged_task_destructor"></a> packaged_task::~packaged_task (Destructor)  
 Destruye un objeto `packaged_task`.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Comentarios  
 Si el *estado asincrónico asociado* no está *listo*, el destructor almacena una excepción [future_error](../standard-library/future-error-class.md) que tiene un código de error de `broken_promise` como el resultado en el estado asincrónico asociado, y cualquier subproceso que esté bloqueado en el estado asincrónico asociado se desbloquea.  
  
##  <a name="reset"></a> packaged_task::reset  
 Usa un nuevo *estado asincrónico asociado* para reemplazar el estado asincrónico asociado existente.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Comentarios  
 De hecho, este método ejecuta `*this = packaged_task(move(fn))`, donde *fn* es el objeto de función que está almacenado en el estado asincrónico asociado de este objeto. Por lo tanto, el estado del objeto se borra, y puede llamarse a [get_future](#get_future), [operator()](#op_call) y [make_ready_at_thread_exit](#make_ready_at_thread_exit) como si estuviera en un objeto recién creado.  
  
##  <a name="swap"></a> packaged_task::swap  
 Intercambia el estado asincrónico asociado con el de un objeto especificado.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Parámetros  
 `Right`  
 Objeto `packaged_task`.  
  
##  <a name="valid"></a> packaged_task::valid  
 Especifica si el objeto tiene `associated asynchronous state`.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Es `true` si el objeto tiene un estado asincrónico asociado; de lo contrario, es `false`.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)



