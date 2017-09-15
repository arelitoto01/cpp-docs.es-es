---
title: "C&#243;mo: Calcular las referencias de cadenas ANSI para ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], calcular las referencias de cadenas ANSI"
  - "cadenas nativas [C++]"
  - "cadenas [C++], ADO.NET"
ms.assetid: 6759d5a2-515f-4079-856b-73b1c1e68f2d
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C&#243;mo: Calcular las referencias de cadenas ANSI para ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Muestra cómo agregar una cadena nativa \(`char *`\) a una base de datos y cómo calcular las referencias de una <xref:System.String?displayProperty=fullName> de una base de datos para una cadena nativa.  
  
## Ejemplo  
 En este ejemplo, la clase DatabaseClass se crea para interactuar con un objeto <xref:System.Data.DataTable> de ADO.NET.  Tenga en cuenta que esta clase es una `class` de C\+\+ nativa \(si se compara con una `ref class` o `value class`\).  Esto es necesario porque deseamos utilizar esta clase desde código nativo y no se pueden utilizar tipos administrados en código nativo.  Esta clase se compilará para CLR, según indica la directiva `#pragma managed` que precede a la declaración de clase.  Para obtener más información sobre esta directiva, vea [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Tenga en cuenta el miembro privado de la clase DatabaseClass: `gcroot<DataTable ^> table`.  Como los tipos nativos no pueden contener tipos administrados, es necesario utilizar la palabra clave `gcroot`.  Para obtener más información sobre `gcroot`, vea [Cómo: Declarar controladores en tipos nativos](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 El resto del código de este ejemplo es código nativo de C\+\+, según indica la directiva `#pragma unmanaged` que precede a `main`.  En este ejemplo, se crea una nueva instancia de DatabaseClass y se llama a sus métodos para crear una tabla y rellenar algunas filas de ésta.  Observe que las cadenas nativas de C\+\+ se pasan como valores de la columna de base de datos StringCol.  Dentro de DatabaseClass, estas cadenas se convierten en cadenas administradas utilizando la funcionalidad de cálculo de referencias que encontramos en el espacio de nombres <xref:System.Runtime.InteropServices?displayProperty=fullName>.  En concreto, el método <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> se utiliza para calcular las referencias de `char *` para <xref:System.String> y el método <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> se utiliza para calcular las referencias de <xref:System.String> para `char *`.  
  
> [!NOTE]
>  La memoria asignada por <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> se debe desasignar llamando a <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> o a `GlobalFree`.  
  
```  
// adonet_marshal_string_native.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(char *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringAnsi(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(char *dataColumn, char **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringAnsi(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a char *.  
            values[i] = (char *)Marshal::StringToHGlobalAnsi(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
    db->AddRow("This is string 1.");  
    db->AddRow("This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    char *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        "StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        cout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalAnsi.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
  **StringCol: es la cadena 1.**  
**StringCol: es la cadena 2.**   
## Compilar el código  
  
-   Para compilar el código desde la línea de comandos, guarde el ejemplo de código en un archivo denominado adonet\_marshal\_string\_native.cpp y escriba la instrucción siguiente:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## Seguridad de .NET Framework  
 Para obtener información sobre problemas de seguridad relacionados con ADO.NET, vea [Proteger aplicaciones de ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Vea también  
 <xref:System.Runtime.InteropServices>   
 [Acceso a datos en ASP.NET \(Visual Studio\)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/es-es/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilidad nativa y de .NET](../dotnet/native-and-dotnet-interoperability.md)