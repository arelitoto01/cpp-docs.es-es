---
title: basic_fstream (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_fstream
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_fstream class
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
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
ms.openlocfilehash: f9d52128703d021ba3a880ff899ca71b144e89ec
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="basicfstream-class"></a>basic_fstream (Clase)
Describe un objeto que controla la inserción y la extracción de elementos y objetos codificados mediante un búfer de flujo de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, con elementos de tipo `Elem`, cuyos rasgos de caracteres están determinados por la clase `Tr`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Elem`  
 Elemento básico del búfer del archivo.  
  
 `Tr`  
 Rasgos del elemento básico del búfer del archivo (normalmente `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Comentarios  
 El objeto almacena un objeto de clase `basic_filebuf`< `Elem`, `Tr`>.  
  
> [!NOTE]
>  El puntero get y el puntero put de un objeto fstream **NO** son independientes el uno del otro. Si el puntero get se mueve, también lo hace el puntero put.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un objeto `basic_fstream` del que se puede leer y en el que se puede escribir.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
```Output  
Writing to a basic_fstream object...  
```  
  
### <a name="constructors"></a>Constructores  
  
|||  
|-|-|  
|[basic_fstream](#basic_fstream)|Construye un objeto de tipo `basic_fstream`.|  
  
### <a name="member-functions"></a>Funciones miembro  
  
|||  
|-|-|  
|[close](#close)|Cierra un archivo.|  
|[is_open](#is_open)|Determina si un archivo está abierto.|  
|[open](#open)|Abre un archivo.|  
|[rdbuf](#rdbuf)|Devuelve la dirección del búfer de flujo almacenado de puntero de tipo a [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>.|  
|[swap](#swap)|Intercambia el contenido de este objeto con el contenido de otro objeto `basic_fstream`.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<fstream>  
  
 **Espacio de nombres:** std  
  
##  <a name="basic_fstream"></a>  basic_fstream::basic_fstream  
 Construye un objeto de tipo `basic_fstream`.  
  
```  
basic_fstream();

explicit basic_fstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Filename`  
 Nombre del archivo que se va a abrir.  
  
 `_Mode`  
 Una de las enumeraciones de [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protección predeterminada de apertura del archivo, equivalente al parámetro `shflag` de [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Comentarios  
 El primer constructor inicializa la clase base al llamar a [basic_iostream](../standard-library/basic-iostream-class.md)(**sb**), donde **sb** es el objeto almacenado de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>. También inicializa **sb** al llamar a `basic_filebuf`\< **Elem**, **Tr**>.  
  
 El segundo y el tercer constructor inicializan la clase base al llamar a `basic_iostream`(**sb**). También inicializa **sb** al llamar a `basic_filebuf`\< **Elem**, **Tr**> y luego a **sb.**[open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Si esta última función devuelve un puntero nulo, el constructor llama a [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**).  
  
 El cuarto constructor inicializa el objeto con el contenido de `right`, tratado como una referencia a un valor R.  
  
### <a name="example"></a>Ejemplo  
  Vea [streampos](../standard-library/ios-typedefs.md#streampos) para obtener un ejemplo de uso de `basic_fstream`.  
  
##  <a name="close"></a>  basic_fstream::close  
 Cierra un archivo.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Comentarios  
 La función miembro llama a [rdbuf](#rdbuf)**->** [close](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) para obtener un ejemplo de uso de **close**.  
  
##  <a name="is_open"></a>  basic_fstream::is_open  
 Determina si un archivo está abierto.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 **True** si el archivo está abierto, **False** en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro devuelve [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) para obtener un ejemplo de uso de `is_open`.  
  
##  <a name="open"></a>  basic_fstream::open  
 Abre un archivo.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Filename`  
 Nombre del archivo que se va a abrir.  
  
 `_Mode`  
 Una de las enumeraciones de [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protección predeterminada de apertura del archivo, equivalente al parámetro `shflag` de [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Comentarios  
 La función miembro llama a [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Si esa función devuelve un puntero nulo, la función llama a [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**).  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) para obtener un ejemplo de uso de **open**.  
  
##  <a name="op_eq"></a>  basic_fstream::operator=  
 Asigna a este objeto el contenido de un objeto de flujo especificado. Se trata de una asignación de movimiento que implica un valor que no deja ninguna copia.  
  
```  
basic_fstream& operator=(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `right`  
 Referencia lvalue a un objeto `basic_fstream`.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `*this`.  
  
### <a name="remarks"></a>Comentarios  
 El operador de miembro reemplaza el contenido del objeto por el contenido de `right`, que se trata como referencia rvalue.  
  
##  <a name="rdbuf"></a>  basic_fstream::rdbuf  
 Devuelve la dirección del búfer de flujo almacenado de puntero de tipo a [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Valor devuelto  
 Dirección del búfer de flujo almacenado.  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) para obtener un ejemplo de uso de `rdbuf`.  
  
##  <a name="swap"></a>  basic_fstream::swap  
 Intercambia el contenido de dos objetos `basic_fstream`.  
  
```  
void swap(basic_fstream& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `right`  
 Referencia `lvalue` a un objeto `basic_fstream`.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro intercambia el contenido de este objeto por el contenido de `right`.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programación con iostream](../standard-library/iostream-programming.md)   
 [Convenciones de iostreams](../standard-library/iostreams-conventions.md)

