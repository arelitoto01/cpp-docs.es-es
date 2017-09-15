---
title: Clase CStringT | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringT
- No header/ATL::CStringT
- No header/ATL::CStringT::CStringT
- No header/ATL::CStringT::AllocSysString
- No header/ATL::CStringT::AnsiToOem
- No header/ATL::CStringT::AppendFormat
- No header/ATL::CStringT::Collate
- No header/ATL::CStringT::CollateNoCase
- No header/ATL::CStringT::Compare
- No header/ATL::CStringT::CompareNoCase
- No header/ATL::CStringT::Delete
- No header/ATL::CStringT::Find
- No header/ATL::CStringT::FindOneOf
- No header/ATL::CStringT::Format
- No header/ATL::CStringT::FormatMessage
- No header/ATL::CStringT::FormatMessageV
- No header/ATL::CStringT::FormatV
- No header/ATL::CStringT::GetEnvironmentVariable
- No header/ATL::CStringT::Insert
- No header/ATL::CStringT::Left
- No header/ATL::CStringT::LoadString
- No header/ATL::CStringT::MakeLower
- No header/ATL::CStringT::MakeReverse
- No header/ATL::CStringT::MakeUpper
- No header/ATL::CStringT::Mid
- No header/ATL::CStringT::OemToAnsi
- No header/ATL::CStringT::Remove
- No header/ATL::CStringT::Replace
- No header/ATL::CStringT::ReverseFind
- No header/ATL::CStringT::Right
- No header/ATL::CStringT::SetSysString
- No header/ATL::CStringT::SpanExcluding
- No header/ATL::CStringT::SpanIncluding
- No header/ATL::CStringT::Tokenize
- No header/ATL::CStringT::Trim
- No header/ATL::CStringT::TrimLeft
- No header/ATL::CStringT::TrimRight
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 4f5e485611b1a8f38375c9a95a959ddf48e3663c
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="cstringt-class"></a>CStringT (clase)
Esta clase representa un `CStringT` objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
 
template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>  
 
