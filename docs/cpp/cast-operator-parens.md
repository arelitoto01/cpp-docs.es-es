---
title: "Operador de conversi&#243;n: () | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "() (operador de conversión)"
  - "operadores de conversión"
ms.assetid: 4c99eb92-1b19-4a5d-9840-5d8c29b8453e
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Operador de conversi&#243;n: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Una conversión de tipo proporciona un método para la conversión explícita del tipo de un objeto en una situación concreta.  
  
## Sintaxis  
  
```  
  
      unary-expression  
( type-name ) cast-expression  
```  
  
## Comentarios  
 Cualquier expresión unaria se considera una expresión de conversión.  
  
 El compilador trata *cast\-expression* como tipo *type\-name* una vez realizada una conversión de tipo.  Las conversiones se pueden utilizar para convertir objetos de cualquier tipo escalar en cualquier otro tipo escalar.  Las conversiones de tipos explícitas están restringidas por las mismas reglas que determinan los efectos de las conversiones implícitas.  Se pueden aplicar otras restricciones derivadas de los tamaños reales o de la representación de tipos específicos.  
  
## Ejemplo  
  
```  
// expre_CastOperator.cpp  
// compile with: /EHsc  
// Demonstrate cast operator  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    double x = 3.1;  
    int i;  
    cout << "x = " << x << endl;  
    i = (int)x;   // assign i the integer part of x  
    cout << "i = " << i << endl;  
}  
```  
  
## Ejemplo  
  
```  
// expre_CastOperator2.cpp  
// The following sample shows how to define and use a cast operator.   
#include <string.h>  
#include <stdio.h>  
  
class CountedAnsiString  
{  
public:  
    // Assume source is not null terminated  
    CountedAnsiString(const char *pStr, size_t nSize) :  
                      m_nSize(nSize)  
    {  
        m_pStr = new char[sizeOfBuffer];  
  
        strncpy_s(m_pStr, sizeOfBuffer, pStr, m_nSize);  
        memset(&m_pStr[m_nSize], '!', 9); // for demonstration purposes.  
    }  
  
    // Various string-like methods...  
  
    const char *GetRawBytes() const  
    {  
        return(m_pStr);  
    }  
  
    //   
    // operator to cast to a const char *  
    //   
    operator const char *()  
    {  
        m_pStr[m_nSize] = '\0';  
        return(m_pStr);  
    }  
  
    enum  
    {  
        sizeOfBuffer = 20  
    } size;  
  
private:  
    char *m_pStr;  
    const size_t m_nSize;  
};  
  
int main()  
{  
    const char *kStr = "Excitinggg";  
    CountedAnsiString myStr(kStr, 8);  
  
    const char *pRaw = myStr.GetRawBytes();  
    printf_s("RawBytes truncated to 10 chars:   %.10s\n", pRaw);  
  
    const char *pCast = myStr; // or (const char *)myStr;  
    printf_s("Casted Bytes:   %s\n", pCast);  
  
    puts("Note that the cast changed the raw internal string");  
    printf_s("Raw Bytes after cast:   %s\n", pRaw);  
}  
```  
  
  **RawBytes truncado en 10 caracteres: Exciting\!\!**  
**Bytes convertidos: Exciting**  
**Observe que la conversión cambió la cadena interna sin formato**  
**Bytes sin formato después de la conversión: Exciting**   
## Vea también  
 [Expresiones con operadores unarios](../cpp/expressions-with-unary-operators.md)   
 [Operadores de C\+\+](../misc/cpp-operators.md)   
 [Operadores de C\+\+, precedencia y asociatividad](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operador de conversión explícita de tipos: \(\)](../cpp/explicit-type-conversion-operator-parens.md)   
 [Operadores de conversión](../cpp/casting-operators.md)   
 [Operadores de conversión](../c-language/cast-operators.md)