---
title: Clase ios_base | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ios_base
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- ios/std::ios_base::fmtflags
- ios/std::ios_base::iostate
- ios/std::ios_base::openmode
- ios/std::ios_base::seekdir
- ios/std::ios_base::event
- ios/std::ios_base::adjustfield
- ios/std::ios_base::app
- ios/std::ios_base::ate
- ios/std::ios_base::badbit
- ios/std::ios_base::basefield
- ios/std::ios_base::beg
- ios/std::ios_base::binary
- ios/std::ios_base::boolalpha
- ios/std::ios_base::cur
- ios/std::ios_base::dec
- ios/std::ios_base::end
- ios/std::ios_base::eofbit
- ios/std::ios_base::failbit
- ios/std::ios_base::fixed
- ios/std::ios_base::floatfield
- ios/std::ios_base::goodbit
- ios/std::ios_base::hex
- ios/std::ios_base::in
- ios/std::ios_base::internal
- ios/std::ios_base::left
- ios/std::ios_base::oct
- ios/std::ios_base::out
- ios/std::ios_base::right
- ios/std::ios_base::scientific
- ios/std::ios_base::showbase
- ios/std::ios_base::showpoint
- ios/std::ios_base::showpos
- ios/std::ios_base::skipws
- ios/std::ios_base::trunc
- ios/std::ios_base::unitbuf
- ios/std::ios_base::uppercase
- ios/std::ios_base::failure
- ios/std::ios_base::flags
- ios/std::ios_base::getloc
- ios/std::ios_base::imbue
- ios/std::ios_base::Init
- ios/std::ios_base::iword
- ios/std::ios_base::precision
- ios/std::ios_base::pword
- ios/std::ios_base::register_callback
- ios/std::ios_base::setf
- ios/std::ios_base::sync_with_stdio
- ios/std::ios_base::unsetf
- ios/std::ios_base::width
- ios/std::ios_base::xalloc
dev_langs:
- C++
helpviewer_keywords:
- ios_base class
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
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
ms.openlocfilehash: 0bf5408966a32534556a25010a212900566bdf37
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="iosbase-class"></a>ios_base (Clase)
La clase describe las funciones de almacenamiento y miembro comunes al flujo de entrada y al de salida que no dependen de los parámetros de plantilla. (La clase de plantilla [basic_ios](../standard-library/basic-ios-class.md) describe lo que es común y depende de los parámetros de plantilla).  
  
 Un objeto de clase ios_base almacena la información de formato, que consta de:  
  