```  
  
#### <a name="parameters"></a>Parámetros  
 `BaseType`  
 El tipo de carácter de la clase string. Puede ser uno de los siguientes:  
  
- `char`(para cadenas de caracteres ANSI).  
  
- `wchar_t`(para cadenas de caracteres Unicode).  
  
- **TCHAR** (para cadenas de caracteres ANSI y Unicode).  
  
 `StringTraits`  
 Determina si la clase string necesita compatibilidad con bibliotecas de tiempo de ejecución de C (CRT) y donde se encuentran los recursos de cadena. Puede ser uno de los siguientes:  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La clase requiere compatibilidad con CRT y busca las cadenas de recursos en el módulo especificado por `m_hInstResource` (un miembro de clase de módulo de la aplicación).  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La clase no requiere compatibilidad con CRT y las búsquedas de cadenas de recursos en el módulo especificado por `m_hInstResource` (un miembro de clase de módulo de la aplicación).  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La clase requiere compatibilidad con CRT y las búsquedas de cadenas de recursos mediante el algoritmo de búsqueda MFC estándar.  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La clase no requiere compatibilidad con CRT y las búsquedas de cadenas de recursos mediante el algoritmo de búsqueda MFC estándar.  
  
## <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Construye un `CStringT` objeto de varias maneras.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Destruye un objeto `CStringT`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Asigna un `BSTR` de `CStringT` datos.|  
|[CStringT::AnsiToOem](#ansitooem)|Realiza una conversión en lugar de caracteres ANSI establecido en el juego de caracteres OEM.|  
|[CStringT::AppendFormat](#appendformat)|Anexa datos con formato en una existente `CStringT` objeto.|  
|[CStringT::Collate](#collate)|Compara dos cadenas (mayúsculas y minúsculas, utiliza la información de configuración regional).|  
|[CStringT::CollateNoCase](#collatenocase)|Compara dos cadenas (mayúsculas y minúsculas, utiliza la información de configuración regional).|  
|[CStringT::Compare](#compare)|Compara dos cadenas (con distinción entre mayúsculas y minúsculas).|  
|[CStringT::CompareNoCase](#comparenocase)|Compara dos cadenas (con distinción entre mayúsculas y minúsculas).|  
|[CStringT::Delete](#delete)|Elimina un carácter o caracteres de una cadena.|  
|[CStringT::Find](#find)|Busca un carácter o una subcadena dentro de una cadena mayor.|  
|[CStringT::FindOneOf](#findoneof)|Busca el primer carácter coincidente de un conjunto.|  
|[CStringT::Format](#format)|Formato de la cadena como `sprintf` does.|  
|[CStringT::FormatMessage](#formatmessage)|Da formato a una cadena de mensaje.|  
|[CStringT::FormatMessageV](#formatmessagev)|Da formato a una cadena de mensaje con una lista de argumentos de variable.|  
|[CStringT::FormatV](#formatv)|Formato de la cadena con una lista variable de argumentos.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Establece la cadena en el valor de la variable de entorno especificada.|  
|[CStringT::Insert](#insert)|Inserta un carácter o una subcadena en el índice especificado dentro de la cadena.|  
|[CStringT::Left](#left)|Extrae la parte izquierda de una cadena.|  
|[CStringT::LoadString](#loadstring)|Carga una existente `CStringT` objeto desde un recurso de Windows.|  
|[CStringT::MakeLower](#makelower)|Convierte todos los caracteres de esta cadena a caracteres en minúsculas.|  
|[CStringT::MakeReverse](#makereverse)|Invierte la cadena.|  
|[CStringT::MakeUpper](#makeupper)|Convierte todos los caracteres de esta cadena a caracteres en mayúsculas.|  
|[CStringT::Mid](#mid)|Extrae la parte central de una cadena.|  
|[CStringT::OemToAnsi](#oemtoansi)|Realiza una conversión en lugar del juego al juego de caracteres ANSI de caracteres OEM.|  
|[CStringT::Remove](#remove)|Quita indica caracteres de una cadena.|  
|[CStringT::Replace](#replace)|Reemplaza indica caracteres con otros caracteres.|  
|[CStringT::ReverseFind](#reversefind)|Busca un carácter dentro de una cadena mayor; se inicia desde el final.|  
|[CStringT::Right](#right)|Extrae la parte derecha de una cadena.|  
|[CStringT::SetSysString](#setsysstring)|Establece una existente `BSTR` objeto con datos procedentes de un `CStringT` objeto.|  
|[CStringT::SpanExcluding](#spanexcluding)|Extrae caracteres de la cadena, comenzando por el primer carácter, que no están en el juego de caracteres identificados por `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Extrae una subcadena que contiene solo los caracteres en un conjunto.|  
|[CStringT::Tokenize](#tokenize)|Extrae especifica tokens en una cadena de destino.|  
|[CStringT::Trim](#trim)|Quita todos los caracteres de espacio en blanco iniciales y finales de la cadena.|  
|[CStringT::TrimLeft](#trimleft)|Quita los caracteres de espacio en blanco de la cadena.|  
|[CStringT::TrimRight](#trimright)|Quita los caracteres de espacio en blanco de la cadena finales.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operador =](#operator_eq)|Asigna un nuevo valor a un `CStringT` objeto.|  
|[CStringT::operator +](#operator_add)|Concatena dos cadenas o un carácter y una cadena.|  
|[CStringT::operator +=](#operator_add_eq)|Concatena una nueva cadena al final de una cadena existente.|  
|[CStringT::operator ==](#operator_eq_eq)|Determina si dos cadenas son lógicamente iguales.|  
|[CStringT::operator! =](#operator_neq)|Determina si dos cadenas lógicamente no son iguales.|  
|[CStringT::operator&lt;](#operator_lt)|Determina si la cadena en el lado izquierdo del operador es menor que la cadena del lado derecho.|  
|[CStringT::operator&gt;](#operator_gt)|Determina si la cadena en el lado izquierdo del operador es mayor que la cadena del lado derecho.|  
|[CStringT::operator&lt;=](#operator_lt_eq)|Determina si la cadena en el lado izquierdo del operador es menor o igual que la cadena del lado derecho.|  
|[CStringT::operator&gt;=](#operator_gt_eq)|Determina si la cadena en el lado izquierdo del operador es mayor o igual que la cadena del lado derecho.|  
  
## <a name="remarks"></a>Comentarios  
 `CStringT`hereda de [CSimpleStringT clase](../../atl-mfc-shared/reference/csimplestringt-class.md). Características avanzadas, como la manipulación de caracteres, ordenación y búsqueda, se implementan mediante `CStringT`.  
  
> [!NOTE]
> `CStringT`los objetos son capaces de producir excepciones. Esto se produce cuando un `CStringT` objeto se ejecuta fuera de memoria por cualquier motivo.  
  
 Un `CStringT` objeto consta de una secuencia de longitud variable de caracteres. `CStringT`proporciona funciones y operadores mediante una sintaxis similar a la de Basic. Asegúrese de concatenación y operadores de comparación, junto con la administración simplificada de la memoria, `CStringT` objetos fáciles de usar que las matrices de caracteres ordinarios.  
  
> [!NOTE]
>  Aunque es posible crear `CStringT` instancias que contienen caracteres null incrustan, se recomienda en él. Al llamar a métodos y operadores en `CStringT` objetos que contienen caracteres nulos incrustados pueden generar resultados no deseados.  
  
 Mediante el uso de combinaciones diferentes de la `BaseType` y `StringTraits` parámetros, `CStringT` objetos puede entrar en los siguientes tipos, que están predefinido por las bibliotecas ATL.  
  
 Si se utiliza en una aplicación ATL:  
  
 `CString`, `CStringA`, y `CStringW` se exportan desde la DLL de MFC (MFC90. DLL), nunca en archivos DLL de usuario. Esto se hace para evitar `CStringT` desde que se definió varias veces.  
  
> [!NOTE]
>  Si encontró errores del vinculador al exportar una `CString`-clase derivada de una extensión MFC DLL en Visual C++ .NET 2002 y se les aplique la solución como se describe en el artículo de Knowledge Base, "Vinculación errores When You Import CString-Derived Classes" (Q309801), debe quitar el código de dicha solución, ya que esto se ha solucionado en Visual C++ .NET 2003. Encontrará artículos de Knowledge Base en [http://support.microsoft.com/support](http://support.microsoft.com/support).  
  
 Los tipos de cadena siguientes están disponibles en las aplicaciones basadas en MFC:  
  
|Tipo de CStringT|Declaración|  
|-------------------|-----------------|  
|`CStringA`|Un carácter ANSI escriba la cadena con el soporte técnico de CRT.|  
|`CStringW`|Un carácter Unicode escriba la cadena con el soporte técnico de CRT.|  
|`CString`|Tipos de caracteres de ANSI y Unicode con compatibilidad con CRT.|  
  
 La siguiente cadena de tipos están disponibles en los proyectos where **ATL_CSTRING_NO_CRT** se define:  
  
|Tipo de CStringT|Declaración|  
|-------------------|-----------------|  
|**CAtlStringA**|Un carácter ANSI escriba una cadena sin compatibilidad con CRT.|  
|**CAtlStringW**|Un carácter Unicode se escriba una cadena sin compatibilidad con CRT.|  
|**CAtlString**|Tipos de caracteres de ANSI y Unicode sin compatibilidad con CRT.|  
  
 La siguiente cadena de tipos están disponibles en los proyectos where **ATL_CSTRING_NO_CRT** no está definido:  
  
|Tipo de CStringT|Declaración|  
|-------------------|-----------------|  
|**CAtlStringA**|Un carácter ANSI escriba la cadena con el soporte técnico de CRT.|  
|**CAtlStringW**|Un carácter Unicode escriba la cadena con el soporte técnico de CRT.|  
|**CAtlString**|Tipos de caracteres de ANSI y Unicode con compatibilidad con CRT.|  
  
 `CString`objetos también tienen las siguientes características:  
  
- `CStringT`objetos pueden crecer como resultado de las operaciones de concatenación.  
  
- `CStringT`objetos siguen "semántica de valores". Piense en un `CStringT` objeto como una cadena real, no como un puntero a una cadena.  
  
-   Puede sustituir libremente `CStringT` de objetos para `PCXSTR` los argumentos de función.  
  
-   Administración de memoria personalizado para los búferes de cadena. Para obtener más información, consulte [administración de memoria y CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT los tipos predefinidos  
 Dado que `CStringT` usa un argumento de plantilla para definir el tipo de caracteres (ya sea [wchar_t](../../c-runtime-library/standard-types.md) o [char](../../c-runtime-library/standard-types.md)) compatibles, tipos de parámetro de método pueden ser complicados en ocasiones. Para simplificar este problema, se define un conjunto de tipos predefinidos y se usa en toda la `CStringT` clase. En la tabla siguiente se enumera los distintos tipos:  
  
|Nombre|Descripción|  
|----------|-----------------|  
|`XCHAR`|Un único carácter (ya sea `wchar_t` o `char`) con el mismo tipo de caracteres que el `CStringT` objeto.|  
|**YCHAR**|Un único carácter (ya sea `wchar_t` o `char`) con el tipo de carácter opuesto como la `CStringT` objeto.|  
|`PXSTR`|Un puntero a una cadena de caracteres (ya sea `wchar_t` o `char`) con el mismo tipo de caracteres que el `CStringT` objeto.|  
|**PYSTR**|Un puntero a una cadena de caracteres (ya sea `wchar_t` o `char`) con el tipo de carácter opuesto como la `CStringT` objeto.|  
|`PCXSTR`|Un puntero a un **const** la cadena de caracteres (ya sea `wchar_t` o `char`) con el mismo tipo de caracteres que el `CStringT` objeto.|  
|**PCYSTR**|Un puntero a un **const** la cadena de caracteres (ya sea `wchar_t` o `char`) con el tipo de carácter opuesto como la `CStringT` objeto.|  
  
> [!NOTE]
>  Código que anteriormente usó los métodos no documentadas de `CString` (como **AssignCopy**) deben reemplazarse por código que usa los siguientes métodos documentados de `CStringT` (como `GetBuffer` o `ReleaseBuffer`). Estos métodos se heredan de `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Requisitos  
  
|Header|Uso de|  
|------------|-------------|  
|CStringT.h|Objetos de cadena solo MFC|  
|atlstr.h|Objetos de cadena no están basados en MFC|  
  
##  <a name="allocsysstring"></a>CStringT::AllocSysString  
 Asigna una cadena compatibles con la automatización del tipo `BSTR` y copia el contenido de la `CStringT` objeto en él, incluido el carácter nulo final.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Valor devuelto  
 La cadena recién asignada.  
  
### <a name="remarks"></a>Comentarios  
 En programas MFC, un [CMemoryException clase](../../mfc/reference/cmemoryexception-class.md) se produce si no existe suficiente memoria. En los programas ATL, un [CAtlException](../../atl/reference/catlexception-class.md) se produce. Esta función se utiliza normalmente para devolver las cadenas para la automatización.  
  
 Normalmente, si esta cadena se pasa a una función COM como [in] parámetro, a continuación, esto requiere que el llamador liberar la cadena. Esto puede hacerse mediante el uso de [SysFreeString](http://msdn.microsoft.com/en-us/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3), tal y como se describe en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Para obtener más información, consulte [asignar y liberar memoria para un BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Para obtener más información acerca de las funciones de asignación de OLE en Windows, consulte [SysAllocString](http://msdn.microsoft.com/en-us/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b) en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el uso de `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities #105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="ansitooem"></a>CStringT::AnsiToOem  
 Convierte todos los caracteres en este `CStringT` objeto a partir de caracteres ANSI establecido en el juego de caracteres OEM.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Comentarios  
 La función no está disponible si `_UNICODE` está definido.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="appendformat"></a>CStringT::AppendFormat  
 Anexa datos con formato en una existente `CStringT` objeto.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Parámetros  
 `pszFormat`  
 Una cadena de formato de control.  
  
 `nFormatID`  
 El identificador de recurso de cadena que contiene la cadena de formato de control.  
  
 `argument`  
 Argumentos opcionales.  
  
### <a name="remarks"></a>Comentarios  
 Esta función se da formato y se anexa una serie de caracteres y valores en el `CStringT`. Cada argumento opcional (si existe) se convierte y se anexa según la especificación de formato correspondiente de `pszFormat` o desde el recurso de cadena identificada por `nFormatID`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="collate"></a>CStringT::Collate  
 Compara dos cadenas utilizando la función de texto genérico `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `psz`  
 La otra cadena utilizada para la comparación.  
  
### <a name="return-value"></a>Valor devuelto  
 Cero si las cadenas son idénticas, < 0 si este `CStringT` objeto es menor que `psz`, o 0 > Si este `CStringT` objeto es mayor que `psz`.  
  
### <a name="remarks"></a>Comentarios  
 La función de texto genérico `_tcscoll`, que se define en TCHAR. H, se asigna a una `strcoll`, `wcscoll`, o `_mbscoll`, según el juego de caracteres que se define en tiempo de compilación. Cada función realiza una comparación entre mayúsculas y minúsculas de las cadenas según la página de códigos actualmente en uso. Para obtener más información, consulte [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="collatenocase"></a>CStringT::CollateNoCase  
 Compara dos cadenas utilizando la función de texto genérico `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `psz`  
 La otra cadena utilizada para la comparación.  
  
### <a name="return-value"></a>Valor devuelto  
 Cero si las cadenas son idénticos (mayúsculas y minúsculas y pasa por alto), < 0 si este `CStringT` objeto es menor que `psz` (mayúsculas de minúsculas), o > 0 si esto `CStringT` objeto es mayor que `psz` (mayúsculas de minúsculas).  
  
### <a name="remarks"></a>Comentarios  
 La función de texto genérico `_tcscoll`, que se define en TCHAR. H, se asigna a una `stricoll`, `wcsicoll`, o `_mbsicoll`, según el juego de caracteres que se define en tiempo de compilación. Cada función realiza una comparación entre mayúsculas y minúsculas de las cadenas, según la página de códigos actualmente en uso. Para obtener más información, consulte [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="compare"></a>CStringT::Compare  
 Compara dos cadenas (con distinción entre mayúsculas y minúsculas).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `psz`  
 La otra cadena utilizada para la comparación.  
  
### <a name="return-value"></a>Valor devuelto  
 Cero si las cadenas son idénticas, < 0 si este `CStringT` objeto es menor que `psz`, o 0 > Si este `CStringT` objeto es mayor que `psz`.  
  
### <a name="remarks"></a>Comentarios  
 La función de texto genérico `_tcscmp`, que se define en TCHAR. H, se asigna a una `strcmp`, `wcscmp`, o `_mbscmp`, según el juego de caracteres que se define en tiempo de compilación. Cada función realiza una comparación entre mayúsculas y minúsculas de las cadenas y no se ve afectada por la configuración regional. Para obtener más información, consulte [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Si la cadena contiene valores null incrustados, la cadena se considera de manera para fines de comparación que se trunca en el primer carácter nulo incrustado.  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el uso de `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities #110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="comparenocase"></a>CStringT::CompareNoCase  
 Compara dos cadenas (con distinción entre mayúsculas y minúsculas).  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `psz`  
 La otra cadena utilizada para la comparación.  
  
### <a name="return-value"></a>Valor devuelto  
 Cero si las cadenas son idénticas (mayúsculas de minúsculas), < 0 si esto `CStringT` objeto es menor que `psz` (mayúsculas de minúsculas), o > 0 si esto `CStringT` objeto es mayor que `psz` (mayúsculas de minúsculas).  
  
### <a name="remarks"></a>Comentarios  
 La función de texto genérico `_tcsicmp`, que se define en TCHAR. H, se asigna a una `_stricmp`, `_wcsicmp` o `_mbsicmp`, según el juego de caracteres que se define en tiempo de compilación. Cada función realiza una comparación entre mayúsculas y minúsculas de las cadenas. La comparación depende de la `LC_CTYPE` aspecto de la configuración regional, pero no `LC_COLLATE`. Para obtener más información, consulte [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="cstringt"></a>CStringT::CStringT  
 Construye un objeto `CStringT`.  
  
```  
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());
 
explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);
 
CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);
 
CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

 operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()  
 
template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);
 
template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());
 
CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);
 
CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```  
  
### <a name="parameters"></a>Parámetros  
 `pch`  
 Un puntero a una matriz de caracteres de longitud `nLength`no terminada en null.  
  
 `nLength`  
 Un recuento del número de caracteres en `pch`.  
  
 `ch`  
 Un único carácter.  
  
 `pszSrc`  
 Una cadena terminada en null que se copiará en esto `CStringT` objeto.  
  
 `pStringMgr`  
 Un puntero al administrador de memoria para el `CStringT` objeto. Para obtener más información sobre `IAtlStringMgr` y administración de memoria para `CStringT`, consulte [administración de memoria con CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Existente `CStringT` objeto que se copiará en esto `CStringT` objeto. Para obtener más información sobre `CThisString` y `CThisSimpleString`, vea la sección Comentarios.  
  
 `varSrc`  
 Un objeto variant que se copiará en esto `CStringT` objeto.  
  
 `BaseType`  
 El tipo de carácter de la clase string. Puede ser uno de los siguientes:  
  
 `char`(para cadenas de caracteres ANSI).  
  
 `wchar_t`(para cadenas de caracteres Unicode).  
  
 `TCHAR`(ANSI y Unicode para cadenas de caracteres).  
  
 `bMFCDLL`  
 Un valor booleano que especifica si el proyecto es un archivo DLL de MFC (TRUE) o no (FALSE).  
  
 `SystemString`  
 Debe ser `System::String`, y el proyecto se debe compilar con/CLR.  
  
 `pString`  
 Un identificador para un `CStringT` objeto.  
  
### <a name="remarks"></a>Comentarios  
 Puesto que los constructores copian los datos de entrada en el nuevo almacenamiento asignado, debe tener en cuenta que pueden dar lugar a excepciones de la memoria. Tenga en cuenta que algunos de estos constructores actúen como funciones de conversión. Esto le permite sustituir, por ejemplo, un `LPTSTR` donde un `CStringT` se espera el objeto.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Construye Unicode `CStringT` de una cadena ANSI. También puede utilizar este constructor para cargar un recurso de cadena, como se muestra en el ejemplo siguiente.  
  
- `CStringT(``LPCWSTR` `lpsz` ): Crea un `CStringT` de una cadena Unicode.  
  
- `CStringT`( `const unsigned char*` `psz` ): Permite construir una `CStringT` de un puntero a `unsigned char`.  
  
> [!NOTE]
>  Definir la **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** macro para desactivar la conversión implícita de cadena entre [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] y [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] cadenas. La macro se excluye de los constructores de compilación que admiten la conversión.  
  
 Tenga en cuenta que la `strSrc` parámetro puede ser un `CStringT` o `CThisSimpleString` objeto. Para `CStringT`, use uno de sus instancias predeterminadas ( `CString`, `CStringA`, o `CStringW`); para `CThisSimpleString`, use un `this` puntero. `CThisSimpleString`declara una instancia de la [CSimpleStringT clase](../../atl-mfc-shared/reference/csimplestringt-class.md), que es una clase de cadena más pequeña con funcionalidad integrada menor que el `CStringT` clase.  
  
 El operador de sobrecarga `CSimpleStringT<>&()` construye una `CStringT` objeto desde un `CSimpleStringT` declaración.  
  
> [!NOTE]
>  Aunque es posible crear `CStringT` instancias que contienen caracteres null incrustan, se recomienda en él. Al llamar a métodos y operadores en `CStringT` objetos que contienen caracteres nulos incrustados pueden generar resultados no deseados.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="_dtorcstringt"></a>CStringT:: ~ CStringT  
 Destruye el objeto `CStringT`.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Comentarios  
 Destruye el objeto `CStringT`.  
  
##  <a name="delete"></a>CStringT::Delete  
 Elimina un carácter o caracteres de una cadena a partir de los caracteres en el índice especificado.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Parámetros  
 `iIndex`  
 Índice de base cero del primer carácter en la `CStringT` objeto que se va a eliminar.  
  
 `nCount`  
 El número de caracteres que se va a quitar.  
  
### <a name="return-value"></a>Valor devuelto  
 La longitud de la cadena modificada.  
  
### <a name="remarks"></a>Comentarios  
 Si `nCount` es más largo de la cadena, el resto de la cadena que se va a quitar.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="find"></a>CStringT::Find  
 Busca la primera coincidencia de un carácter o subcadena esta cadena.  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `pszSub`  
 Una subcadena que se va a buscar.  
  
 `iStart`  
 El índice del carácter en la cadena para iniciar la búsqueda con, o 0 para iniciar desde el principio.  
  
 `ch`  
 Un único carácter que se va a buscar.  
  
### <a name="return-value"></a>Valor devuelto  
 Índice de base cero del primer carácter en esta `CStringT` objeto que coincide con la subcadena solicitada o caracteres; -1 si no se encuentra la subcadena o caracteres.  
  
### <a name="remarks"></a>Comentarios  
 La función se sobrecarga para aceptar ambos caracteres individuales (similar a la función de tiempo de ejecución `strchr`) y cadenas (similar a `strstr`).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="findoneof"></a>CStringT::FindOneOf  
 Busca en esta cadena para el primer carácter que coincide con cualquier carácter que se encuentra en `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `pszCharSet`  
 Cadena que contiene caracteres de coincidencia.  
  
### <a name="return-value"></a>Valor devuelto  
 Índice de base cero del primer carácter de esta cadena que también está disponible en `pszCharSet`; -1 si no hay ninguna coincidencia.  
  
### <a name="remarks"></a>Comentarios  
 Busca la primera aparición de cualquiera de los caracteres de `pszCharSet`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="format"></a>CStringT::Format  
 Escribe datos con formato en un `CStringT` en la misma forma en que [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) da formato a datos en una matriz de caracteres de estilo C.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Parámetros  
 `nFormatID`  
 El identificador de recurso de cadena que contiene la cadena de formato de control.  
  
 `pszFormat`  
 Una cadena de formato de control.  
  
 `argument`  
 Argumentos opcionales.  
  
### <a name="remarks"></a>Comentarios  
 Esta función da formato y almacena una serie de caracteres y valores en el `CStringT`. Cada argumento opcional (si existe) se convierte y sale según la especificación de formato correspondiente de `pszFormat` o desde el recurso de cadena identificada por `nFormatID`.  
  
 Se producirá un error en la llamada si el propio objeto de cadena se proporciona como un parámetro a `Format`. Por ejemplo, el código siguiente provocará resultados impredecibles:  
  
 [!code-cpp[NVC_ATLMFC_Utilities #116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Para obtener más información, vea [Sintaxis de especificación de formato: Funciones printf y wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="formatmessage"></a>CStringT::FormatMessage  
 Da formato a una cadena de mensaje.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Parámetros  
 `nFormatID`  
 El identificador de recurso de cadena que contiene el texto del mensaje sin formato.  
  
 `pszFormat`  
 Apunta a la cadena de formato de control. Se examinan para las inserciones y con formato en consecuencia. La cadena de formato es similar a la función en tiempo de ejecución `printf`-aplicar estilo a las cadenas de formato, salvo que permite para que los parámetros que se van a insertar en un orden arbitrario.  
  
 `argument`  
 Argumentos opcionales.  
  
### <a name="remarks"></a>Comentarios  
 La función requiere una definición de mensaje como entrada. La definición del mensaje viene determinada por `pszFormat` o desde el recurso de cadena identificada por `nFormatID`. La función copia el texto del mensaje con formato para la `CStringT` objeto, procesar ninguna incrustado Inserta secuencias si se solicita.  
  
> [!NOTE]
> `FormatMessage`intenta asignar memoria del sistema para la cadena ha dado formateada recientemente. Si se produce un error en este intento, automáticamente se produce una excepción de memoria.  
  
 Cada inserción debe tener un parámetro correspondiente que sigue el `pszFormat` o `nFormatID` parámetro. En el texto del mensaje, se admiten varias secuencias de escape para dinámicamente dar formato al mensaje. Para obtener más información, consulte las ventanas [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) funcionando en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="formatmessagev"></a>CStringT::FormatMessageV  
 Da formato a una cadena de mensaje con una lista de argumentos de variable.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Parámetros  
 `pszFormat`  
 Apunta a la cadena de formato de control. Se examinan para las inserciones y con formato en consecuencia. La cadena de formato es similar a la función en tiempo de ejecución `printf`-aplicar estilo a las cadenas de formato, salvo que permite para que los parámetros que se van a insertar en un orden arbitrario.  
  
 `pArgList`  
 Puntero a una lista de argumentos.  
  
### <a name="remarks"></a>Comentarios  
 La función requiere una definición de mensaje como entrada, determinado por `pszFormat`. La función copia el texto del mensaje con formato y una lista variable de argumentos para el `CStringT` objeto, procesar ninguna incrustado Inserta secuencias si se solicita.  
  
> [!NOTE]
> `FormatMessageV`llamadas [CStringT::FormatMessage](#formatmessage), que intenta asignar memoria del sistema para la cadena ha dado formateada recientemente. Si se produce un error en este intento, automáticamente se produce una excepción de memoria.  
  
 Para obtener más información, consulte las ventanas [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) funcionando en el [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="formatv"></a>CStringT::FormatV  
 Da formato a una cadena de mensaje con una lista de argumentos de variable.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Parámetros  
 `pszFormat`  
 Apunta a la cadena de formato de control. Se examinan para las inserciones y con formato en consecuencia. La cadena de formato es similar a la función en tiempo de ejecución `printf`-aplicar estilo a las cadenas de formato, salvo que permite para que los parámetros que se van a insertar en un orden arbitrario.  
  
 `args`  
 Puntero a una lista de argumentos.  
  
### <a name="remarks"></a>Comentarios  
 Escribe una cadena con formato y una lista variable de argumentos para una `CStringT` cadena en la misma forma en que `vsprintf_s` da formato a datos en una matriz de caracteres de estilo C.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities #120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable  
 Establece la cadena en el valor de la variable de entorno especificada.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Parámetros  
 `pszVar`  
 Puntero a una cadena terminada en null que especifica la variable de entorno.  
  
### <a name="return-value"></a>Valor devuelto  
 Si es correcta, su valor es distinto de cero. En caso contrario, es cero.  
  
### <a name="remarks"></a>Comentarios  
 Recupera el valor de la variable especificada en el bloque de entorno del proceso que realiza la llamada. El valor es en forma de una cadena de caracteres terminada en null.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="insert"></a>CStringT::Insert  
 Inserta un carácter o una subcadena en el índice especificado dentro de la cadena.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Parámetros  
 `iIndex`  
 El índice del carácter antes de la cual llevará a cabo la inserción.  
  
 `psz`  
 Un puntero a la subcadena que se va a insertar.  
  
 `ch`  
 El carácter que se va a insertar.  
  
### <a name="return-value"></a>Valor devuelto  
 La longitud de la cadena modificada.  
  
### <a name="remarks"></a>Comentarios  
 El `iIndex` parámetro identifica el primer carácter que se va a mover para dejar espacio para el carácter o subcadena. Si `nIndex` es cero, se producirá la inserción antes de la cadena completa. Si `nIndex` supera la longitud de la cadena, la función concatenará la cadena está presente y el nuevo material proporcionado, ya sea `ch` o `psz`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="left"></a>CStringT::Left  
 Extrae los `nCount` caracteres situados más a la izquierda de este objeto `CStringT` y devuelve una copia de la subcadena extraída.  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `nCount`  
 Número de caracteres que se va a extraer de este objeto `CStringT`.  
  
### <a name="return-value"></a>Valor devuelto  
 El objeto `CStringT` que contiene una copia del rango de caracteres especificado. El objeto `CStringT` devuelto puede estar vacío.  
  
### <a name="remarks"></a>Comentarios  
 Si `nCount` supera la longitud de la cadena, se extrae la cadena completa. `Left` es similar a la función `Left` de Basic.  
  
 En los juegos de caracteres multibyte (MBCS), `nCount` trata cada secuencia de 8 bits como un carácter, de modo que `nCount` devuelve el número de caracteres multibyte multiplicado por dos.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities n.º 123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="loadstring"></a>CStringT::LoadString  
 Lee un recurso de cadena de Windows, identificado por `nID`, en una existente `CStringT` objeto.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Parámetros  
 `hInstance`  
 Identificador de la instancia del módulo.  
  
 `nID`  
 Un identificador de recurso de cadena de Windows.  
  
 `wLanguageID`  
 El idioma del recurso de cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 Es distinto de cero si la carga de los recursos fue correcta; en caso contrario es 0.  
  
### <a name="remarks"></a>Comentarios  
 Carga el recurso de cadena ( `nID`) desde el módulo especificado ( `hInstance`) mediante el lenguaje especificado ( `wLanguage`).  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="makelower"></a>CStringT::MakeLower  
 Convierte el `CStringT` objeto a una cadena en minúsculas.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Valor devuelto  
 La cadena resultante en minúsculas.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="makereverse"></a>CStringT::MakeReverse  
 Invierte el orden de los caracteres de la `CStringT` objeto.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Valor devuelto  
 Resultante invierte la cadena.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="makeupper"></a>CStringT::MakeUpper  
 Convierte la `CStringT` objeto en una cadena en mayúsculas.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Valor devuelto  
 La cadena resultante en mayúsculas.  
  
### <a name="remarks"></a>Comentarios  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities número 127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="mid"></a>CStringT::Mid  
 Extrae una subcadena de longitud `nCount` caracteres desde este `CStringT` objeto, comenzando en la posición `iFirst` (basado en cero).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `iFirst`  
 Índice de base cero del primer carácter en esta `CStringT` objeto que va a incluir en la subcadena extraída.  
  
 `nCount`  
 Número de caracteres que se va a extraer de este objeto `CStringT`. Si no se proporciona este parámetro, se extrae el resto de la cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 El objeto `CStringT` que contiene una copia del rango de caracteres especificado. Tenga en cuenta que el valor devuelto `CStringT` objeto puede estar vacío.  
  
### <a name="remarks"></a>Comentarios  
 La función devuelve una copia de la subcadena extraída. `Mid`es similar a la función básica Mid (salvo que los índices en Basic son basado en uno).  
  
 Para juegos de caracteres multibyte (MBCS), `nCount` hace referencia a cada byte de 8 bits caracteres; es decir, una inicial y final de una carácter multibyte se cuentan como dos caracteres.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="oemtoansi"></a>CStringT::OemToAnsi  
 Convierte todos los caracteres en este `CStringT` objeto del juego al juego de caracteres ANSI de caracteres OEM.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Comentarios  
 Esta función no está disponible si `_UNICODE` está definido.  
  
### <a name="example"></a>Ejemplo  
 Vea el ejemplo de [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="operator_add"></a>CStringT::operator +  
 Concatena dos cadenas o un carácter y una cadena.  
  
```  
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```  
  
### <a name="parameters"></a>Parámetros  
 `ch1`  
 Un carácter ANSI o Unicode que se va a concatenar con una cadena.  
  
 `ch2`  
 Un carácter ANSI o Unicode que se va a concatenar con una cadena.  
  
 `str1`  
 Un `CStringT` para concatenar con una cadena o carácter.  
  
 `str2`  
 Un `CStringT` para concatenar con una cadena o carácter.  
  
 `psz1`  
 Un puntero a una cadena terminada en null al concatenar con una cadena o carácter.  
  
 `psz2`  
 Un puntero a una cadena para concatenar con una cadena o carácter.  
  
### <a name="remarks"></a>Comentarios  
 Hay siete formas de sobrecarga de la `CStringT::operator+` (función). La primera versión concatena dos existente `CStringT` objetos. Los dos siguientes concatenar un `CStringT` objeto y una cadena terminada en null. Los dos siguientes concatenar un `CStringT` objeto y un carácter ANSI. Las dos últimas concatenar un `CStringT` objeto y un carácter Unicode.  
  
> [!NOTE]
>  Aunque es posible crear `CStringT` instancias que contienen caracteres null incrustan, se recomienda en él. Al llamar a métodos y operadores en `CStringT` objetos que contienen caracteres nulos incrustados pueden generar resultados no deseados.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="operator_add_eq"></a>CStringT::operator +=  
 Concatena los caracteres hasta el final de la cadena.  
  
```  
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```  
  
### <a name="parameters"></a>Parámetros  
 str  
 Referencia a un objeto `CThisSimpleString`.  
  
 `bMFCDLL`  
 Valor booleano que especifica si el proyecto es una DLL de MFC o no.  
  
 `BaseType`  
 El tipo de base de la cadena.  
  
 `var`  
 Un objeto variant a concatenar con esta cadena.  
  
 `ch`  
 Un carácter ANSI o Unicode que se va a concatenar con una cadena.  
  
 `pszSrc`  
 Un puntero a la cadena original que se va a concatenar.  
  
 `strSrc`  
 Un `CStringT` para concatenar con esta cadena.  
  
### <a name="remarks"></a>Comentarios  
 El operador acepta otro `CStringT` objeto, un puntero de carácter o un carácter individual. Debe tener en cuenta que las excepciones pueden producirse siempre que se use este operador de concatenación porque se puede asignar un almacenamiento nuevo para los caracteres que se agregan a la de la memoria `CStringT` objeto.  
  
 Para obtener información sobre `CThisSimpleString`, vea la sección Comentarios de [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Aunque es posible crear `CStringT` instancias que contienen caracteres null incrustan, se recomienda en él. Al llamar a métodos y operadores en `CStringT` objetos que contienen caracteres nulos incrustados pueden generar resultados no deseados.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="operator_eq_eq"></a>CStringT::operator ==  
 Determina si dos cadenas son lógicamente iguales.  
  
```  
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `ch1`  
 Un carácter ANSI o Unicode para la comparación.  
  
 `ch2`  
 Un carácter ANSI o Unicode para la comparación.  
  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena terminada en null para la comparación.  
  
 `psz2`  
 Un puntero a una cadena terminada en null para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Comprueba si una cadena o un carácter en el lado izquierdo es igual a una cadena o un carácter a la derecha y devuelve TRUE o FALSE según corresponda.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="operator_neq"></a>CStringT::operator! =  
 Determina si dos cadenas lógicamente no son iguales.  
  
```  
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `ch1`  
 Un carácter ANSI o Unicode que se va a concatenar con una cadena.  
  
 `ch2`  
 Un carácter ANSI o Unicode que se va a concatenar con una cadena.  
  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena terminada en null para la comparación.  
  
 `psz2`  
 Un puntero a una cadena terminada en null para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Comprueba si una cadena o un carácter a la izquierda no es igual a una cadena o un carácter en el lado derecho.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="operator_lt"></a>CStringT::operator&lt;  
 Determina si la cadena en el lado izquierdo del operador es menor que la cadena del lado derecho.  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena terminada en null para la comparación.  
  
 `psz2`  
 Un puntero a una cadena terminada en null para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Una comparación lexicográfica entre cadenas, carácter a carácter hasta que:  
  
-   Encuentra dos caracteres correspondientes distintos y el resultado de la comparación se toma como el resultado de la comparación entre las cadenas.  
  
-   No encuentra ninguna desigualdad, pero una cadena tiene más caracteres que la otra y la cadena más corta se considera menor que la cadena más larga.  
  
-   No encuentra ninguna desigualdad y encuentra que las cadenas tienen el mismo número de caracteres, por lo que las cadenas son iguales.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="operator_gt"></a>CStringT::operator&gt;  
 Determina si la cadena en el lado izquierdo del operador es mayor que la cadena del lado derecho.  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena terminada en null para la comparación.  
  
 `psz2`  
 Un puntero a una cadena terminada en null para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Una comparación lexicográfica entre cadenas, carácter a carácter hasta que:  
  
-   Encuentra dos caracteres correspondientes distintos y el resultado de la comparación se toma como el resultado de la comparación entre las cadenas.  
  
-   No encuentra ninguna desigualdad, pero una cadena tiene más caracteres que la otra y la cadena más corta se considera menor que la cadena más larga.  
  
-   No encuentra ninguna desigualdad y encuentra que las cadenas tienen el mismo número de caracteres, por lo que las cadenas son iguales.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="operator_lt_eq"></a>CStringT::operator&lt;=  
 Determina si la cadena en el lado izquierdo del operador es menor o igual que la cadena del lado derecho.  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena terminada en null para la comparación.  
  
 `psz2`  
 Un puntero a una cadena terminada en null para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Una comparación lexicográfica entre cadenas, carácter a carácter hasta que:  
  
-   Encuentra dos caracteres correspondientes distintos y el resultado de la comparación se toma como el resultado de la comparación entre las cadenas.  
  
-   No encuentra ninguna desigualdad, pero una cadena tiene más caracteres que la otra y la cadena más corta se considera menor que la cadena más larga.  
  
-   No encuentra ninguna desigualdad y encuentra que las cadenas tienen el mismo número de caracteres, por lo que las cadenas son iguales.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="operator_gt_eq"></a>CStringT::operator&gt;=  
 Determina si la cadena en el lado izquierdo del operador es mayor o igual que la cadena del lado derecho.  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `str1`  
 Un `CStringT` para la comparación.  
  
 `str2`  
 Un `CStringT` para la comparación.  
  
 `psz1`  
 Un puntero a una cadena para la comparación.  
  
 `psz2`  
 Un puntero a una cadena para la comparación.  
  
### <a name="remarks"></a>Comentarios  
 Una comparación lexicográfica entre cadenas, carácter a carácter hasta que:  
  
-   Encuentra dos caracteres correspondientes distintos y el resultado de la comparación se toma como el resultado de la comparación entre las cadenas.  
  
-   No encuentra ninguna desigualdad, pero una cadena tiene más caracteres que la otra y la cadena más corta se considera menor que la cadena más larga.  
  
-   No encuentra ninguna desigualdad y encuentra que las cadenas tienen el mismo número de caracteres, por lo que las cadenas son iguales.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="remove"></a>CStringT::Remove  
 Quita todas las instancias del carácter especificado de la cadena.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Parámetros  
 `chRemove`  
 El carácter que se va a quitar de una cadena.  
  
### <a name="return-value"></a>Valor devuelto  
 El número de caracteres que se quitan de la cadena. Devuelve cero si no se cambia la cadena.  
  
### <a name="remarks"></a>Comentarios  
 Las comparaciones para el carácter distinguen entre mayúsculas y minúsculas.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="replace"></a>CStringT::Replace  
 Hay dos versiones de `Replace`. La primera versión reemplaza una o más copias de una subcadena por otra subcadena. Las subcadenas son terminada en null. La segunda versión reemplaza una o más copias de un carácter con otro carácter. Ambas versiones funcionan en los datos de caracteres almacenados en `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Parámetros  
 `pszOld`  
 Un puntero a una cadena terminada en null que será sustituido por `pszNew`.  
  
 `pszNew`  
 Un puntero a una cadena terminada en null que reemplaza `pszOld`.  
  
 `chOld`  
 El carácter que será sustituido por `chNew`.  
  
 `chNew`  
 El carácter reemplazando `chOld`.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el número de instancias reemplazados del carácter o subcadena o cero si no se cambia la cadena.  
  
### <a name="remarks"></a>Comentarios  
 `Replace`puede cambiar la longitud de cadena porque `pszNew` y `pszOld` no es necesario tener la misma longitud, y se pueden cambiar varias copias de la subcadena antigua al nuevo. La función realiza a una coincidencia entre mayúsculas y minúsculas.  
  
 Ejemplos de `CStringT` instancias son `CString`, `CStringA`, y `CStringW`.  
  
 Para `CStringA`, `Replace` funciona con ANSI o con caracteres multibyte (MBCS). Para `CStringW`, `Replace` funciona con caracteres anchos.  
  
 Para `CString`, se selecciona el tipo de datos de caracteres en tiempo de compilación, en función de si se definen las constantes en la tabla siguiente.  
  
|Constante definida|Tipo de datos de caracteres|  
|----------------------|-------------------------|  
|`_UNICODE`|Caracteres anchos|  
|`_MBCS`|Caracteres multibyte|  
|Ninguno|Caracteres de byte único|  
|Ambos|Sin definir|  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="reversefind"></a>CStringT::ReverseFind  
 Busca este `CStringT` objeto para la última coincidencia de un carácter.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Parámetros  
 `ch`  
 El carácter que se va a buscar.  
  
### <a name="return-value"></a>Valor devuelto  
 Índice de base cero del último carácter en esta `CStringT` objeto que coincide con el carácter solicitado, o -1 si no se encuentra el carácter.  
  
### <a name="remarks"></a>Comentarios  
 La función es similar a la función de tiempo de ejecución `strrchr`.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="right"></a>CStringT::Right  
 Extrae la última (es decir, derecha) `nCount` caracteres desde este `CStringT` de objetos y devuelve una copia de la subcadena extraída.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `nCount`  
 Número de caracteres que se va a extraer de este objeto `CStringT`.  
  
### <a name="return-value"></a>Valor devuelto  
 El objeto `CStringT` que contiene una copia del rango de caracteres especificado. Tenga en cuenta que el valor devuelto `CStringT` objeto puede estar vacío.  
  
### <a name="remarks"></a>Comentarios  
 Si `nCount` supera la longitud de la cadena, se extrae la cadena completa. `Right`es similar a las opciones básicas `Right` función (salvo que los índices en Basic están basadas en cero).  
  
 Para juegos de caracteres multibyte (MBCS), `nCount` hace referencia a cada byte de 8 bits caracteres; es decir, una inicial y final de una carácter multibyte se cuentan como dos caracteres.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="setsysstring"></a>CStringT::SetSysString  
 Reasigna el `BSTR` que señala `pbstr` y copia el contenido de la `CStringT` objeto en él, incluidos el `NULL` caracteres.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `pbstr`  
 Un puntero a una cadena de caracteres.  
  
### <a name="return-value"></a>Valor devuelto  
 La nueva cadena.  
  
### <a name="remarks"></a>Comentarios  
 Según el contenido de la `CStringT` (objeto), el valor de la `BSTR` referenciado por `pbstr` puede cambiar. La función produce una `CMemoryException` si existe suficiente memoria.  
  
 Esta función se utiliza normalmente para cambiar el valor de cadenas que se pasan por referencia para la automatización.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="spanexcluding"></a>CStringT::SpanExcluding  
 Extrae caracteres de la cadena, comenzando por el primer carácter, que no están en el juego de caracteres identificados por `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `pszCharSet`  
 Una cadena se interpreta como un juego de caracteres.  
  
### <a name="return-value"></a>Valor devuelto  
 Una subcadena que contiene caracteres de la cadena que no están en `pszCharSet`, comenzando por el primer carácter de la cadena y termina con el primer carácter que se encuentra en la cadena que también está disponible en `pszCharSet` (es decir, empezando por el primer carácter en la cadena y hasta, pero sin incluir el primer carácter que se encuentra en la cadena `pszCharSet`). Devuelve la cadena completa si ningún carácter de `pszCharSet` se encuentra en la cadena.  
  
### <a name="remarks"></a>Comentarios  
 `SpanExcluding`extrae y devuelve todos los caracteres anteriores de la primera aparición de un carácter de `pszCharSet` (es decir, el carácter de `pszCharSet` y no se devuelven todos los caracteres siguientes en la cadena). Si ningún carácter de `pszCharSet` se encuentra en la cadena, a continuación, `SpanExcluding` devuelve la cadena completa.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="spanincluding"></a>CStringT::SpanIncluding  
 Extrae caracteres de la cadena, comenzando por el primer carácter, que se encuentran en el juego de caracteres identificados por `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `pszCharSet`  
 Una cadena se interpreta como un juego de caracteres.  
  
### <a name="return-value"></a>Valor devuelto  
 Una subcadena que contiene caracteres de la cadena que se encuentran en `pszCharSet`, comenzando con el primer carácter de la cadena y la finalización cuando se encuentra un carácter en la cadena que no esté en `pszCharSet`. `SpanIncluding`Devuelve una subcadena vacía si el primer carácter de la cadena no está en el conjunto especificado.  
  
### <a name="remarks"></a>Comentarios  
 Si el primer carácter de la cadena no está en el juego de caracteres, a continuación, `SpanIncluding` devuelve una cadena vacía. En caso contrario, devuelve una secuencia de caracteres consecutivos que se encuentran en el conjunto.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="tokenize"></a>CStringT::Tokenize  
 Busca el siguiente token en una cadena de destino  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Parámetros  
 `pszTokens`  
 Una cadena que contiene delimitadores de token. No es importante el orden de estos delimitadores.  
  
 `iStart`  
 Índice de base cero que se va a comenzar la búsqueda.  
  
### <a name="return-value"></a>Valor devuelto  
 Un `CStringT` objeto que contiene el valor del token actual.  
  
### <a name="remarks"></a>Comentarios  
 El `Tokenize` función busca el siguiente token en la cadena de destino. El juego de caracteres en `pszTokens` especifica los delimitadores posibles del token se encuentre. En cada llamada a `Tokenize` empieza a la función en `iStart`, omite los delimitadores iniciales y devuelve un `CStringT` objeto que contiene el token actual, que es una cadena de caracteres hasta el siguiente carácter de delimitador. El valor de `iStart` se actualiza para que sea la posición siguiente el carácter delimitador final, o -1 si se alcanzó el final de la cadena. Más tokens se pueden extraer el resto de la cadena de destino mediante una serie de llamadas a `Tokenize`con `iStart` para realizar un seguimiento de dónde en la cadena es el token siguiente que debe leerse. Cuando no hay ningún más tokens la función devuelve una cadena vacía y `iStart` se establecerá en -1.  
  
 A diferencia de la biblioteca CRT dividir las funciones como [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` no modifica la cadena de destino.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Comentarios  
 La salida de este ejemplo es la siguiente:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="trim"></a>CStringT::Trim  
 Recorta iniciales y finales de caracteres de la cadena.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Parámetros  
 `chTarget`  
 El carácter de destino que se deben recortar.  
  
 `pszTargets`  
 Un puntero a una cadena que contiene los caracteres de destino que se deben recortar. Todas las iniciales y finales de las apariciones de caracteres `pszTarget` se eliminarán de la `CStringT` objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve la cadena recortada.  
  
### <a name="remarks"></a>Comentarios  
 Quita todas las apariciones del principio y el finales de uno de los siguientes:  
  
-   El carácter especificado por`chTarget.`  
  
-   Todos los caracteres que se encuentran en la cadena especificada por`pszTargets.`  
  
-   Espacio en blanco.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Comentarios  
 La salida de este ejemplo es la siguiente:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="trimleft"></a>CStringT::TrimLeft  
 Quita los caracteres iniciales de la cadena.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Parámetros  
 `chTarget`  
 El carácter de destino que se deben recortar.  
  
 `pszTargets`  
 Un puntero a una cadena que contiene los caracteres de destino que se deben recortar. Todas las apariciones de caracteres de `pszTarget` se eliminarán de la `CStringT` objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 Cadena recortada resultante.  
  
### <a name="remarks"></a>Comentarios  
 Quita todas las apariciones del principio y el finales de uno de los siguientes:  
  
-   El carácter especificado por`chTarget.`  
  
-   Todos los caracteres que se encuentran en la cadena especificada por`pszTargets.`  
  
-   Espacio en blanco.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="trimright"></a>CStringT::TrimRight  
 Quita los caracteres finales de la cadena.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Parámetros  
 `chTarget`  
 El carácter de destino que se deben recortar.  
  
 `pszTargets`  
 Un puntero a una cadena que contiene los caracteres de destino que se deben recortar. Todos los finales de las apariciones de caracteres `pszTarget` se eliminarán de la `CStringT` objeto.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve el `CStringT` objeto que contiene la cadena recortada.  
  
### <a name="remarks"></a>Comentarios  
 Quita los finales apariciones de uno de los siguientes:  
  
-   El carácter especificado por`chTarget.`  
  
-   Todos los caracteres que se encuentran en la cadena especificada por`pszTargets.`  
  
-   Espacio en blanco.  
  
 El `CStringT& TrimRight(XCHAR chTarget)` versión acepta un parámetro de carácter y quita todas las copias de dicho carácter de final de `CStringT` datos de cadena. Se inicia desde el final de la cadena y funciona hacia la parte delantera. Se detiene cuando encuentra un carácter distinto o cuando `CSTringT` agota los datos de caracteres.  
  
 El `CStringT& TrimRight(PCXSTR pszTargets)` versión acepta una cadena terminada en null que contiene todos los caracteres diferentes que se buscará. Quita todas las copias de los caracteres en el `CStringT` objeto. Se inicia al final de la cadena y funciona hacia la parte delantera. Se detiene cuando encuentra un carácter que no está en la cadena de destino, o cuando `CStringT` agota los datos de caracteres. No intenta coincidir con la cadena de destino completa a una subcadena al final de `CStringT`.  
  
 El `CStringT& TrimRight()` versión no requiere ningún parámetro. Que recorta los caracteres de espacio en blanco finales desde el final de la `CStringT` cadena. Caracteres de espacio en blanco pueden ser saltos de línea, espacios o tabulaciones.  
  
-  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[NVC_ATLMFC_Utilities #138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>Vea también  
 [Gráfico de jerarquías](../../mfc/hierarchy-chart.md)   
 [Clases compartidas de ATL y MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT (clase)](../../atl-mfc-shared/reference/csimplestringt-class.md)


