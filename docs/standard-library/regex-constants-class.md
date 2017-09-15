---
title: regex_constants (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_constants
- regex/std::regex_constants
- error_collate
- regex/std::regex_constants::error_collate
- error_ctype
- regex/std::regex_constants::error_ctype
- error_escape
- regex/std::regex_constants::error_escape
- error_backref
- regex/std::regex_constants::error_backref
- error_brack
- regex/std::regex_constants::error_brack
- error_paren
- regex/std::regex_constants::error_paren
- error_brace
- regex/std::regex_constants::error_brace
- error_badbrace
- regex/std::regex_constants::error_badbrace
- error_range
- regex/std::regex_constants::error_range
- error_space
- regex/std::regex_constants::error_space
- error_badrepeat
- regex/std::regex_constants::error_badrepeat
- error_complexity
- regex/std::regex_constants::error_complexity
- error_stack
- regex/std::regex_constants::error_stack
- error_parse
- regex/std::regex_constants::error_parse
- error_syntax
- regex/std::regex_constants::error_syntax
- match_default
- regex/std::regex_constants::match_default
- match_not_bol
- regex/std::regex_constants::match_not_bol
- match_not_eol
- regex/std::regex_constants::match_not_eol
- match_not_bow
- regex/std::regex_constants::match_not_bow
- match_not_eow
- regex/std::regex_constants::match_not_eow
- match_any
- regex/std::regex_constants::match_any
- match_not_null
- regex/std::regex_constants::match_not_null
- match_continuous
- regex/std::regex_constants::match_continuous
- match_prev_avail
- regex/std::regex_constants::match_prev_avail
- format_default
- regex/std::regex_constants::format_default
- format_sed
- regex/std::regex_constants::format_sed
- format_no_copy
- regex/std::regex_constants::format_no_copy
- format_first_only
- regex/std::regex_constants::format_first_only
- regex/std::regex_constants::ECMAScript
- regex/std::regex_constants::basic
- regex/std::regex_constants::extended
- regex/std::regex_constants::awk
- regex/std::regex_constants::grep
- regex/std::regex_constants::egrep
- regex/std::regex_constants::icase
- regex/std::regex_constants::nosubs
- regex/std::regex_constants::optimize
- regex/std::regex_constants::collate
dev_langs:
- C++
helpviewer_keywords:
- regex_constants class
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
caps.latest.revision: 18
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
ms.openlocfilehash: 83cf6d3c8b6c571898bf6d1f2aeeefbc930dd573
ms.contentlocale: es-es
ms.lasthandoff: 04/29/2017

---
# <a name="regexconstants-class"></a>regex_constants (Clase)
Espacio de nombres para las marcas de expresiones regulares.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
namespace regex_constants {  
    enum syntax_option_type;  
    enum match_flag_type;  
    enum error_type;  
 }  
```  
  
## <a name="remarks"></a>Comentarios  
 El espacio de nombres `regex_constants` encapsula varios tipos de marca y sus valores de marca asociados.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<regex>  
  
 **Espacio de nombres:** std  
  
##  <a name="error_type"></a> regex_constants::error_type  
 Marcas para notificar errores de sintaxis de expresión regular.  
  
```  
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };  
```  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un tipo enumerado que describe un objeto que puede contener marcadores de error. Los diferentes valores de marca son:  
  
 `error_backref`: la expresión contenía una referencia inversa no válida  
  
 `error_badbrace`: la expresión contenía un recuento no válido en una expresión { }  
  
 `error_badrepeat`: una expresión de repetición (uno de "*", '', "+", "{" en la mayoría de los contextos) no estaba precedida por una expresión  
  
 `error_brace`: la expresión contenía un "{" o un "}" desemparejado  
  
 `error_brack`: la expresión contenía un "[" o un "]" desemparejado  
  
 `error_collate`: la expresión contenía un nombre de elemento de intercalación no válido  
  
 `error_complexity`: error en intento de coincidencia porque era demasiado compleja  
  
 `error_ctype`: la expresión contenía un nombre de clase de carácter no válido  
  
 `error_escape`: la expresión contenía una secuencia de escape no válido  
  
 `error_paren`: la expresión contenía un "(" o un ")" desemparejado  
  
 `error_parse`: la expresión no se pudo analizar  
  
 `error_range`: la expresión contenía un especificador de rango de carácter no válido  
  
 `error_space`: error al analizar una expresión regular porque no había suficientes recursos disponibles  
  
 `error_stack`: error en intento de coincidencia porque no había suficiente memoria disponible  
  
 `error_syntax`: error en el análisis de un error de sintaxis  
  
 `error_backref`: la expresión contenía una referencia inversa no válida  
  
##  <a name="match_flag_type"></a> regex_constants::match_flag_type  
 Marcadores para las opciones de coincidencia de expresión regular.  
  
```  
enum match_flag_type 
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };  
```  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un tipo de máscara de bits que describe las opciones que se van a usar al buscar coincidencias entre una secuencia de texto y una expresión regular, así como las marcas de formato que se usarán al reemplazar texto. Las opciones pueden combinarse con `|`.  
  
 Las opciones de coincidencia son las siguientes:  
  
 `match_default`  
  
 `match_not_bol`: no tratar la primera posición de la secuencia de destino como el principio de una línea  
  
 `match_not_eol`: no tratar la posición más allá del final de la secuencia de destino como el final de una línea  
  
 `match_not_bow`: no tratar la primera posición de la secuencia de destino como el principio de una palabra  
  
 `match_not_eow`: no tratar la posición más allá del final de la secuencia de destino como el final de una palabra  
  
 `match_any`: si se permite más de una coincidencia, cualquier coincidencia es aceptable  
  
 `match_not_null`: no tratar una subsecuencia vacía como una coincidencia  
  
 `match_continuous`: solo buscar coincidencias en el principio de la secuencia de destino  
  
 `match_prev_avail` -- `--first` es un iterador válido; omitir las opciones `match_not_bol` y `match_not_bow` si están establecidas  
  
 Las marcas de formato son las siguientes:  
  
 `format_default`: usar reglas de formato de ECMAScript  
  
 `format_sed`: usar reglas de formato usadas  
  
 `format_no_copy`: no copiar texto que no coincide con la expresión regular  
  
 `format_first_only`: no buscar coincidencias después de la primera  
  
##  <a name="syntax_option_type"></a> regex_constants::syntax_option_type  
 Marcas para seleccionar las opciones de sintaxis.  
  
```  
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };  
```  
  
### <a name="remarks"></a>Comentarios  
 El tipo es un tipo de máscara de bits que describe los especificadores de idioma y los modificadores de sintaxis que se usarán al compilar una expresión regular. Las opciones pueden combinarse con `|`. Debe usarse un especificador de idioma a la vez.  
  
 Los especificadores de idioma son:  
  
 `ECMAScript`: compila como ECMAScript  
  
 `basic`: compila como BRE  
  
 `extended`: compila como ERE  
  
 `awk`: compila como awk  
  
 `grep`: compila como grep  
  
 `egrep`: compila como egrep  
  
 Los modificadores de sintaxis son los siguientes:  
  
 `icase`: genera coincidencias sin distinción entre mayúsculas y minúsculas  
  
 `nosubs`: no es necesario que la implementación haga un seguimiento de los contenidos de los grupos de captura  
  
 `optimize`: la implementación debe dar prioridad a la velocidad de coincidencia, en lugar de la velocidad de compilación de expresiones regulares  
  
 `collate`: genera coincidencias dependientes de la configuración regional  
  
## <a name="see-also"></a>Vea también  
[\<regex>](../standard-library/regex.md)  
[regex_error (Clase)](../standard-library/regex-error-class.md)  
[Funciones de \<regex>](../standard-library/regex-functions.md)  
[regex_iterator (Clase)](../standard-library/regex-iterator-class.md)  
[Operadores de \<regex>](../standard-library/regex-operators.md)  
[regex_token_iterator (Clase)](../standard-library/regex-token-iterator-class.md)  
[regex_traits (Clase)](../standard-library/regex-traits-class.md)  
[Definiciones de tipo \<regex>](../standard-library/regex-typedefs.md)  