-   Marcas de formato en un objeto de tipo [fmtflags](#fmtflags).  
  
-   Una máscara de excepción en un objeto de tipo [iostate](#iostate).  
  
-   Un ancho de campo en un objeto de tipo `int`.  
  
-   Una precisión de visualización en un objeto de tipo `int`.  
  
-   Un objeto de configuración regional en un objeto de tipo **locale**.  
  
-   Dos matrices extensibles, con elementos de tipo **long** y puntero `void`.  
  
 Un objeto de clase ios_base también almacena información de estado de flujo en un objeto de tipo [iostate](#iostate) y una pila de devolución de llamada.  
  
### <a name="constructors"></a>Constructores  
  
|||  
|-|-|  
|[ios_base](#ios_base)|Construye objetos `ios_base`.|  
  
### <a name="typedefs"></a>Definiciones de tipo  
  
|||  
|-|-|  
|[event_callback](#event_callback)|Describe una función que se pasa a [register_call](#register_callback).|  
|[fmtflags](#fmtflags)|Constantes para especificar la apariencia de la salida.|  
|[iostate](#iostate)|Define constantes que describen el estado de una secuencia.|  
|[openmode](#openmode)|Describe cómo interactuar con una secuencia.|  
|[seekdir](#seekdir)|Especifica el punto de partida para las operaciones de desplazamiento.|  
  
### <a name="enums"></a>Enumeraciones  
  
|||  
|-|-|  
|[event](#event)|Especifica tipos de eventos.|  
  
### <a name="constants"></a>Constantes  
  
|||  
|-|-|  
|[adjustfield](#fmtflags)|Máscara de bits que se define como `internal` &#124; `left` &#124; `right`.|  
|[app](#openmode)|Especifica la búsqueda al final de una secuencia antes de cada inserción.|  
|[ate](#openmode)|Especifica la búsqueda al final de una secuencia cuando se crea por primera vez su objeto de control.|  
|[badbit](#iostate)|Registra una pérdida de integridad del búfer de secuencia.|  
|[basefield](#fmtflags)|Máscara de bits que se define como `dec` &#124; `hex` &#124; `oct`.|  
|[beg](#seekdir)|Especifica la búsqueda en relación con el principio de una secuencia.|  
|[binary](#openmode)|Especifica que se debe leer un archivo como una secuencia binaria, en lugar de como una secuencia de texto.|  
|[boolalpha](#fmtflags)|Especifica la inserción o extracción de objetos de tipo `bool` como nombres (como `true` y `false`), en lugar de como valores numéricos.|  
|[cur](#seekdir)|Especifica la búsqueda en relación con la posición actual dentro de una secuencia.|  
|[dec](#fmtflags)|Especifica la inserción o extracción de valores enteros en formato decimal.|  
|[end](#seekdir)|Especifica la búsqueda en relación con el final de una secuencia.|  
|[eofbit](#iostate)|Registra el final de archivo al extraer de una secuencia.|  
|[failbit](#iostate)|Registra un error al extraer un campo válido de una secuencia.|  
|[fixed](#fmtflags)|Especifica la inserción de valores de punto flotante en formato de punto fijo (sin campo de exponente).|  
|[floatfield](#fmtflags)|Máscara de bits que se define como `fixed` &#124; `scientific`.|  
|[goodbit](#iostate)|Se borran todos los bits de estado.|  
|[hex](#fmtflags)|Especifica la inserción o extracción de valores enteros en formato hexadecimal.|  
|[in](#openmode)|Especifica la extracción de una secuencia.|  
|[internal](#fmtflags)|Rellena un ancho de campo insertando caracteres de relleno en un punto interno a un campo numérico generado.|  
|[left](#fmtflags)|Especifica la justificación a la izquierda.|  
|[oct](#fmtflags)|Especifica la inserción o extracción de valores enteros en formato octal.|  
|[out](#openmode)|Especifica la inserción en una secuencia.|  
|[right](#fmtflags)|Especifica la justificación a la derecha.|  
|[scientific](#fmtflags)|Especifica la inserción de valores de punto flotante en formato científico (con un campo de exponente).|  
|[showbase](#fmtflags)|Especifica la inserción de un prefijo que revela la base de un campo entero generado.|  
|[showpoint](#fmtflags)|Especifica la inserción incondicional de un separador decimal en un campo de punto flotante generado.|  
|[showpos](#fmtflags)|Especifica la inserción de un signo más en un campo numérico generado no negativo.|  
|[skipws](#fmtflags)|Especifica la omisión del espacio en blanco inicial antes de ciertas extracciones.|  
|[trunc](#openmode)|Especifica la eliminación de contenido de un archivo existente cuando se crea su objeto de control.|  
|[unitbuf](#fmtflags)|Hace que la salida se vacíe después de cada inserción.|  
|[uppercase](#fmtflags)|Especifica la inserción de los equivalentes en mayúsculas de letras en minúsculas en ciertas inserciones.|  
  
### <a name="member-functions"></a>Funciones miembro  
  
|||  
|-|-|  
|[failure](#failure)|Clase miembro que actúa como la clase base para todas las excepciones producidas por la función miembro [clear](../standard-library/basic-ios-class.md#clear) en la clase de plantilla [basic_ios](../standard-library/basic-ios-class.md).|  
|[flags](#flags)|Establece o devuelve la configuración actual de la marca.|  
|[getloc](#getloc)|Devuelve el objeto de configuración regional almacenado.|  
|[imbue](#imbue)|Cambia la configuración regional.|  
|[Init](#init)|Crea los objetos iostream estándar durante la construcción.|  
|[iword](#iword)|Asigna un valor que se va a almacenar como `iword`.|  
|[precision](#precision)|Especifica el número de dígitos que se debe mostrar en un número de punto flotante.|  
|[pword](#pword)|Asigna un valor que se va a almacenar como `pword`.|  
|[register_callback](#register_callback)|Especifica una función de devolución de llamada.|  
|[setf](#setf)|Establece las marcas especificadas.|  
|[sync_with_stdio](#sync_with_stdio)|Se asegura de que las operaciones de la biblioteca en tiempo de ejecución de C e iostream se produzcan en el orden en que aparecen en el código fuente.|  
|[unsetf](#unsetf)|Hace que las marcas especificadas se desactiven.|  
|[width](#width)|Establece la longitud del flujo de salida.|  
|[xalloc](#xalloc)|Especifica que una variable formará parte de la secuencia.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator=](#op_eq)|Operador de asignación de objetos `ios_base`.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<ios>  
  
 **Espacio de nombres:** std  
  
##  <a name="event"></a>  ios_base::event  
 Especifica tipos de eventos.  
  
```  
enum event {erase_event,
    imbue_event,
    copyfmt_event};  
```  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un tipo enumerado que describe un objeto que puede almacenar el evento de devolución de llamada usado como argumento para una función registrada con [register_callback](#register_callback). Los diferentes valores de evento son:  
  
- **copyfmt_event**, para identificar una devolución de llamada que se produce casi al final de una llamada a [copyfmt](../standard-library/basic-ios-class.md#copyfmt), justo antes de que se copie la [máscara de excepción](../standard-library/ios-base-class.md).  
  
- **erase_event**, para identificar una devolución de llamada que se produce al principio de una llamada a [copyfmt](../standard-library/basic-ios-class.md#copyfmt) o al principio de una llamada al destructor para **\*this**.  
  
- **imbue_event**, para identificar una devolución de llamada que se produce al final de una llamada a [imbue](#imbue), justo antes de que se devuelva la función.  
  
### <a name="example"></a>Ejemplo  
  Vea [register_callback](#register_callback) para obtener un ejemplo.  
  
##  <a name="event_callback"></a>  ios_base::event_callback  
 Describe una función que se pasa a [register_call](#register_callback).  
  
```  
 
typedef void (
__  
cdecl *event  
_  
callback)(
    event 
_E  ,  
    ios 
_  
base& 
_Base  ,  
    int _I);
```  
  
### <a name="parameters"></a>Parámetros  
 *_E*  
 [Evento](#event).  
  
 `_Base`  
 Flujo en el que se ha llamado al evento.  
  
 *_I*  
 Número definido por el usuario.  
  
### <a name="remarks"></a>Comentarios  
 El tipo describe un puntero a una función que se puede registrar con [register_callback](#register_callback). Este tipo de función no debe producir una excepción.  
  
### <a name="example"></a>Ejemplo  
  Vea [register_call](#register_callback) para obtener un ejemplo del uso de `event_callback`.  
  
##  <a name="failure"></a>  ios_base::failure  
 La clase `failure` define la clase base para los tipos de todos los objetos que las funciones de la biblioteca `iostreams` producen como excepciones para notificar los errores detectados durante las operaciones del búfer de flujo.  
  
```  
 
namespace std {  
class failure : public system_error {  
public:  
explicit failure(
const string& _Message,  
const error_code& _Code = io_errc::stream);

explicit failure(
const char* str,  
const error_code& _Code = io_errc::stream);

};  
```  
  
### <a name="remarks"></a>Comentarios  
 El valor devuelto por `what``()` es una copia de `_Message`, posiblemente aumentada con una prueba basada en `_Code`. Si no se especifica `_Code`, el valor predeterminado es `make_error_code``(io_errc::stream)`.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// ios_base_failure.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )  
{  
using namespace std;  
fstream file;  
file.exceptions(ios::failbit);  
try  
{  
file.open( "rm.txt", ios_base::in );  
// Opens nonexistent file for reading  
}  
catch( ios_base::failure f )  
{  
cout << "Caught an exception: " << f.what() << endl;  
}  
}  
  
```  
  
```Output  
Caught an exception: ios_base::failbit set  
```  
  
##  <a name="flags"></a>  ios_base::flags  
 Establece o devuelve la configuración actual de la marca.  
  
```  
 
fmtflags flags() const;

 
fmtflags flags(fmtflags fmtfl);
```  
  
### <a name="parameters"></a>Parámetros  
 `fmtfl`  
 Nueva configuración de `fmtflags`.  
  
### <a name="return-value"></a>Valor devuelto  
 Configuración anterior o actual de `fmtflags`.  
  
### <a name="remarks"></a>Comentarios  
 Vea [ios_base:: fmtflags](#fmtflags) para obtener una lista de marcas.  
  
 La primera función miembro devuelve las marcas de formato almacenadas. La segunda función miembro almacena `fmtfl` en las marcas de formato y devuelve su anterior valor almacenado.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// ios_base_flags.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )  
{  
using namespace std;  
cout << cout.flags( ) << endl;  
cout.flags( ios::dec | ios::boolalpha );  
cout << cout.flags( );  
}  
  
```  
  
```Output  
  
513  
16896  
  
```  
  
##  <a name="fmtflags"></a>  ios_base::fmtflags  
 Constantes para especificar la apariencia de la salida.  
  
class ios_base {  
   public:  
   typedef implementation-defined-bitmask-type fmtflags;  
   static const fmtflags boolalpha;  
   static const fmtflags dec;  
   static const fmtflags fixed;  
   static const fmtflags hex;  
   static const fmtflags internal;  
   static const fmtflags left;  
   static const fmtflags oct;  
   static const fmtflags right;  
   static const fmtflags scientific;  
   static const fmtflags showbase;  
   static const fmtflags showpoint;  
   static const fmtflags showpos;  
   static const fmtflags skipws;  
   static const fmtflags unitbuf;  
   static const fmtflags uppercase;  
   static const fmtflags adjustfield;  
   static const fmtflags basefield;  
   static const fmtflags floatfield;  
   ...  
   };  
  
### <a name="remarks"></a>Comentarios  
 Es compatible con los manipuladores de [ios](../standard-library/ios.md).  
  
 El tipo es un tipo de máscara de bits que describe un objeto que puede almacenar marcas de formato. Los distintos valores de marca (elementos) son:  
  
- `dec`, para insertar o extraer valores enteros en formato decimal.  
  
- `hex`, para insertar o extraer valores enteros en formato hexadecimal.  
  
- `oct`, para insertar o extraer valores enteros en formato octal.  
  
- `showbase`, para insertar un prefijo que revela la base de un campo numérico entero generado.  
  
- `internal`, para rellenar un ancho de campo tanto como sea necesario mediante la inserción de caracteres de relleno en un punto interno a un campo numérico generado. (Para obtener información sobre cómo establecer el ancho de campo, vea [setw](../standard-library/iomanip-functions.md#setw)).  
  
- `left`, para rellenar un ancho de campo tanto como sea necesario mediante la inserción de caracteres de relleno al final de un campo generado (justificación a la izquierda).  
  
- `right`, para rellenar un ancho de campo tanto como sea necesario mediante la inserción de caracteres de relleno al principio de un campo generado (justificación a la derecha).  
  
- `boolalpha`, para insertar o extraer objetos de tipo `bool`, como nombres (como `true` y `false`), en lugar de como valores numéricos.  
  
- `fixed`, para insertar valores de punto flotante en formato de punto fijo (sin campo de exponente).  
  
- `scientific`, para insertar valores de punto flotante en formato científico (con un campo de exponente).  
  
- `showpoint`, para insertar un separador decimal de manera incondicional en un campo de punto flotante generado.  
  
- `showpos`, para insertar un signo más en un campo numérico generado no negativo.  
  
- `skipws`, para omitir el espacio en blanco inicial antes de ciertas extracciones.  
  
- `unitbuf`, para vaciar los resultados después de cada inserción.  
  
- `uppercase`, para insertar los equivalentes en mayúsculas de letras en minúsculas en ciertas inserciones.  
  
 Además, varios valores útiles son:  
  
- `adjustfield`, una máscara de bits que se define como `internal` &#124; `left` &#124; `right`  
  
- `basefield`, que se define como `dec` &#124; `hex` &#124; `oct`  
  
- `floatfield`, que se define como `fixed` &#124; `scientific`  
  
 Para ver ejemplos de funciones que modifican estas marcas de formato, vea [\<iomanip>](../standard-library/iomanip.md).  
  
##  <a name="getloc"></a>  ios_base::getloc  
 Devuelve el objeto de configuración regional almacenado.  
  
```  
 
locale getloc() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 Objeto de configuración regional almacenado.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// ios_base_getlock.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
cout << cout.getloc( ).name( ).c_str( ) << endl;  
}  
  
```  
  
```Output  
C  
```  
  
##  <a name="imbue"></a>  ios_base::imbue  
 Cambia la configuración regional.  
  
```  
 
locale imbue(const locale& _Loc);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Loc`  
 Nueva configuración regional.  
  
### <a name="return-value"></a>Valor devuelto  
 Configuración regional anterior.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro almacena `_Loc` en el objeto de configuración regional y, después, notifica el evento de devolución de llamada y `imbue_event`. Devuelve el valor almacenado anterior.  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue) para obtener un ejemplo.  
  
##  <a name="init"></a>  ios_base::Init  
 Crea los objetos iostream estándar durante la construcción.  
  
class Init { };  
  
### <a name="remarks"></a>Comentarios  
 La clase anidada describe un objeto cuya construcción garantiza que los objetos de iostreams estándar se construyen correctamente, incluso antes de la ejecución de un constructor para un objeto estático arbitrario.  
  
##  <a name="ios_base"></a>  ios_base::ios_base  
 Crea objetos ios_base.  
  
```  
 
ios  
_  
base();
```  
  
### <a name="remarks"></a>Comentarios  
 El constructor (protegido) no hace nada. Una llamada posterior a **basic_ios::**[init](../standard-library/basic-ios-class.md#init) debe inicializar el objeto para que se pueda destruir con seguridad. Por lo tanto, el único uso seguro de la clase ios_base es como clase base para la clase de plantilla [basic_ios](../standard-library/basic-ios-class.md).  
  
##  <a name="iostate"></a>  ios_base::iostate  
 Tipo de constantes que describen el estado de un flujo.  
  
class ios_base {  
   public:  
   typedef implementation-defined-bitmask-type iostate;  
   static const iostate badbit;  
   static const iostate eofbit;  
   static const iostate failbit;  
   static const iostate goodbit;  
   ...  
   };  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un tipo de máscara de bits que describe un objeto que puede almacenar información sobre el estado del flujo. Los distintos valores de marca (elementos) son:  
  
- `badbit`, para registrar una pérdida de integridad del búfer de flujo.  
  
- `eofbit`, para registrar el final de archivo al extraer de un flujo.  
  
- `failbit`, para registrar un error al extraer un campo válido de un flujo.  
  
 Además, un valor útil es `goodbit`, en el que no se establece ninguno de los bits mencionados anteriormente (está garantizado que `goodbit` es cero).  
  
##  <a name="iword"></a>  ios_base::iword  
 Asigna un valor que se va a almacenar como `iword`.  
  
```  
 
long& iword(int idx);
```  
  
### <a name="parameters"></a>Parámetros  
 `idx`  
 Índice del valor que se va a almacenar como `iword`.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro devuelve una referencia al elemento `idx` de la matriz extensible con elementos de tipo **long**. Todos los elementos están presentes de forma eficaz y almacenan inicialmente el valor cero. La referencia devuelta no es válida después de la siguiente llamada a `iword` para el objeto, después de que el objeto se haya modificado mediante una llamada a **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) o después de que el objeto se haya destruido.  
  
 Si `idx` es negativo o si el almacenamiento único no está disponible para el elemento, la función llama a [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** y devuelve una referencia que podría no ser única.  
  
 Para obtener un índice único para su uso en todos los objetos de tipo `ios_base`, llame a [xalloc](#xalloc).  
  
### <a name="example"></a>Ejemplo  
  Vea [xalloc](#xalloc) para obtener un ejemplo del uso de `iword`.  
  
##  <a name="openmode"></a>  ios_base::openmode  
 Describe cómo interactuar con una secuencia.  
  
class ios_base {  
   public:  
   typedef implementation-defined-bitmask-type iostate;  
   static const iostate badbit;  
   static const iostate eofbit;  
   static const iostate failbit;  
   static const iostate goodbit;  
   ...  
   };  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un `bitmask type` que describe un objeto que puede almacenar el modo de apertura para varios objetos iostreams. Los distintos valores de marca (elementos) son:  
  
- **app**, para buscar el final de un flujo antes de cada inserción.  
  
- **ate**, para buscar el final de un flujo cuando se crea por primera vez su objeto de control.  
  
- **binary**, para leer un archivo como un flujo binario, en lugar de como un flujo de texto.  
  
- **in**, para permitir la extracción de un flujo.  
  
- **out**, para permitir la inserción en un flujo.  
  
- **trunc**, para eliminar contenido de un archivo existente cuando se crea su objeto de control.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// ios_base_openmode.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )  
{  
using namespace std;  
fstream file;  
file.open( "rm.txt", ios_base::out | ios_base::trunc );  
  
file << "testing";  
}  
  
```  
  
##  <a name="op_eq"></a>  ios_base::operator=  
 Operador de asignación de objetos ios_base.  
  
```  
 
ios  
_  
base& operator=(const ios  
_  
base& 
    right);
```  
  
### <a name="parameters"></a>Parámetros  
 `right`  
 Objeto de tipo `ios_base`.  
  
### <a name="return-value"></a>Valor devuelto  
 Objeto al que se va a asignar.  
  
### <a name="remarks"></a>Comentarios  
 El operador copia la información de formato almacenada y crea una nueva copia de las matrices extensibles. Después, devuelve **\*this**. Tenga en cuenta que la pila de devolución de llamada no se copia.  
  
 Este operador solo lo usan las clases derivadas de `ios_base`.  
  
##  <a name="precision"></a>  ios_base::precision  
 Especifica el número de dígitos que se debe mostrar en un número de punto flotante.  
  
```  
 
streamsize precision() const;

 
streamsize precision(streamsize _Prec);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Prec`  
 Número de dígitos significativos que se van a mostrar, o número de dígitos después del separador decimal en notación fija.  
  
### <a name="return-value"></a>Valor devuelto  
 La primera función miembro devuelve la [precisión de visualización](../standard-library/ios-base-class.md) almacenada. La segunda función miembro almacena `_Prec` en la precisión de visualización y devuelve su anterior valor almacenado.  
  
### <a name="remarks"></a>Comentarios  
 Los números de punto flotante se muestran en notación fija con [fixed](../standard-library/ios-functions.md#fixed).  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// ios_base_precision.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
float i = 31.31234F;  
  
cout.precision( 3 );  
cout << i << endl;          // display three significant digits  
cout << fixed << i << endl; // display three digits after decimal  
// point  
}  
  
```  
  
```Output  
  
31.3  
31.312  
  
```  
  
##  <a name="pword"></a>  ios_base::pword  
 Asigna un valor que se va a almacenar como `pword`.  
  
```  
 
void *& pword(int _Idx);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Idx`  
 Índice del valor que se va a almacenar como `pword`.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro devuelve una referencia al elemento _ *Idx* de la matriz extensible con elementos de puntero de tipo `void`. Todos los elementos están presentes de forma eficaz y almacenan inicialmente el puntero null. La referencia devuelta no es válida después de la siguiente llamada a `pword` para el objeto, después de que el objeto se haya modificado mediante una llamada a **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) o después de que el objeto se haya destruido.  
  
 Si _ *Idx* es negativo o si el almacenamiento único no está disponible para el elemento, la función llama a [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** y devuelve una referencia que podría no ser única.  
  
 Para obtener un índice único para su uso en todos los objetos de tipo `ios_base`, llame a [xalloc](#xalloc).  
  
### <a name="example"></a>Ejemplo  
  Vea [xalloc](#xalloc) para obtener un ejemplo que usa `pword`.  
  
##  <a name="register_callback"></a>  ios_base::register_callback  
 Especifica una función de devolución de llamada.  
  
```  
 
void register  
_  
callback(
    event 
_  
callback   
pfn  ,  
    int idx);
```  
  
### <a name="parameters"></a>Parámetros  
 `pfn`  
 Puntero a la función de devolución de llamada.  
  
 `idx`  
 Número definido por el usuario.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro inserta el par `{``pfn`, `idx``}` en la [pila de devolución de llamada](../standard-library/ios-base-class.md) almacenada. Cuando se notifica un evento de devolución de llamada **ev**, se la llama a las funciones en orden inverso de registro mediante la expresión ( **\***`pfn`)( **ev**, ``**\*this**, ```idx`).  
 
### <a name="example"></a>Ejemplo  
```  
  
// ios_base_register_callback.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
void callback1( ios_base::event e, ios_base& stream, int arg )  
{  
cout << "in callback1" << endl;  
switch ( e )  
{  
case ios_base::erase_event:  
cout << "an erase event" << endl;  
break;  
case ios_base::imbue_event:  
cout << "an imbue event" << endl;  
break;  
case ios_base::copyfmt_event:  
cout << "an copyfmt event" << endl;  
break;  
};  
}  
  
void callback2( ios_base::event e, ios_base& stream, int arg )  
{  
cout << "in callback2" << endl;  
switch ( e )  
{  
case ios_base::erase_event:  
cout << "an erase event" << endl;  
break;  
case ios_base::imbue_event:  
cout << "an imbue event" << endl;  
break;  
case ios_base::copyfmt_event:  
cout << "an copyfmt event" << endl;  
break;  
};  
}  
  
int main( )  
{  
// Make sure the imbue will not throw an exception  
// assert( setlocale( LC_ALL, "german" )!=NULL );  
  
cout.register_callback( callback1, 0 );  
cin.register_callback( callback2, 0 );  
  
try  
{  
// If no exception because the locale's not found,  
// generate an imbue_event on callback1  
cout.imbue(locale("german"));  
}  
catch(...)  
{  
cout << "exception" << endl;  
}  
  
// This will  
// (1) erase_event on callback1  
// (2) copyfmt_event on callback2  
cout.copyfmt(cin);  
  
// We get two erase events from callback2 at the end because  
// both cin and cout have callback2 registered when cin and cout  
// are destroyed at the end of program.  
}  
  
```  
```Output  
  
in callback1  
an imbue event  
in callback1  
an erase event  
in callback2  
an copyfmt event  
in callback2  
an erase event  
in callback2  
an erase event  
  
```  
 
##  <a name="seekdir"></a> ios_base::seekdir  
    Specifies starting point for offset operations.  
```  
  
namespace std {  
class ios_base {  
public:  
typedef implementation-defined-enumerated-type seekdir;  
static const seekdir beg;  
static const seekdir cur;  
static const seekdir end;  
...  
};  
}  
  
```  
 
### <a name="remarks"></a>Comentarios  
    The type is an enumerated type that describes an object that can store the seek mode used as an argument to the member functions of several iostream classes. The distinct flag values are:  
 
- **beg**, para buscar (modificar la posición actual de lectura o escritura) en relación con el principio de una secuencia (matriz, secuencia o archivo).  
 
- **cur**, para buscar en relación con la posición actual dentro de una secuencia.  
 
- **end**, para buscar en relación con el final de una secuencia.  
 
### <a name="example"></a>Ejemplo  
```  
  
// ios_base_seekdir.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )  
{  
using namespace std;  
fstream file;  
file.open( "rm.txt", ios_base::out | ios_base::trunc );  
  
file << "testing";  
file.seekp( 0, ios_base::beg );  
file << "a";  
file.seekp( 0, ios_base::end );  
file << "a";  
}  
  
```  
 
##  <a name="setf"></a> ios_base::setf  
    Sets the specified flags.  
```  
  
fmtflags setf(  
fmtflags _Mask  
);  
fmtflags setf(  
fmtflags _Mask,  
fmtflags _Unset  
);  
  
```  
 
### <a name="parameters"></a>Parámetros  
 `_Mask`  
    Marcas que se van a activar.  
 
 *_Unset* 
 Marcas que se van a desactivar.  
 
### <a name="return-value"></a>Valor devuelto  
    The previous format flags  
 
### <a name="remarks"></a>Comentarios  
    The first member function effectively calls [flags](#flags)(_ *Mask* &#124; \_ *Flags*) (set selected bits) and then returns the previous format flags. The second member function effectively calls **flags**(\_ *Mask* **& fmtfl, flags& ~**`_Mask`) (replace selected bits under a mask) and then returns the previous format flags.  
 
### <a name="example"></a>Ejemplo  
```  
  
// ios_base_setf.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
int i = 10;  
cout << i << endl;  
  
cout.unsetf( ios_base::dec );  
cout.setf( ios_base::hex );  
cout << i << endl;  
  
cout.setf( ios_base::dec );  
cout << i << endl;  
cout.setf( ios_base::hex, ios_base::dec );  
cout << i << endl;  
}  
  
```  
 
##  <a name="sync_with_stdio"></a> ios_base::sync_with_stdio  
    Ensures that iostream and C run-time library operations occur in the order that they appear in source code.  
```  
  
static bool sync  
_  
with  
_  
stdio(  
   bool   
_Sync  
=true  
);  
  
```  
 
### <a name="parameters"></a>Parámetros  
 `_Sync`  
    Indica si todos los flujos están sincronizados con **stdio**.  
 
### <a name="return-value"></a>Valor devuelto  
    Previous setting for this function.  
 
### <a name="remarks"></a>Comentarios  
    The static member function stores a **stdio** sync flag, which is initially **true**. When **true**, this flag ensures that operations on the same file are properly synchronized between the [iostreams](../standard-library/iostreams-conventions.md) functions and those defined in the C++ Standard Library. Otherwise, synchronization may or may not be guaranteed, but performance may be improved. The function stores `_Sync` in the **stdio** sync flag and returns its previous stored value. You can call it reliably only before performing any operations on the standard streams.  
 
##  <a name="unsetf"></a> ios_base::unsetf  
    Causes the specified flags to be off.  
```  
  
void unsetf(  
   fmtflags   
_Mask  
);  
  
```  
 
### <a name="parameters"></a>Parámetros  
 `_Mask`  
    Marcas que quiere desactivar.  
 
### <a name="remarks"></a>Comentarios  
    The member function effectively calls [flags](#flags)(`~`*_Mask* **& flags**) (clear selected bits).  
 
### <a name="example"></a>Ejemplo  
    See [ios_base::setf](#setf) for a sample of using `unsetf`.  
 
##  <a name="width"></a> ios_base::width  
    Sets the length of the output stream.  
```  
  
streamsize width( ) const;  
streamsize width(  
   streamsize   
_Wide  
);  
  
```  
 
### <a name="parameters"></a>Parámetros  
 `_Wide`  
    Tamaño deseado del flujo de salida.  
 
### <a name="return-value"></a>Valor devuelto  
    The current width setting.  
 
### <a name="remarks"></a>Comentarios  
    The first member function returns the stored field width. The second member function stores `_Wide` in the field width and returns its previous stored value.  
 
### <a name="example"></a>Ejemplo  
```  
  
// ios_base_width.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( ) {  
using namespace std;  
  
cout.width( 20 );  
cout << cout.width( ) << endl;  
cout << cout.width( ) << endl;  
}  
  
```  
```Output  
  
20  
0  
  
```  
 
##  <a name="xalloc"></a> ios_base::xalloc  
    Specifies that a variable is part of the stream.  
```  
  
static int xalloc( );  
  
```  
 
### <a name="return-value"></a>Valor devuelto  
    The static member function returns a stored static value, which it increments on each call.  
 
### <a name="remarks"></a>Comentarios  
    You can use the return value as a unique index argument when calling the member functions [iword](#iword) or [pword](#pword).  
 
### <a name="example"></a>Ejemplo  
```  
  
// ios_base_xalloc.cpp  
// compile with: /EHsc  
// Lets you store user-defined information.  
// iword, jword, xalloc  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
static const int i = ios_base::xalloc();  
static const int j = ios_base::xalloc();  
cout.iword( i ) = 11;  
cin.iword( i ) = 13;  
cin.pword( j ) = "testing";  
cout << cout.iword( i ) << endl;  
cout << cin.iword( i ) << endl;  
cout << ( char * )cin.pword( j ) << endl;  
}  
  
```  
```Output  
  
11  
13  
testing  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programación con iostream](../standard-library/iostream-programming.md)   
 [Convenciones de iostreams](../standard-library/iostreams-conventions.md)




